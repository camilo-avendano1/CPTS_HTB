https://mega.nz/file/pOdwgYbB#8lTyf-mWFNq7xvKWObKUV9gkrZj3nzhuHVlGQmnZ6BQ


primero
![[Pasted image 20240913085242.png]]


le tire un escaneo y solo estaba el Puerto 80

![[Pasted image 20240913085429.png]]

es una web para en un servidor apache en un SO linux
![[Pasted image 20240913085542.png]]
hay un uploads que permite subir archivos
como es en php use la pagina de revershells https://www.revshells.com/
![[Pasted image 20240913085732.png]]
pongo el puerto en escucha para traer la shell con el siguiente comando 
![[Pasted image 20240913085816.png]]
y subo el archivo de la reverse shell 

lo que conectara con mi puerto y tendre la shell

luego realizo un tratamiento de consola como es linux para manipularla de manera correcta siguiendo los pasos 
![[Pasted image 20240913085942.png]]

una vez estoy alli lo que hago es ejecutar una bsuqueda de privilegios con 
sudo -l
lo cual me da una busqueda de archivos con privlegios root que me permiten subir, luego busco en 
[GTFOBins](https://gtfobins.github.io/)
el bianrio encontrado y ejecutamos
![[Pasted image 20240913090105.png]]

![[Pasted image 20240913090133.png]]