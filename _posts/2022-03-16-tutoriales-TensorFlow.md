---
layout: single
title: TensorFlow Instalacion
excerpt: "Instala todo lo necesario para usar TensorFlow en tu PC"
date: 2022-03-16
classes: wide
header:
  teaser: /assets/images/tensorflow/TFLogo.png
  teaser_home_page: true
categories:
  - TensorFlow
  - Python
tags:  
  - TensorFlow
  - Python
---

![](/assets/images/tensorflow/TFLogo.png)


En esta pagina se explicara que software es necesario para empezar a desarrollar redes neuronales (NN).

### Paso primero - Instalar Anaconda

Necesitaremos instalar python, para ello instalaremos Anaconda concretamente instalaremos la version de Anaconda3-2019.07 que incluye la version de Python 3.7. Nos podemos descargar dicha version desde:

```bash
https://repo.anaconda.com/archive
```
podemos instalarlo para todos los usuarios o solo para el nuestro. 


### Paso segundo - Instalar Visual Studio Community

Necesitamos instalar Visual Studio Community con la workload (carga de trabajo) Desktop development with C++ ya que, TensorFlow depende den C++ Build Tools y CUDA requiere de Visual Studio.
Podemos descargar VS Community desde:

```bash
https://visualstudio.microsoft.com/vs/community/
```

### Paso tercero - Instalar CUDA y CUDNN

Este paso es opcional pero muy recomendable si tenemos alguna tarjeta grafica Nvidia. Una vez instalados Anaconda y VS Community, descargamos CUDA y CUDNN desde los siguientes enlaces:

```bash
https://developer.nvidia.com/cuda-10.1-download-archive-base?target_os=Windows&target_arch=x86_64&target_version=10&target_type=exelocal
```

En este caso descargaremos CUDA 10.1 y el tipo de instalador sera local, ya que trabajaremos en local.
Una vez descargado, haremos doble click, le daremos una ruta valida para descomprimir y despues instalaremos la version Express.

```bash 
https://developer.nvidia.com/rdp/cudnn-archive
```

Por compatibilidad instalaremos CUDNN 7.6 para CUDA 10.1. Para poder descargarnos este archivo, deberemos estar registrados en Nvidia. Una vez descargado el archivo llamado: cudnn-10.1-windows10-x64-v7.6.5.32.zip lo descompriremos y copiaremos cada archivo en la carpeta donde esten los archivos de CUDA. La iamgen siguiente muestra los dos directorios que se han de fusionar;
![](/assets/images/tensorflow/CUDAfiles.png)<br> 
por lo tanto, tendremos que añadir los ficheros en los directorios bin, include y lib recien descargados a los directorios bin,include y lib de NVIDIA GPU Computing Toolkit .

### Paso cuarto - Instalar Protoc

Es necesario instalar esto ya que los graficos de TensorFlow son representados en un formato llamado protocol buffer( a veces protobuf) y Protoc facilita trabajar con ellos.
Desde la siguiente web, podremos descargar Protoc. Existen 28 assets disponibles, aqui deberemos seleccionar el asset que sea para nuestro sistema operativo.
```bash 
https://github.com/protocolbuffers/protobuf/releases
```

Una vez descargado, lo deberemos extraer en el directorio que queramos, en este caso hemos usado un directorio por debajo de C: llamado additionalPackages. El siguiente paso sera añadir el directorio con los binarios al PATH, para ello abrimos las Variables de entorno desde las Propiedades del sistema y añadimos nuestra ruta al PATH.
![](/assets/images/tensorflow/varPATH.png)

### Paso quinto - Instalar TF Object detection

Para la instalacion de TensorFlow tendremos que usar el siguiente repositorio de github:

```bash
https://github.com/tensorflow/models
```

Una vez clonado, deberemos movernos hasta el directorio \models\research y ejecutar un par de comandos, mostrados a continuacion:

```bash
cd models\research
protoc object_detection\protos\*.protos --python_out=.
copy object_detection\packages\tf2\setup.py .
python -m pip install .
```

Con estos 5 pasos tendremos preparado nuestro entorno con todo lo necesario para trabajar con TensorFlow.




