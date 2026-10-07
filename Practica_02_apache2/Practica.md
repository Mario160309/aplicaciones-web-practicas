# Práctica: Instalación, configuración y securización de Apache en Ubuntu 24.04
## 4. Desarrollo de la práctica
### Apartado 1. Preparación del sistema
Primero actualizaremos los repositorios de ubuntu con el comando ```sudo apt update```
![Captura del resultado final](./Imagenes/Captura_1.png)<br>
Y comprobaremos la version del sistema con ```lsb_release -a```<br>
![Captura del resultado final](./Imagenes/Captura_2.png)<br>
### Apartado 2. Instalación de Apache
Ahora instalaremos Apache con el comando ```sudo apt install apache2 -y```
![Captura del resultado final](./Imagenes/Captura_3.png)<br>
**¿Qué paquetes adicionales se han instalado como dependencias? (pista: revisa la salida de apt).**
### Apartado 3. Comprobación del funcionamiento
Ahora vamos a comprobar el funcionamiento del servidos, estoy hay que hacerlo en 4 partes que son las siguientes:
  1. Con el comando ```sudo systemctl status apache2``` comporbaremos el estado del servicio
  2. Con el comando ```sudo ss -tulpn | grep apache2``` comprobaremos que puertos estan escuchando
  3. Para hacer pruebas las podemos hacer en la terminal o desde el navegador, en la terminal tendriamos que poner el siguiente comando ```curl -I http://localhost``` o en el navegador escribir lo siguiete *http://IP_DE_TU_SERVIDOR.*
     ![Captura del resultado final](./Imagenes/Captura_4.png)<br>
  4. Ahora comprobaremos si el Firewall esta activo y le diremos que deje a 'Apache' hacer lo que tenga que hacer con los siguientes comandos ```sudo ufw status``` y ```sudo ufw allow 'Apache'```
        ![Captura del resultado final](./Imagenes/Captura_5.png)<br>
