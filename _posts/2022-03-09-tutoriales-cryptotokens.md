---
layout: single
title: Crypto Tokens
excerpt: "Convertirte en un autento cryptolai, creando tu propio crypto token"
date: 2022-03-09
classes: wide
header:
  teaser: /assets/images/prycto.png
  teaser_home_page: true
categories:
  - Cryptobros
  - Creacion de contenidos
tags:  
  - Cryptobros
  - Creacion de contenidos
---

![](/assets/images/prycto.png)
<br>
Aqui crearemos un token de la conocida crypto Solana, elegimos Solana porque el tiempo entre las transacciones es muy pequeño.
Para seguir el tutorial se necesita acceder a un sistema Linux donde instalar el software, asi como 10€ aproximadamente para no andar cortos de cryptos(SOL).

## Conseguir una Maquina Virtual (MV)

Conseguimos una MV desde nuestro proveedor cloud preferido, aqui se uso Linode.com.
Linode.com ofrece $100 gratuitos al darte de alta y para lo que vamos a utilizar nos sirve una maquina con CPU compartida de solo $5 al mes, por lo que tendremos 20 meses para usarlos.

Lo mejor seria usar un OS como Ubuntu 18.04 o 20.04.

## Instalar wallet de Solana

Lo primero sera instalar la wallet de Solana en nuestra MV, para ello nos conectamos por ssh:

```bash
ssh root@<MV_ip>
```
e instalamos la wallet:

```bash
sh -c "$(curl -sSfL https://release.solana.com/v1.8.5/install)"
```

Para asegurarnos de que los PATHs y dependencias se reconfiguran, reiniciamos la conexion ssh.
Una vez reiniciada, ejecutamos:

```bash
solana-keygen new 
```

para crear una nueva wallet. Al terminar este comando nos mostrara nuestra clave publica, la cual deberemos guardar.
A continuacion podemos ejecutar:

```bash 
solana balance
```

y nos devolvera 0 SOL, ya que se acaba de crear.

## Instalar Rust y dependencias

Lo siguiente sera instalar Rust:

```bash
curl https://sh.rustup.rs -sSf | sh 
```

 y las librerias necesarias para que todo funcione:

```bash
sudo apt install libudev-dev

sudo apt install libssl-dev pkg-config

sudo apt install build-essential -y
```


Una vez todo esta instalamos utilizamos la herramienta escrita en Rust cargo:

```bash
cargo install spl-token-cli
```
## Usando spl-token

Lo primero tendremos que crear nuestro token, esto nos costara un poco de Solana:

```bash
spl-token create-token
```

Nos guardaremos el id de nuestro token, de la linea que empieza con Creating token <token_id>
Y crearemos una cuenta donde guardar los tokens:

```bash
spl-token create-account <token_id> 
```

Igualmente, nos guardaremos nuestro account_id.
ya podemos generar tokens usando el comando mint:

```bash
spl-token mint <token_id> <cantidad> <account_id>
```

Podemos ver el balance de nuestra cuenta:

```bash
spl-token accounts
```

Para enviar los tokens a otra cuenta:
```bash
spl-token transfer --fund-recipient --allow-unfunded-recipient <account_id origen> <cantidad> <account_id destino>
```

Nota que se han añadido las flags de --fund-recipient y --allow-unfunded-recipient para poder transferir estos tokens a wallets de Solana que no tengan nuestros token aun.



