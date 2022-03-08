---
layout: single
title: Citrix en Linux
excerpt: "Intalar Citrix en Ubuntu 20.04"
date: 2022-03-08
classes: wide
header:
  teaser: /assets/images/citrix.png
  teaser_home_page: true
categories:
  - Apps
  - Teletrabajo
tags:  
  - Apps
  - Teletrabajo
---

![](/assets/images/citrix.png)
<br>
Guia de instalacion de Citrix en Ubuntu 20.04 (se requiere Mozilla Firefox)
## Primer paso
Descargar los correspondientes paquetes .deb de Citrix Workspace App (Full Package(Self-Service Support) y USB Support Packages de la url:
```url
 https://www.citrix.com/es-es/downloads/workspace-app/
```

## Segundo paso
Instalar los paquetes con los permisos correspondientes
```bash
sudo dpkg -i icaclient*
sudo dpkg -i ctxusb*
```
## Tercer paso
Crear accesos directos a los certificados CA
```bash
sudo ln -s /usr/share/ca-certificates/mozilla/* /opt/Citrix/ICAClient/keystore/cacerts/
sudo c_rehash /opt/Citrix/ICAClient/keystore/cacerts/
sudo ln -s /opt/Citrix/ICAClient/npica.so /usr/lib/firefox-addons/plugins/npica.so
```
## Cuarto paso
 Para utilizar Chrome
```bash
sudo xdg-mime default wfica.desktop application/x-ica
```
## Quinto paso
Importar el certificado DigiCert TLS RSA SHA256 2020 CA1, para ello intalamos wget, en caso de que no este instalado
```bash
sudo apt-get install wget -y
wget https://digicert.tbs-certificats.com/DigiCertTLSRSASHA2562020CA1.crt
```
## Sexto paso
Copiar el certificado en el directorio 
```bash
sudo cp *.crt /opt/Citrix/ICAClient/keystore/cacerts/
```
  
