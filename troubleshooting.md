---
title: 🩺 Troubleshooting
nav_order: 20
schema: true
---

# 🩺 Troubleshooting

## Vérification du fonctionnement de la LED

Si la LED ne clignote pas, commencer par tester en l'inversant, elle ne grillera pas ;-) (tout de suite)

Le montage suivant permet d'allumer de manière continue la LED sans écrire un sketch

![montage-led](resources/trouble-montage-led.jpg)

## Erreur d'upload

En cas d'erreur d'upload, il faut ré-essayer.

Vérifier également que le cable USB de l'ESP8266 est bien connecté à l'ordinateur ! ;)

Si le problème persiste, appuyer sur le bouton `RESET` situé en haut à droite du port USB.

Voir également cet article : [Arduino - Déterminer qui bloque un port](https://support.arduino.cc/hc/en-us/articles/4407830972050-Find-and-stop-process-blocking-a-port)

## `Permission denied` sous Linux

- `avrdude: ser_open(): can't open device <port>: Permission denied (Linux)` : vérifier que l'utilisateur courant est bien dans le groupe `dialout` via la commande `id` :
```
uid=1000(guillaume) gid=1000(guillaume) groups=1000(guillaume), ... 20(dialout)
```
Si ce n'est pas le cas, ajouter le user courant :
```
sudo usermod -a -G dialout $USER
```
cf : [Arduino - Ajustements des droits sous Linux](https://support.arduino.cc/hc/en-us/articles/360016495679-Fix-port-access-on-Linux)

- Sur les distributions Ubuntu récente, le programme `brltty` bloque le port série et empêche l'upload ==> Le désinstaller via la commande : `sudo apt remove -y brltty`.

## Menu "Port" grisé ou absent sous Windows

Installer le [driver ch340](https://learn.sparkfun.com/tutorials/how-to-install-ch340-drivers/all) pour reconnaitre l'ESP via son port série émulé sur USB.

## Menu "Port" grisé ou absent sous MacOS

Logiquement, aucun driver supplémentaire n'est requis sous MacOS à partir de la version 10.14 (Mojave). Toutefois, si vous rencontrez un problème vous pouvez installer le [driver ch340](https://www.wemos.cc/en/latest/ch340_driver.html).

## Pas d'affichage sur le moniteur série

Bien vérifier la correspondance entre l'instruction d'initialisation du canal de communication via la fonction  `Serial.begin(9600)` où `9600` est la vitesse en _baud/s_ et celle choisie dans la liste déroulante en bas à droite du moniteur correspondant.

![serial](resources/tp4-serial.jpg)
