# Práctica 5

Práctica realizada en la sesión 5
En esta prácitca se busca aprender a configurar máquinas para mantener actualizadas las bases de datos.
Es decir una máquina sera la maestra y otra la esclava que se encargar de actualizar la información respecto a esta.

## Creación de la base de datos
Empezamos abriendo mysql, y siguendo los comandos que se ven en la imagen para crear la base de datos e introducir dos contactos en nuestro caso.
**captura de pantalla de la creación de la base de datos en mysql**
![imagen](https://github.com/AntonioJA/SWAP1617/blob/master/Pr%C3%A1ctica5/bdmaquina2.png)


## Replicación de la base de datos de forma manual
Una vez ya comprobada que tenemos creada nuestra base de datos y que podemos acceder a ella procedemos a realizar una copia de esta con mysqldump.
**captura de pantalla de la creación de la copia de esta base de datos**
![imagen](https://github.com/AntonioJA/SWAP1617/blob/master/Pr%C3%A1ctica5/mysqldumpCreacion.png)

Una vez realizado esto procedemos a enviar la copia creada a la otra máquina mediante scp, copiandola así en esta y utilizar ese archivo copiado para restaurar la base de datos copiada.
**captura de pantalla en el que se muestra este reparto de trabajo por defecto**
![imagen](https://github.com/AntonioJA/SWAP1617/blob/master/Pr%C3%A1ctica5/comandosCopia.png)


## Replicación de la base de datos mediante configuración maestro-esclavo
Para poder realizar esto empezamos configurandos los archivos mysqld.cnf de ambas máquinas.
En nuestro caso la máquina 2 es la maestra y tiene la siguiente configuración:
![imagen](https://github.com/AntonioJA/SWAP1617/blob/master/Pr%C3%A1ctica5/configuracionMaestro.png)

La máquina 1 es la esclava y tiene con esta configuración:
![imagen](https://github.com/AntonioJA/SWAP1617/blob/master/Pr%C3%A1ctica5/configuracionEsclavo.png)

Una vez hecho esto realizamos un restart del servicio mysql en ambas máquinas.

Procedemos a crear un usuario por el cual accedera la máquina esclava y mediante show master status obtenemos la información relevante para hacer la configuracion de la base de datos del esclavo.
![imagen](https://github.com/AntonioJA/SWAP1617/blob/master/Pr%C3%A1ctica5/ShowMasterStatus.png)

En la base de datos del esclavo hemos puesto la siguiente configuracion teniendo en cuenta los datos anteriores:
mysql> CHANGE MASTER TO MASTER_HOST='10.0.2.17',
MASTER_USER='esclavo', MASTER_PASSWORD='esclavo',
MASTER_LOG_FILE='mysql-bin.000005', MASTER_LOG_POS=154,
MASTER_PORT=3306;

Luego en el maestro desbloqueamos las tablas y ya funcionaría. 
Esto lo podemos ver mirando el show slave status y viendo como Seconds_Behind_Master es 0.
![imagen](https://github.com/AntonioJA/SWAP1617/blob/master/Pr%C3%A1ctica5/ShowSlaveStatus.png)

