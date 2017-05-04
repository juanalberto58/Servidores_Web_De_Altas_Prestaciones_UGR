# **EJERCICIOS TEMA 3**

## **EJERCICIO 3.1:**

**Buscar con qué órdenes de terminal o herramientas gráficas podemos configurar bajo Windows y bajo Linux el enrutamiento del tráfico de un servidor para pasar el tráfico desde una subred a otra.**


-Windows incluye el 'Servicio de Enrutamiento' y 'Acceso Remoto' que permite conectividad a usuarios remotos o conectividad entre sitios mediante conexiones de acceso telefónico o de red privada virtual (VPN) siguiendo un asistente.

-En Linux, la configuración de red se guarda en el archivo /etc/network/interfaces, el cual contiene un mini-lenguaje de descripción y configuración para cada interfaz de red, la configuración se puede asignar estáticamente o por DHCP. En una configuración estática típica se pueden indicar las siguientes cuestiones:

La dirección de red: address 192.168.1.10.
La máscara de subred: netmask 255.255.255.0.
La red: network 192.168.1.0
La dirección broadcast: broadcast 192.168.1.255.
La puerta de enlace: gateway 192.168.1.1.

Para crear una ruta se utiliza el comando route.


## **EJERCICIO 3.2:**

**Buscar con qué órdenes de terminal o herramientas gráficas podemos configurar bajo Windows y bajo Linux el filtrado y bloqueo de paquetes.**

-En Windows utilizamos IPsec.

-En Linux podemos utilizar las distintas opciones que nos ofrece iptables.


