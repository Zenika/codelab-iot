---
title: "TP 5 : Capteur de lumière"
nav_order: 8
schema: true
---

# TP 5 : Capteur de lumière

{: .objectiv }
Brancher le capteur de lumière et afficher sa valeur sur la console série.

1. La résistance de la [LDR](https://en.wikipedia.org/wiki/Photoresistor){:target="_blank"} varie en fonction de la lumière : plus il fait sombre, plus sa résistance est élevée (> 1MΩ), moins il y a de courant qui passe, plus la tension aux bornes du composant est élevée. <br> Nous utiliserons un pont diviseur de tension afin de lire la tension aux bornes de la résistance via la broche `A0` de l'ESP et envoyer la valeur lue sur la console série.

2. Le schéma électronique est le suivant :
![schema](resources/tp5-schema.jpg)

3. Voici le câblage correspondant :

{: .caution }
⚠️ Avant toutes manipulations de composants, il faut **débrancher** le câble USB.

![montage](resources/tp5-montage.jpg)

{:style="counter-reset:none"}
4. L'API à utiliser pour mesurer la tension aux bornes de la photo-résistance est [`analogRead()`](https://www.arduino.cc/reference/en/language/functions/analog-io/analogread/){:target="_blank"}.

----
[{{ site.code-spoiler }}](tp5_code.md)

----
[⬅️ TP 4](tp4.md) :: [TP 6 ➡️](tp6.md)
