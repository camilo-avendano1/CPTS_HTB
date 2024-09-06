 


#enumeracion #nmap #interes 
La manera universal de enumerar con nmap --> OJO EN CTFS --> la mayoria de veces este es el parametro general **nmap -p- --open -sC -sV --min-rate 5000 -vvv -n -Pn 10.10.10.10 --> REEMPLAZA AQUI POR LA IP VICTIMA** 


este comando me sirivo para sacar la version del servidor dns alojada en el puerto 53
`sudo nmap -sU --open -A 10.129.1.121 -p 53 -sV  --packet-trace`

![[Pasted image 20240904211003.png]]


escaneo profundo en smb lo que no puede traer, usuarios, sistemas operativos, incluso intenta fuerza bruta y contrasenas
`enum4linux -a 10.129.144.116`
