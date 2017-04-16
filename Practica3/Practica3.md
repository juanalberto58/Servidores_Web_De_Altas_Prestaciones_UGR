# Documentacion Práctica 3 #

1.Una vex instalado nginx en la maquina balanceadora con los comandos:

sudo apt-get update && sudo apt-get dist-upgrade && sudo apt-get
autoremove

sudo apt-get install nginx

sudo systemctl start nginx

Ahora procedemos a configurar el archivo /etc/nginx/conf.d/default.conf de la siguiente forma:
![Practica3](/Practica3/ConfiguracionNginx.png)

Una vez configurado el archivo default.conf hemos borrado el archivo /etc/nginx/sites-enabled/default para que nos salga la página de inicio de cada una de las máquinas
![Practica3](/Practica3/RmDefault.png)

Y una vez hecho esto ya podemos comprobar que el balanceo de carga entre las dos máquinas que en nuestro caso hemos modificado el archivo default.conf para que la máquina 1 tenga el doble de capacidad que la máquina 2:

![Practica3](/Practica3/ConfiguracionDefaultFinal.png)

Finalmente podemos comprobar el reparto de carga final:

![Practica3](/Practica3/FuncionaminetoFinal.png)
