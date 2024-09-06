

explorar cuantas maquinas hay en el host

`sudo arp-scan -i eth0 -l`

tirarle el nmap magico
#nmap_magico
**nmap -p- --open -sC -sV --min-rate 5000 -vvv -n -Pn 10.10.10.10

enumerar y tomar pantallazo a los servicios enumerados para la documentacion

#root_linux
buscar binarios para priv escalation linux find / -user root -perm /4000 2>/dev/null