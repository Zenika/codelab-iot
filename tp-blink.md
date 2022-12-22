---
title: "TP 2 : Blink World"
nav_order: 4
schema: true
---

# TP 2 : Utilisation de l'IDE & Blink World

{: .objectiv }
Configuration de l'environnement Arduino IDE et écrire un _sketch_ pour faire clignoter la led interne.

1. Dans Arduino IDE, aller dans le menu _Tools_ > _Board: .*_ >, sélectionner _ESP8266 Boards_ > _LOLIN(WEMOS) D1 R2 & mini_
 ![select](resources/arduino-ide-board-select.jpg)
2. Connecter l'ESP avec le câble USB
3. Sélectionner le port de communication via le menu _Tools_ > _Port_ > `/dev/cu.usbserial-*` sous GNU Linux ou macOS, `COM` sous windows
 ![port](resources/arduino-ide-board-port.jpg)
4. Créer un premier sketch faisant clignoter la led intégrée en utilisant un snippet de code existant : aller dans _File_ > _Examples_ > _ESP8266_ > _Blink_. Le _sketch_ est le même que dans le TP précédent.
![port](resources/tp-blink-example.jpg)
5. Lancer la compilation via le menu _Sketch_ > _Compile_ (ou le bouton "Check")![port](resources/tp-blink-compile.jpg)
6. Uploader le programme via le menu _Sketch_ > _Upload_ (ou le bouton "Flèche" surligné en rouge) ![port](resources/tp-blink-upload.jpg)
7. Admirer la led clignoter 🎉 ![clignote](resources/tp-blink-led-interne-clignote.gif)

----
[⬅️ TP 1](tp-simulation.md) :: [TP 3 ➡️](tp-led-ext.md)
