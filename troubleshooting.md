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

## Pas d'affichage sur le moniteur série

Bien vérifier la correspondance entre l'instruction d'initialisation du canal de communication via la fonction  `Serial.begin(9600)` où `9600` est la vitesse en _baud/s_ et celle choisie dans la liste déroulante en bas à droite du moniteur correspondant.

![serial](resources/tp4-serial.jpg)
