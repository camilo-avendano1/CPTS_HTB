


primero ejecute 

`└─$ sudo nmap -sV -Pn 10.129.2.47 -n -sS --disable-arp-ping  --top-ports=20`


![[Pasted image 20240904214800.png]]
teniendo esto, busque vulnerabilidades en los puertos abiertos del cual no oobtuve nada

`nmap --script vuln -p 22,80 10.129.2.47`
![[Pasted image 20240904215038.png]]


no entendi como, solo segui la guia y me conecte  pero realmente no segui un estandard seguramente el peurto estaba abierto pero como no hice escaneo completo no lo vi 

`ncat -nv --source-port 53 10.129.2.47 50000`

