# Práctica: Instalación de MariaDB y PHP en Ubuntu 24.04 (completando el LAMP)

<p align="center">
 
</p>

<p align="center">
  <strong>🌐 INSTALACIÓN · CONFIGURACIÓN</strong>
</p>

---

<p align="center">
   💻 APLICACIONES WEB
</p>

<br>

##  Datos del alumno

- **Nombre:** Mario Alemany Cobo
- **Curso:** 2º SMR
- **Fecha:** 23/10/2026

---
## 4. Desarrollo de la práctica
### Apartado 1. Preparación del sistema
En este apartado vamos a preparar el sistema para poder instalar MariaDB y PHP correctamente. Para esto vamos a borrar los sitios que hicimos en la practica anterior y actualizaremos apache  y comprobaremos que siga funvionando con el siguiente comando:
![Captura del resultado final](./Imagenes/Captura_1.png)<br>
### Apartado 2. Instalación de MariaDB
Y ahora instalaremos MariaDB con el siguiente comando ```sudo apt install mariadb-server -y``` y comprobaremos la version con:
![Captura del resultado final](./Imagenes/Captura_2.png)<br>
### Apartado 3. Comprobación del funcionamiento
Vamos a comprobar el estado en el que se encuentra MariaDB
![Captura del resultado final](./Imagenes/Captura_3.1.png)<br>
Y entraremos en la base de datos d MariaDB con el siguiente comando:
![Captura del resultado final](./Imagenes/Captura_3.2.png)<br>
### Apartado 4. Comandos principales

|Comando                      | Función             |
|-------------------------------------|-----------------------------------------------|
|```sudo systemctl start mariadb``` | Arranca el servicio |
|```sudo systemctl stop mariadb```| Detiene el servicio |
|```sudo systemctl restart mariadb```| Reinicia el servicio |
|```sudo systemctl status mariadb```| Muestra su estado |
|```sudo systemctl enable mariadb```| Lo arranca automáticamente al encender el equipo |

### Apartado 5. ¿Qué pasa si MariaDB está parado?
Si MariaBD esta parado e intentamos entrar, nos mostrara un error como este:
![Captura del resultado final](./Imagenes/Captura_4.png)<br>
Despues volveremos a arrancarlo y comprobaremos que todo este en orden con:<br>
```sudo systemctl start mariadb```
```systemctl is-active mariadb```
> Si WordPress no pudiera conectar con la base de datos, ¿qué dos comandos de este apartado usarías para saber si el problema es que MariaDB está parado?<BR>
Utilizaria ```systemctl is-active mariadb``` y ```sudo mariadb``` ya que el primero nos dira si esta activo y el segundo nos dira si hay algun error
### Apartado 6. Instalación de PHP
| Paquete | Función |
|---|---|
| ```php``` | El lenguaje PHP |
| ```libapache2-mod-php``` | Permite a Apache ejecutar PHP |
| ```php-mysql``` | **Permite a PHP hablar con MariaDB (imprescindible)** |
| ```php-curl``` | Conexiones a otros servidores (actualizaciones, plugins) |
| ```php-gd``` | Tratamiento de imágenes |
| ```php-mbstring``` | Manejo de textos con tildes y caracteres especiales |
| ```php-xml``` | Lectura y escritura de ficheros XML |
| ```php-zip``` | Instalación y actualización de plugins y temas |
| ```php-intl``` | Idiomas y formatos regionales |
Instalaremos PHP con los siguientes comandos: ```sudo apt install php libapache2-mod-php php-mysql php-curl php-gd php-mbstring php-xml php-zip```, ```php-intl -y``` y con ```php -v``` comprobaremos la version de este mismo
![Captura del resultado final](./Imagenes/Captura_6.png)<br>
Y buscaremos en el navegador *http://IP_DE_TU_SERVIDOR/info.php*, aqui nos debera aparecer la siguiente pagina con la version de PHP
![Captura del resultado final](./Imagenes/Captura_6.2.png)<br>
> ¿Por qué es peligroso dejar info.php en un servidor real? ¿Para qué sirve el paquete php-mysql? <br>
Dejar un archivo info.php (que ejecuta la función phpinfo()) accesible públicamente en un servidor en producción es un riesgo de seguridad grave por fuga de información (Information Disclosure).
