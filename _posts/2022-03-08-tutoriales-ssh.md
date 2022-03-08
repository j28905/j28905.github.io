---
layout: single
title: Usando ssh
excerpt: "Tutorial para usar ssh"
date: 2022-03-08
classes: wide
header:
  teaser: /assets/images/sshLogo.png
  teaser_home_page: true
categories:
  - Apps
  - Teletrabajo
tags:  
  - Apps
  - Teletrabajo
---


![](/assets/images/sshLogo.png)

## Primer paso

Deberemos tener una maquina virtual, ya sea en nuestro local o en la nube.
Linode.com ofrece 100$ gratuitos al darte de alta, y podremos usar maquinas con CPU compartidas por 5$ al mes, muy rentable.

## Segundo paso

Una vez que la maquina esta encendida y funcionando, nos hacemos con su IP.

## Tercer paso

La conexion, para ello ejecutamos desde nuestro local:
```bash
ssh root@<IP de la instancia>
```
Y aceptamos la autenticidad del host
```bash

The authenticity of host <IP de la instancia> (<IP de la instancia> cant be established.
ECDSA key fingerprint is SHA256:-------------------------.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes




Warning: Permanently added <IP de la instancia> (ECDSA) to the list of known hosts.
root@1<IP de la instancia> s password: 

Welcome to Ubuntu 20.04.4 LTS (GNU/Linux 5.4.0-100-generic x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Tue 08 Mar 2022 09:57:15 AM UTC

  System load:           0.0
  Usage of /:            8.0% of 24.05GB
  Memory usage:          14%
  Swap usage:            0%
  Processes:             107
  Users logged in:       0
  IPv4 address for eth0: <IP de la instancia>
  IPv6 address for eth0: <IP de la instancia>

The list of available updates is more than a week old.
To check for new updates run: sudo apt update


The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

root@localhost:~#

```

## Cuarto paso

Copiar la clave publica de nuestro local a la maquina virtual, para ello se imprime en pantalla

```bash 

usuario@local:~$ cat .ssh/id_rsa.pub 

```
y se copia a pelo en la maquina virtual

```bash

root@localhost:~# nano .ssh/authorized_keys

``` 
Existe otra opcion para hacer esto, la herramienta ssh-copy-id

```bash

usuario@local:~$ ssh-copy-id root@<IP de la instancia>

```

