---
layout: post
title: "Installation Seedbox Deluge + ftps"
description: "Installation d'une SeedBox avec Deluge et un serveur ftp avec ssl/tls"
category: ""
tags: [seedbox, xorhead, deluge, ssl,tls,ftp,ftps,torrent,ratio]
---
{% include JB/setup %}

# Installation de Deluge  

----------  

1. ### Création de l'utilisateur et des logs  
    adduser --disabled-password --system --home /var/lib/deluge --gecos "Deluge server" --group deluge
    touch /var/log/deluged.log
    touch /var/log/deluge-web.log
    
    $ chown deluge:deluge /var/log/deluge*

2. ###Installation des paquets

  apt-get update && apt-get upgrade  
  apt-get install deluge-common deluged deluge-web  

3. ###Edition du fichier de configuration du Daemon  
`nano /etc/default/deluge-daemon`  

  DELUGED_USER="deluge"  
  RUN_AT_STARTUP="YES"  

`nano /etc/init.d/deluge-daemon`


4. #### Add permissions:

  chmod 755 /etc/init.d/deluge-daemon  
  update-rc.d deluge-daemon defaults  

5. ### Accès à l'interface  
http://xxx.xxx.xxx.xxx:8112 avec le mot de passe par défaut: **deluge**  

