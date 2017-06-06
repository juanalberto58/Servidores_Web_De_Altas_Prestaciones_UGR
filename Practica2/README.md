# Práctica 2

Práctica realizada en la sesión 2

## Envío de un archivo con ssh
Para ello creamos un archivo tar.tgz que contendra la carpeta prueba y mediante ssh y la dirección 
ip se realiza en el envío.
**captura de pantalla del envío del tar.gz creado**
![imagen](https://github.com/AntonioJA/SWAP1617/blob/master/Pr%C3%A1ctica2/tarssh.png)

## Sincronización entre máquinas con rsync
Realizamos una sincronización entre nuestro directorio /var/www/ y el /var/www/ de la otra máquina mediante el comando rsync. Con esto vemos que el contenido que se encontraba en nuestro directorio se ha copiado en el otro.
**captura de pantalla de la copia con rsync**
![imagen](https://github.com/AntonioJA/SWAP1617/blob/master/Pr%C3%A1ctica2/rsync.png)

## Generación de clave atuomática par ssh
Utilizamos ssh-copy-id para almacenar la clave una vez que la introduzcamos y con ello poder acceder ya
automáticamente.
**captura de pantalla de la generación de clave automática**
![imagen](https://github.com/AntonioJA/SWAP1617/blob/master/Pr%C3%A1ctica2/keygen1.png)
![imagen](https://github.com/AntonioJA/SWAP1617/blob/master/Pr%C3%A1ctica2/keygen2.png)

## Uso de crontab
Creamos un archivo ejemplo en el que introducimos un mensaje hello
**captura de pantalla del uso de crontab**
![imagen](https://github.com/AntonioJA/SWAP1617/blob/master/Pr%C3%A1ctica2/crontab.png)
