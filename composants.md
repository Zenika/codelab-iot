---
title: 🔎 Composants
nav_order: 21
schema: true
---

# 🔎 Identification et caractéristiques de chaque composant

## Micro-contrôleur

Le micro-contrôleur utilisé est un WeMos D1 mini qui intègre sur la même circuit imprimé :
  - Processeur ESP8266EX : 32-bit CPU @ 80 MHz
  - Flash Size 4: MB
  - Wi-Fi : IEEE 802.11 b/g/n

![Pinout](resources/ESP8266-12E-Wemos-D1-Mini-pinout.jpg)

## Breadboard

Une _breadboard_ ou plaque d'essai permet de brancher des composants électroniques entre eux sans les souder. Très utile pour prototyper.

Photos :
![Breadboard](resources/breadboard.jpg)

La connection entre les différents trous est par colonne et par ligne. Sur le diagramme ci-dessous, les lignes noires représentent les connections inter-trous.

![Breadboard wiring](resources/breadboard-wiring.jpg)

Explications : [magpi.raspberrypi.com](https://magpi.raspberrypi.com/articles/breadboard-tutorial), [learn.adafruit.com](https://learn.adafruit.com/breadboards-for-beginners)

## LED

![Pinout](resources/led-pinout.jpg)

Patte la plus longue = Anode (+) / Patte la plus courte = Cathode (-)

Le méplat est toujours du côté Cathode (-)

Explications : [circuits-diy](https://www.circuits-diy.com/how-to-blink-led-using-an-arduino/)

## LDR

La [LDR](https://en.wikipedia.org/wiki/Photoresistor), ou photo-résistance, est une resistance dont la valeur varie en fonction de la lumière : plus il fait sombre, plus sa résistance est élevée (> 1MΩ), moins il y a de courant qui passe, plus la tension aux bornes du composant est élevée.
Ce composant n'est pas polarisé, c'est à dire qu'il n'y a pas de broche positive (+) et moins (-).

![LCD / photorésistance](resources/photoresistor.jpg)


## Résistance

Mnémonic pour se rappeler des couleurs :
```
Ne Mangez Rien Ou Jeunez, Voila Bien Votre Grande Bêtise
⚫   🟤     🔴  🟠   🟡    🟣    🔵    🟢   🔘     ⚪
1     2     3    4    5     6     7     8    9      0
```

Voir [ce site pour le calcul des valeurs de résistances](https://www.electronique-radioamateur.fr/elec/composants/resistance-code-couleurs.php).

![resistance](resources/resistors.jpg)

----
Sources : [microcontrollerslab](https://microcontrollerslab.com), [element14](https://element14.com), [raspberrypi](https://magpi.raspberrypi.com), [circuits-diy](https://www.circuits-diy.com)

----
[⬅️  Accueil](README.md) :: [Pré-requis ➡️](pre-requis.md)
