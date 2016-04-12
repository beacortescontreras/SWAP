#Práctica 3

##1.Instalar nginx en Ubuntu Server 12.04

Para realizar esta práctica lo primero que he tenido que hacer ha sido crear una nueva máquina virtual a la que he llamado *Ubuntu 3 (balanceador)* que como su propio
nombre indica la he usado para balancear la carga de las otras dos máquinas.

Ahora nos disponemos a instalar nginx, lo primero que hemos hecho ha sido importar la clave del repositorio de software:
	*cd /tmp/*
	*wget http://nginx.org/keys/nginx_signing.key*
	*apt-key add /tmp/nginx_signing.key*
	*rm -f /tmp/nginx_signing.key*
A continuación simplemente tenemos que instalar nginx usando el comando *apt-get install nginx*

![imagen](https://github.com/beacortescontreras/SWAP/blob/master/Practica3/imagenes/1.PNG)

Una vez instalado, procedemos a su configuración como balanceador de carga.

##2.Balanceo de carga usando nginx

Para poder hacer el balanceo de carga usando nginx vamos a tener que configurarlo modificando el fichero de configuración 
*/etc/nginx/conf.d/default.conf* el cual se nos quedaría tal que así:

![imagen](https://github.com/beacortescontreras/SWAP/blob/master/Practica3/imagenes/2.PNG)

Una vez configurado lanzamos el servicio nginx usando el comando *service nginx restart* y si no obtenemos ningun error 
probamos la configuración haciendo peticiones a la IP de la máquina balanceador usando el comando *curl*.

![Imagen](https://github.com/beacortescontreras/SWAP/blob/master/Practica3/imagenes/1URL.PNG)

Y aquí ya podemos ver el resultado:

![Imagen](https://github.com/beacortescontreras/SWAP/blob/master/Practica3/imagenes/3URL.PNG)


![Imagen](https://github.com/beacortescontreras/SWAP/blob/master/Practica3/imagenes/2URL.PNG)

##3.Balanceo de carga con haproxy

En primer lugar tenemos que instalar *haproxy* esto lo haremos usando el comando *apt-get install haproxy*. Una vez instalado
debemos modificar el archivo */etc/haproxy/haproxy.cfg* y dicho archivo debe quedar así: 

![Imagen](https://github.com/beacortescontreras/SWAP/blob/master/Practica3/imagenes/5.1.PNG) 

Una vez configurado tenemos detener el servicio *nginx* ya que escucha por el puerto 80 como *haproxy* para ello usaremos el comando 
*service nginx stop*. Ahora lanzamos el servicio *haproxy* mediante el comando */usr/sbin/haproxy -f /etc/haproxy/haproxy.cfg*: 

![Imagen](https://github.com/beacortescontreras/SWAP/blob/master/Practica3/imagenes/5.2.PNG)

Por último tendriamos que hacer lo mismo que en el ejercicio 2 con el comando *curl* para poder hacer peticiones a la IP del balanceador.



