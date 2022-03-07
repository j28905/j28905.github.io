---
layout: single
title: Pagina Web
excerpt: "Crear una pagina web como esta en 5 minutos"
date: 2022-03-07
classes: wide
header:
  teaser: /assets/images/avatar.png
  teaser_home_page: true
categories:
  - Paginas Web
  - Creacion de contenidos
tags:  
  - Paginas Web
  - Creacion de contenidos
---

![](/assets/images/avatar.png)
<br>
Crea una pagina como esta en 5 min.
## Primer paso
Creamos la carpeta webserver y nos moveremos a ella para trabajar desde ahí.
```bash
┌──(kali㉿kali)-[~/]
└─$ mkdir webserver
┌──(kali㉿kali)-[~/]
└─$ cd webserver
┌──(kali㉿kali)-[~/webserver]
└─$ 
```
Clonar el repositorio desde github.
```bash
┌──(kali㉿kali)-[~/webserver]
└─$ git clone https://github.com/j28905/j28905.github.io.git
Cloning into 'j28905.github.io'...
remote: Enumerating objects: 3096, done.
remote: Counting objects: 100% (33/33), done.
remote: Compressing objects: 100% (22/22), done.
remote: Total 3096 (delta 10), reused 26 (delta 7), pack-reused 3063
Receiving objects: 100% (3096/3096), 76.55 MiB | 3.73 MiB/s, done.
Resolving deltas: 100% (763/763), done.
```

## Segundo paso

Movernos al directorio clonado.

```sh
┌──(kali㉿kali)-[~/webserver]
└─$ cd j28905.github.io
┌──(kali㉿kali)-[~/webserver/j28905.github.io]
└─$ 
 ```
Una vez en el directori correspondiente, instalar bundle.
```zsh                                                                   
┌──(kali㉿kali)-[~/webserver/j28905.github.io]
└─$ bundle install                                                       1 ⨯
Warning: the running version of Bundler (2.2.5) is older than the version that created the lockfile (2.3.8). We suggest you to upgrade to the version that created the lockfile by running `gem install bundler:2.3.8`.                
Fetching gem metadata from https://rubygems.org/.........                    
Following files may not be writable, so sudo is needed:
  /usr/local/bin                                                             
  /var/lib/gems/2.7.0                                                        
  /var/lib/gems/2.7.0/build_info                                             
  /var/lib/gems/2.7.0/cache                                                  
  /var/lib/gems/2.7.0/doc                                                    
  /var/lib/gems/2.7.0/extensions                                             
  /var/lib/gems/2.7.0/gems                                                   
  /var/lib/gems/2.7.0/plugins                                                
  /var/lib/gems/2.7.0/specifications                                         
Fetching multi_json 1.15.0
Fetching concurrent-ruby 1.1.8


Your user account isnt allowed to install to the system RubyGems.
  You can cancel this installation and run:

      bundle config set --local path 'vendor/bundle'
      bundle install

  to install the gems into ./vendor/bundle/, or you can enter your password
  and install the bundled gems to RubyGems using sudo.

  Password: 
```
Se introduce la contraseña.
Instalar seguidamente gem.

```bash
┌──(kali㉿kali)-[~/webserver/j28905.github.io]
└─$ sudo gem install jekyll                                            127 ⨯
[sudo] password for kali: 
```


## Ultimo paso

Ejecutar el servicio de web jekyll.

```bash
──(kali㉿kali)-[~/webserver/j28905.github.io]
└─$ bundle exec jekyll serve                                             1 ⨯
Configuration file: /home/kali/webserver/j28905.github.io/_config.yml
            Source: /home/kali/webserver/j28905.github.io
       Destination: /home/kali/webserver/j28905.github.io/_site
 Incremental build: disabled. Enable with --incremental
      Generating... 
      Remote Theme: Using theme mmistakes/minimal-mistakes
       Jekyll Feed: Generating feed for posts
   GitHub Metadata: No GitHub API authentication could be found. Some fields may be missing or have incorrect data.                                       
                    done in 28.925 seconds.
/var/lib/gems/2.7.0/gems/pathutil-0.16.2/lib/pathutil.rb:502: warning: Using the last argument as keyword parameters is deprecated
 Auto-regeneration: enabled for '/home/kali/webserver/j28905.github.io'
    Server address: http://127.0.0.1:4000
  Server running... press ctrl-c to stop.
```
Y ya tendrias tu pagina web funcionando.
