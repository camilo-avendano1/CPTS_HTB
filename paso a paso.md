

* explorar cuantas maquinas hay en el host
#escaneo_red
```bash
sudo arp-scan -i eth0 -l
```
#nmap_magico
* tirarle el nmap magico de puertos abiertos
```bash
sudo nmap -p- --open -sS --min-rate 5000 -vvv -n -Pn 10.10.10.10 -oG puertos_abiertos
```
#nmap_magico 
* tiramos descubrimiento de versiones y servicios en los puertos

```shell
nmap -sCV -p22,80,443  10.10.10.10 -oN servicios_versiones
```

enumerar y tomar pantallazo a los servicios enumerados para la documentacion

#root_linux
buscar binarios para priv escalation linux ==find / -user root -perm /4000 2>/dev/null==

#permisos #privilegios
con el siguiente comando podemos verificar que permisos tenemos como usuarios en linux 
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
