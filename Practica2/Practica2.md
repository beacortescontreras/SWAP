#Pr�ctica 2

##1. Crear un tar con ficheros locales en un equipo remoto

He utilizado el comando *tar czf - /home/beacortescontreras | ssh 192.168.64.137 'cat > ~/tar.tgz*
donde la IP es la del equipo de destino en este caso la m�quina 2.

![imagen](https://github.com/beacortescontreras/SWAP/blob/master/Practica2/imagenes/1.PNG)

Ahora vamos hasta la m�quina 1 para ver que se ha creado el archivo *tar.tgz*

![imagen](https://github.com/beacortescontreras/SWAP/blob/master/Practica2/imagenes/2.PNG)

##2. Instalar la herramienta rsync

Para instalar la herramienta rsync he usado el comando *sudo apt-get install rsync* . Tendremos que activar
la cuenta root para poder trabajar con todos los permisos sobre los ficheros, esto lo haremos
con el comando *sudo passwd root*.

Ahora podemos probar el funcionamiento de rsync, clonando una carpeta. Para ello en la segunda m�quina ejecutamos el comando
*rsync -avz -e ssh root@192.168.64.138:/var/www/ /var/www/* poniendo la IP de la m�quina 1. Tambi�n esta herramienta nos permite 
especificar qu� directorios copiar y cu�les ignorar en el proceso de copia, de manera que no se sobreescriban los archivos que no
queremos, lo he hecho mediante este comando *rsync -avz --delete --exclude=**/stats --exclude=**/error --
exclude=**/files/pictures -e "ssh -l root" root@192.168.64.138:/var/www/ /var/www/* con la IP de la m�quina 1.

![imagen](https://github.com/beacortescontreras/SWAP/blob/master/Practica2/imagenes/4.PNG)

Y ahora comprobamos que el directorio /var/www se ha clonado bien en la m�quina 1.

![imagen](https://github.com/beacortescontreras/SWAP/blob/master/Practica2/imagenes/3.PNG)

##3. Acceso sin contrase�a para ssh

Configuraremos ssh para acceder a m�quinas remotas sin contrase�a con el comando *ssh-keygen -t dsa* y generamos la clave.

![imagen](https://github.com/beacortescontreras/SWAP/blob/master/Practica2/imagenes/8.PNG)

Ahora procedemos a copiar la clave a la m�quina principal en mi caso a la m�quina 1, la manera en que lo he hecho ha sido 
usando el siguiente comando *ssh-copy-id -i .ssh/id_dsa.pub root@192.168.64.138*

As�, ya podremos conectarnos a la m�quina 1 sin necesidad de introducir ninguna contrase�a, usando el comando *ssh 192.168.64.38 -l root*

![imagen](https://github.com/beacortescontreras/SWAP/blob/master/Practica2/imagenes/7.PNG)

##4. Programar tareas con crontab

He modificado el archivo /etc/crontab y he puesto una nueva tarea que es la que aparece en �ltimo lugar, he usado el comando 
explicado en el ejercicio 2 para que se realice autom�ticamente todos los d�as a las diez de la noche. Lo podemos ver haciendo un 
cat usando *cat crontab* dentro de etc.

![imagen](https://github.com/beacortescontreras/SWAP/blob/master/Practica2/imagenes/9.PNG)





