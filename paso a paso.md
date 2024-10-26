

explorar cuantas maquinas hay en el host

`sudo arp-scan -i eth0 -l`

tirarle el nmap magico
#nmap_magico
**nmap -p- --open -sC -sV --min-rate 5000 -vvv -n -Pn 10.10.10.10

enumerar y tomar pantallazo a los servicios enumerados para la documentacion

#root_linux
buscar binarios para priv escalation linux find / -user root -perm /4000 2>/dev/null

#permisos #privilegios
con el siguiente comando podemos verificar que permisos tenemos como usairios en linux 
```shell-session
 sudo -l
```

comando para dar permisos de ejecucion a un archivo

```
chmod +x
```
comando para dar permisos de ssh key

```
chmod 600
```

bins para escalada de privilegios
[GTFOBins](https://gtfobins.github.io/)
