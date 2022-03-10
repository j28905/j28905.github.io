---
layout: single
title: GCP BigTable
excerpt: "Empieza a usar BigTable"
date: 2022-03-10
classes: wide
header:
  teaser: /assets/images/BigTable/GCPLogo.png
  teaser_home_page: true
categories:
  - GCP
tags:  
  - GCP
---

![](/assets/images/BigTable/BigTableLogo.png)
<br>
Aqui vamos a empezar a usar Big Table para ello necesitaremos tener una cuenta de google con la facturacion activada y un proyecto en la Google Cloud Platform (https://console.cloud.google.com/home/dashboard).
##  Introduccion

En este tutorial se muestra como se utiliza BigTable, tanto desde la GCP como desde el GoogleSDK. 


## Instalar GoogleSDK:

Descargar el ejecutable desde:

	https://dl.google.com/dl/cloudsdk/channels/rapid/GoogleCloudSDKInstaller.exe

Y añadir la variable de entorno GOOGLE_APPLICATION_CREDENTIALS apuntando al fichero .json con las credenciales.

## Usar la GCP

Lo primero es seleccionar el projecto que usaremos, para ello en la parte superior desplegamos la ventana con los projectos creados.

![](/assets/images/BigTable/bt1.png)

Se desplegara la siguiente ventana:

![](/assets/images/BigTable/bt2.png)

En la ventana anterior se puede ver tanto el nombre como la id de los projectos que tenemos. Es importante si tenemos projectos con nombres que seran distintos al id, que el id es el termino al que se hara referencia al hablar de el projecto o el project_id.

Una vez el proyecto esta seleccionado, vamos al producto BigTable.

![](/assets/images/BigTable/bt3.png)

Desde BigTable, deberemos crear una instancia.

![](/assets/images/BigTable/bt4.png)

Simplemente al hacer click en el boton de crear instancia se abrira el siguiente desplegable:

![](/assets/images/BigTable/bt5.png)

En el cual se deberá aportar un nombre, en este caso "instanciaprueba1". Al igual, tendremos que seleccionar un tipo de almacenamiento, una ubicacion para nuestra instancia y el numero de nodos que tendra.
A continuacion se muestra un ejemplo para un cluster de almacenamiento SSD y un solo nodo ubicado en Belgica, esto es bien caro ~$468/mes solo por tenerla...

![](/assets/images/BigTable/bt6.png)
![](/assets/images/BigTable/bt7.png) 

Y al presionar crear, estaria creada nuestra primera instancia de BigTable.

Lo siguiente seria crear una tabla, para ello en la parte izquierda de la ventana de BigTable seleccionamos Tablas.
Y a continuacion, presionamos en crear tabla.

![](/assets/images/BigTable/bt8.png)

Le damos un nombre a la tabla asi como, al menos, una familia de columnas y decidiremos la politica de recoleccion de elementos no utilizados. En este caso la familia de columnas se ha llamado "columnFamily" y se ha decidido no recolectar elementos no utilizados.

![](/assets/images/BigTable/bt9.png)


## Usar la GoogleSDK

A continuacion, usaremos la SDK de Google para realizar los mismos pasos que se realizaron con la GCP. Los siguientes comandos se pueden ejecutar sobre el GoogleSDK o en la propia shell de la GCP.

Para crear una instancia utilizaremos:

```bash

gcloud bigtable instances create <nombreDeLaInstancia> --cluster=<nombreDelCluster> --cluster-zone=<region>  \
    --cluster-num-nodes=<numeroDeNodos>    --display-name=<nombreDeLaInstancia>

``` 

Un ejemplo podria ser:
```bash

gcloud bigtable instances create instanciaprueba1 --cluster=instanciaprueba1 --cluster-zone=europe-west1-c   \
    --cluster-num-nodes=1 --display-name=instanciaprueba1

```

Lo siguiente sera crear una tabla y una familia de columnas.

```bash

cbt -instance <nombreInstancia> createtable <nombreTabla>
cbt -instance  <nombreInstancia> createfamily <nombreTabla> <nombreFamiliaColumnas>

```
Un ejemplo de los comandos anteriores:

```bash

cbt -instance instanciaprueba1 createtable my-table
cbt -instance instanciaprueba1 createfamily my-table columnFamily

```


## Importar un archivo .csv



Esta por terminar no juzgar

