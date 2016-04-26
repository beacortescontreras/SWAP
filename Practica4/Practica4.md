#Práctica 4

##1.Comprobar el rendimiento de servidores web con Apache Benchmark.

Para poder comprobar el rendimiento con Apache Benchmark lo he hecho con el siguiente comando:

	*ab -n 1000 -c 10 http://IP correspondiente/index.html*
	
Lo he realizado 10 veces con Nginx, haproxy y mi máquina 1, a continuación muestro las tablas
con los datos recogidos durante la prueba:

![imagen](https://github.com/beacortescontreras/SWAP/blob/master/Practica4/imagenes/ABtablas.PNG)

Y aquí podemos ver las gráficas donde *serie 1* se refiere a *Nginx*, *serie 2* a *Haproxy* y 
finalmente *serie 3* se refiere a mi *Máquina 1*.

![imagen](https://github.com/beacortescontreras/SWAP/blob/master/Practica4/imagenes/AB1.PNG)
![imagen](https://github.com/beacortescontreras/SWAP/blob/master/Practica4/imagenes/AB2.PNG)
![imagen](https://github.com/beacortescontreras/SWAP/blob/master/Practica4/imagenes/AB3.PNG)

##2.Comprobar el rendimiento con Siege

Para poder comprobar el rendimiento con Siege lo he hecho con el siguiente comando:

	*siege -b -t60S -v http://IP correspondiente/index.html*
	
Lo he realizado 10 veces con Nginx, haproxy y mi máquina 1, a continuación muestro las tablas
con los datos recogidos durante la prueba:

![imagen](https://github.com/beacortescontreras/SWAP/blob/master/Practica4/imagenes/Siegetablas.PNG)

Y aquí podemos ver las gráficas donde *serie 1* se refiere a *Nginx*, *serie 2* a *Haproxy* y 
finalmente *serie 3* se refiere a mi *Máquina 1*.

![imagen](https://github.com/beacortescontreras/SWAP/blob/master/Practica4/imagenes/availa.PNG)
![imagen](https://github.com/beacortescontreras/SWAP/blob/master/Practica4/imagenes/Siege2.PNG)
![imagen](https://github.com/beacortescontreras/SWAP/blob/master/Practica4/imagenes/Siege3.PNG)
![imagen](https://github.com/beacortescontreras/SWAP/blob/master/Practica4/imagenes/trans.PNG)

##3.[Voluntario] Comprobar el rendimiento con Httperf

Para poder comprobar el rendimiento con Httperf lo he hecho con el siguiente comando:

	*httperf num-call 3000 rate 300 http://IP correspondiente/index.html*
	
Donde *num-call* se refiere a las peticiones que se envian por conexión y *rate* se refiere
cuantas peticiones se quieren enviar por segundo.

Lo he realizado 10 veces con Nginx, haproxy y mi máquina 1, a continuación muestro las tablas
con los datos recogidos durante la prueba:

![imagen](https://github.com/beacortescontreras/SWAP/blob/master/Practica4/imagenes/HTTPERFtablas.PNG)

Y aquí podemos ver las gráficas donde *serie 1* se refiere a *Nginx*, *serie 2* a *Haproxy* y 
finalmente *serie 3* se refiere a mi *Máquina 1*.

![imagen](https://github.com/beacortescontreras/SWAP/blob/master/Practica4/imagenes/httperf1.PNG)
![imagen](https://github.com/beacortescontreras/SWAP/blob/master/Practica4/imagenes/cone.PNG)
![imagen](https://github.com/beacortescontreras/SWAP/blob/master/Practica4/imagenes/re.PNG)
	
	
