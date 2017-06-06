# Práctica 6

Práctica realizada en la sesión 6
Esta práctica se centra en familiarizarnos con la distribución de datos RAID. 
Para ello configuraremos dos discos en RAID 1 por software, mediante el uso de máquina virtual.
En estas máquinas se añadiran dos discos más teniendo así tres discos. Estos dos discos los añadimos 
desde la configuración propia de la máquina virtual ya instalada. 

## Configuración del RAID por software
Comenzamos instalando el software necesario para instalar el RAID, mdadm.
Ahora ya podemos pasar a crear el RAID

**captura de pantalla de la creación del RAID**
![imagen](https://github.com/AntonioJA/SWAP1617/blob/master/Pr%C3%A1ctica6/CreacionRaid1md0.png)

Ya con el RAID creado primero le damos formato y pasamos a crear el directorio en el que lo montaremos.
![imagen](https://github.com/AntonioJA/SWAP1617/blob/master/Pr%C3%A1ctica6/ConfiguracionRaid.png)

Pasamos a comprobar el estado del RAID.

![imagen](https://github.com/AntonioJA/SWAP1617/blob/master/Pr%C3%A1ctica6/DetallesRaid.png)

Una vez hecho esto obtenemos los UUID de todos los dispositivos de almacenamiento.
![imagen](https://github.com/AntonioJA/SWAP1617/blob/master/Pr%C3%A1ctica6/UUIDs.png)

Y ya que sabemos cual es la UUIDs de nuestro RAID, configuramos el archivo /etc/fstab para que lo monte automáticamente.
![imagen](https://github.com/AntonioJA/SWAP1617/blob/master/Pr%C3%A1ctica6/Conffstab.png)

## Comprobación de funcionamiento
Una vez ya tenemos montado el RAID y configurado por completo pasamos a realizar las pruebas de funcionamiento pedidas.
Primero simulamos un fallo en uno de los discos, lo retiramos en caliente y comprobamos.

**Simulación de fallo y retirada en caliente en uno de los discos**
![imagen](https://github.com/AntonioJA/SWAP1617/blob/master/Pr%C3%A1ctica6/FalloRetiradaYComprobacion.png)

Una vez realizado esto procedemos a añadirlo y realizar una comprobación.

**Añadir disco**

![imagen](https://github.com/AntonioJA/SWAP1617/blob/master/Pr%C3%A1ctica6/AñadidoYComprobado.png)

