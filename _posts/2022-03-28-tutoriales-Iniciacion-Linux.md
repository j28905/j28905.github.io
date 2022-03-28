---
layout: single
title: Linux FileSystem
excerpt: "Entiende el arbol de directorios de Linux"
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
![](/assets/images/Linux/LinuxLogo.jpg)

En este post se explicara brevemente el sistema de ficheros de cualquier distribucion de Linux conocido como FHS (Filesystem Hierarchy Standard).
La siguiente imagen muestra sus principales directorios.
![](/assets/images/Linux/Linux_FileSystem.jpg)
<br>
Como se puede observar en la parte superior de la imagen, el directorio principal es /. Desde este, salen el resto de directorios.
Los siguentes directorios son
- boot: como su nombre dice, es el directorio donde se almacenan los ficheros necesarios para el arranque del sistema operativo.
- bin: aqui se almacenan los binarios de los distintos programas accesibles por todos los usuarios; cat, ls, cd, mkdir, etc
- sbin: aqui se almacenan los binarios que solo pueden ser utilizados por el administrador. Tambien conocidos como superbinarios, ya que incluyen los binarios de programas como adduser, chpasswd o ifconfig.
- media: aqui se almacenan los dispositivos conectados, normamente estos dispositivos se configuran automaticamente en el sistema operativo. Este seria el caso de las memorias USBs o los CD-ROMs por ejemplo.
- mnt: en este directorio, se almacenan los dispositivos montados en el sistema, normalmente son los discos duros, y estos se pueden montar y desmontar.
- home: este es el directorio que almacena los datos de cada usuario excepto root, que tiene su propio directorio.
- root: este directorio es donde vive root, el todopoderoso, aqui estan su directorio Documents o Downloads.
- lib/lib32/lib64/libx32: estos directorios almacenan las librerias necesarias para que los binarios de /bin y /sbin funcionen correctamente al iniciar el sistema operativo.
- etc: directorio conocido como etcetera o etsy, aqui se almacenan los archivos de configuracion del sistema.
- opt: este directorio se suele utilizar para almacenar el software agregado por el usuario.
- usr: en este caso, originalmente el directorio era usado para almacenar archivos binarios y las librerias necesarias para su uso una vez que el sistema operativo estaba enendido. Desde la salida de Ubuntu 19.04, la diferencia entre /usr/bin y /bin esta desapareciendo ya que estas distros requieren tanto de binarios almacenados en /bin como /usr/bin. Asimismo, los directorios /lib y /usr/lib tambien tienden a almacenar los mismos datos.
- var: este directorio incluye los ficheros en los que el sistema operativo escribe datos durante el curso de sus operaciones, un ejemplo serian los logs.
- tmp: es este directorio se almacenan los ficheros temporales, que seguramente sean borrados al reiniciar el sistema operativo.

