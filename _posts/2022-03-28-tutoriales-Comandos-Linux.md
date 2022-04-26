---
layout: single
title: Comandos básicos de linux
excerpt: "Empieza a usar Linux con estos comandos básicos"
date: 2022-03-28
classes: wide
header:
  teaser: /assets/images/Linux/LinuxLogo.jpg
  teaser_home_page: true
categories:
  - Linux
tags:  
  - Linux
---

![](/assets/images/linux/LinuxCommands.jpg)
<br>

En este post se mostrarán algunos de los comandos mas básicos de Linux. Estos comandos se pueden ejecutar independientemente de la distribuciones de Linux que estemos usando: Ubuntu, Debian, Arch, Kali, etc.

|Comando|Descripcion de uso|
|-------|------------------|
|`pwd`|Print Working Directory, indica el directorio en el que estamos|
|`cd`|Change Directory, permite cambiarnos de directorio|
|`ls`|List, lista el contenido de un directorio|
|`cat`|Concat, devuelve el contenido de un fichero en la terminal|
|`cp`|Copy, permite copiar ficheros|
|`mv`|Move, permite mover ficheros|
|`mkdir`|Make Directory, permite crear un directorio|
|`rmdir`|Remove Directory, permite eliminar un directorio vacio|
|`rm`|Remove, permite eliminar ficheros y directorios|
|`touch`|Touch, permite crear un fichero vacio|
|`locate`|Locate, permite localizar un fichero|
|`find`|Find, busca ficheros y directorios dentro de una ruta|
|`grep`|Grep, permite buscar dentro del texto almacenado en un fichero|
|`sudo`|SuperUser Do, permite ejecutar comandos con permisos de root|
|`head`|Head, permite ver las primeras lineas de un fichero|
|`tail`|Tail, permite ver las ultimas lineas de un fichero|
|`diff`|Difference, muestra las diferencias entre dos ficheros|
|`tar`|Tar, permite usar ficheros comprimidos del tipo tarball|
|`chmod`|Change Mod, permite cambiar los permisos de un fichero|
|`chown`|Change Owner, permite cambiar la propiedad de un fichero|
|`kill`|Kill, permite cerrar programas|
|`ping`|Ping, verifica tu estado de conectividad con un servidor|
|`wget`|Web Get, permite descargar ficheros de internet|
|`uname`|Unix Name, permite conocer datos del sistema Linux utilizado|
|`top`|Top, muestra los procesos en ejecucion del sistema|
|`man`|Manual, muestra informacion detallada de los comandos de Linux|
|`echo`|Echo, permite imprimir en pantalla texto plano|
|`hostname`|Hostname, permite saber el nombre del host|
|`useradd`|UserAdd, permite crear usuarios|
|`userdel`|UserDel, permite eliminar usuarios|



# Ejemplos

### pwd
Este comando nos devuelve la ruta absoluta en la que estamos trabajando, es decir la ruta desde /.
```bash 
j28905@PC->j28905:~$ pwd
/home/j28905

j28905@PC->j28905:~/Desktop$ pwd
/home/j28905/Desktop
 ```

### cd 
Este comando se utiliza para movernos a traves de los directorios del sistema. Se indica la ruta a seguir despues del comando cd.
Si no se le indica ninguna ruta, nos moverá al directorio principal del usuario que lo ejecute, /home/<user>.
```bash
j28905@PC->j28905:~$ cd Downloads/
j28905@PC->j28905:~/Downloads$ cd ../../..
j28905@PC->j28905:/$ cd
j28905@PC->j28905:~$
 ```
Notese que cuando estamos por debajo del directorio principal del usuario el simbolo de prompt es ~, mientras que cuando estamos situados en directorios por encima del home, el simbolo es $.


### ls
Este comando se utiliza para mostrar por pantalla el contenido de un directorio. Se puede usar sin argumentos, mostrara el contenido del directorio en el que se ejecuta, o con argumentos, especificando una ruta distinta o pasando argumentos para ver archivos ocultos, permisos, etc.
```bash
j28905@PC->j28905:/$ ls
bin   dev  home  lib    lib64   media  opt   root  sbin  srv  tmp  var
boot  etc  init  lib32  libx32  mnt    proc  run   snap  sys  usr
j28905@PC->j28905:/$ ls /home/j28905/
Desktop  Documents  Downloads
j28905@PC->j28905:/$ ls -alh
total 620K
drwxr-xr-x  1 root root 4.0K Apr 26 10:18 .
drwxr-xr-x  1 root root 4.0K Apr 26 10:18 ..
lrwxrwxrwx  1 root root    7 Apr 23  2020 bin -> usr/bin
drwxr-xr-x  1 root root 4.0K Apr 23  2020 boot
drwxr-xr-x  1 root root 4.0K Apr 26 11:00 dev
drwxr-xr-x  1 root root 4.0K Apr 26 11:00 etc
drwxr-xr-x  1 root root 4.0K Apr 26 10:50 home
-rwxr-xr-x  1 root root 618K Feb 23 23:08 init
lrwxrwxrwx  1 root root    7 Apr 23  2020 lib -> usr/lib
lrwxrwxrwx  1 root root    9 Apr 23  2020 lib32 -> usr/lib32
lrwxrwxrwx  1 root root    9 Apr 23  2020 lib64 -> usr/lib64
lrwxrwxrwx  1 root root   10 Apr 23  2020 libx32 -> usr/libx32
drwxr-xr-x  1 root root 4.0K Apr 23  2020 media
drwxr-xr-x  1 root root 4.0K Apr 26 10:18 mnt
drwxr-xr-x  1 root root 4.0K Apr 23  2020 opt
dr-xr-xr-x  9 root root    0 Apr 26 11:00 proc
drwx------  1 root root 4.0K Apr 26 10:52 root
drwxr-xr-x  1 root root 4.0K Apr 26 11:00 run
lrwxrwxrwx  1 root root    8 Apr 23  2020 sbin -> usr/sbin
drwxr-xr-x  1 root root 4.0K Apr 10  2020 snap
drwxr-xr-x  1 root root 4.0K Apr 23  2020 srv
dr-xr-xr-x 12 root root    0 Apr 26 11:00 sys
drwxrwxrwt  1 root root 4.0K Apr 26 10:50 tmp
drwxr-xr-x  1 root root 4.0K Apr 23  2020 usr
drwxr-xr-x  1 root root 4.0K Apr 23  2020 var
```

### cat
Este comando se usa para mostrar en pantalla el contenido completo de un fichero.

