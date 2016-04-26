#Pr�ctica 4

##1.Comprobar el rendimiento de servidores web con Apache Benchmark.

Para poder comprobar el rendimiento con Apache Benchmark lo he hecho con el siguiente comando:
	*ab -n 1000 -c 10 http://IP correspondiente/index.html*
Lo he realizado 10 veces con Nginx, haproxy y mi m�quina 1, a continuaci�n muestro las tablas
con los datos recogidos durante la prueba:

![imagen](https://github.com/beacortescontreras/SWAP/blob/master/Practica4/imagenes/ABtablas.PNG)

Y aqu� podemos ver las gr�ficas donde *serie 1* se refiere a *Nginx*, *serie 2* a *Haproxy* y 
finalmente *serie 3* se refiere a mi *M�quina 1*.

![imagen](https://github.com/beacortescontreras/SWAP/blob/master/Practica4/imagenes/AB1.PNG)
![imagen](https://github.com/beacortescontreras/SWAP/blob/master/Practica4/imagenes/AB2.PNG)
![imagen](https://github.com/beacortescontreras/SWAP/blob/master/Practica4/imagenes/AB3.PNG)

##2.Comprobar el rendimiento con Siege

Para poder comprobar el rendimiento con Siege lo he hecho con el siguiente comando:
	*siege -b -t60S -v http://IP correspondiente/index.html*
Lo he realizado 10 veces con Nginx, haproxy y mi m�quina 1, a continuaci�n muestro las tablas
con los datos recogidos durante la prueba:

![imagen](https://github.com/beacortescontreras/SWAP/blob/master/Practica4/imagenes/Siegetablas.PNG)

Y aqu� podemos ver las gr�ficas donde *serie 1* se refiere a *Nginx*, *serie 2* a *Haproxy* y 
finalmente *serie 3* se refiere a mi *M�quina 1*.

![imagen](https://github.com/beacortescontreras/SWAP/blob/master/Practica4/imagenes/Siege1.PNG)
![imagen](https://github.com/beacortescontreras/SWAP/blob/master/Practica4/imagenes/Siege2.PNG)
![imagen](https://github.com/beacortescontreras/SWAP/blob/master/Practica4/imagenes/Siege3.PNG)
![imagen](https://github.com/beacortescontreras/SWAP/blob/master/Practica4/imagenes/Siege4.PNG)

##3.[Voluntario] Comprobar el rendimiento con Httperf

Para poder comprobar el rendimiento con Httperf lo he hecho con el siguiente comando:
	*httperf num-call 3000 rate 300 http://IP correspondiente/index.html*
Donde *num-call* se refiere a las peticiones que se envian por conexi�n y *rate* se refiere
cuantas peticiones se quieren enviar por segundo.

Lo he realizado 10 veces con Nginx, haproxy y mi m�quina 1, a continuaci�n muestro las tablas
con los datos recogidos durante la prueba:

![imagen](https://github.com/beacortescontreras/SWAP/blob/master/Practica4/imagenes/HTTPERFtablas.PNG)

Y aqu� podemos ver las gr�ficas donde *serie 1* se refiere a *Nginx*, *serie 2* a *Haproxy* y 
finalmente *serie 3* se refiere a mi *M�quina 1*.

![imagen](https://github.com/beacortescontreras/SWAP/blob/master/Practica4/imagenes/httperf1.PNG)
![imagen](https://github.com/beacortescontreras/SWAP/blob/master/Practica4/imagenes/httperf2.PNG)
![imagen](https://github.com/beacortescontreras/SWAP/blob/master/Practica4/imagenes/httperf3.PNG)
	
	