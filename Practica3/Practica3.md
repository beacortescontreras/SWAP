#Pr�ctica 3

##1.Instalar nginx en Ubuntu Server 12.04

	Para realizar esta pr�ctica lo primero que he tenido que hacer ha sido crear una nueva m�quina virtual a la que he llamado *Ubuntu 3 (balanceador)* que como su propio
nombre indica la he usado para balancear la carga de las otras dos m�quinas.

Ahora nos disponemos a instalar nginx, lo primero que hemos hecho ha sido importar la clave del repositorio de software:
	*cd /tmp/*
	*wget http://nginx.org/keys/nginx_signing.key*
	*apt-key add /tmp/nginx_signing.key*
	*rm -f /tmp/nginx_signing.key*
A continuaci�n simplemente tenemos que instalar nginx usando el comando *apt-get install nginx*

![imagen](https://github.com/beacortescontreras/SWAP/blob/master/Practica3/imagenes/1.PNG)

Una vez instalado, procedemos a su configuraci�n como balanceador de carga.

##2.Balanceo de carga usando nginx

	Para poder hacer el balanceo de carga usando nginx vamos a tener que configurarlo modificando el fichero de configuraci�n 
*/etc/nginx/conf.d/default.conf* el cual se nos quedar�a tal que as�:

![imagen](https://github.com/beacortescontreras/SWAP/blob/master/Practica3/imagenes/2.PNG)

Una vez configurado lanzamos el servicio nginx usando el comando *service nginx restart* y si no obtenemos ningun error 
probamos la configuraci�n haciendo peticiones a la IP de la m�quina balanceador usando el comando *curl*.

Aqu� lo hacemos en la m�quina principal:

![Imagen](https://github.com/beacortescontreras/SWAP/blob/master/Practica3/imagenes/3.PNG)

Aqu� lo hacemos en la m�quina secundaria:

![Imagen](https://github.com/beacortescontreras/SWAP/blob/master/Practica3/imagenes/4.PNG)

##3.Balanceo de carga con haproxy

	En primer lugar tenemos que instalar *haproxy* esto lo haremos usando el comando *apt-get install haproxy*. Una vez instalado
debemos modificar el archivo */etc/haproxy/haproxy.cfg* y dicho archivo debe quedar as�: 

![Imagen](https://github.com/beacortescontreras/SWAP/blob/master/Practica3/imagenes/5.1.PNG) 

	Una vez configurado tenemos detener el servicio *nginx* ya que escucha por el puerto 80 como *haproxy* para ello usaremos el comando 
*service nginx stop*. Ahora lanzamos el servicio *haproxy* mediante el comando */usr/sbin/haproxy -f /etc/haproxy/haproxy.cfg*: 

![Imagen](https://github.com/beacortescontreras/SWAP/blob/master/Practica3/imagenes/5.2.PNG)

Por �ltimo tendriamos que hacer lo mismo que en el ejercicio 2 con el comando *curl* para poder hacer peticiones a la IP del balanceador.



