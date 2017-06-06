# Documentacion Práctica 4 #
# ASEGURAR LA GRANJA WEB #

## Instalar certificado SSL autofirmado para configurar el acceso HTTPS a los servidores

Lo primero que haremos será habilitar el modulo SSL con:

a2enmod ssl

Reiniciaremos el servicio apache con:

service apache2 restart

Creamos un directorio para albergar el certificado con:

mkdir /etc/apache2/ssl

![Practica4](/Practica4/Captura1.png)

Y ahora generaremos el certificado con:

openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/apache2/ssl/apache.key -out /etc/apache2/ssl/apache.crt

Que nos pedirá cierta información para la configuración del dominio

Todo esto por supuesto hay que realizarlo como root:

![Practica4](/Practica4/Captura2.png)

Una vez añadido la información y haber terminado el proceso de configuración deberemos de editar el archivo de configuracíon del sitio default-ssl que se encuentra en la siguiente ruta:

/etc/apache2/sites-available/default-ssl

Y agregar las siguientes lineas debajo de SSLEngine on:

![Practica4](/Practica4/Captura3.png)

Ahora activaremos el sitio default-ssl y reiniciaremos apache con:

a2ensite default-ssl
service apache2 reload

![Practica4](/Practica4/Captura4.png)

## Configuracíon del cortafuegos

Para configurar las reglas del cortafuegos con Iptables permitiendo el acceso por el puerto de HTTP y HTTPS vamos a proceder a crear un script en el cual mediante los siguientes comandos los habilitaremos:

![Practica4](/Practica4/ScriptIPTables.png)

Una vez creado el script procederemos a añadirlo al archivo rc.local que se encuentra en la siguiente dirección:

/etc/rc.local

![Practica4](/Practica4/ArchivoRcLocal.png)

Como vemos primero accedemos al directorio donde se encuentra el script, le damos permisos de ejecución y seguidamente lo ejecutamos.

Ahora para comprobar que todo ha ido correctamente utilizaremos el comando:

iptables -L -n -v

Que nos mostrara el estado del cortafuegos:

![Practica4](/Practica4/IptablesFuncionando.png)
