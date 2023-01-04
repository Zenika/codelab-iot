---
title: "TP 2 : Blink World"
nav_order: 22
schema: true
---

# TP 2 : Utilisation de l'IDE & Blink World

{: .objectiv }
Configuration de l'environnement Arduino IDE et écrire un _sketch_ pour faire clignoter la led interne.

{: .caution }
⚠️ Nous déclinons toute responsabilité en cas de mauvais branchement ou mauvaise manipulation.

1. Assurez vous qu'aucun fil n'est branché sur la breadboard, uniquement le micro-contrôleur. Brancher le câble USB sur la carte électronique à l'un des ports USB de votre machine. Utilisez si nécessaire l'adaptateur USB-C.
2. Dans Arduino IDE, ouvrir le menu déroulant "Select Board", sélectionner le port de communication associé à votre carte : `/dev/cu.usbserial-*` sous GNU Linux ou macOS, `COM` sous windows. Il est probable qu'il faille essayer tous les ports pour trouver la carte...
 ![port](resources/tp2-board-port.jpg)
3. Dans la fenêtre qui s'est ouverte, saisir `wemos` dans le champs de recherche puis sélectionner _LOLIN(WEMOS) D1 R2 & mini_ puis valider
 ![select](resources/tp2-board-select.jpg)

4. Créer un premier sketch faisant clignoter la led intégrée en utilisant un snippet de code existant : aller dans _File_ > _Examples_ > _ESP8266_ > _Blink_. Le _sketch_ est le même que dans le TP précédent.
![port](resources/tp2-blink.jpg)
5. Lancer la compilation et l'upload du _sketch_ via le bouton "Flèche" surligné en rouge. Le log s'affiche en base de l'écran. ![port](resources/tp2-upload.jpg)
6. Lorsque le flashage est terminé, la log est de la forme suivante : ![log](resources/tp2-upload-fin.jpg)


{: .tip }
En cas d'erreur d'upload, consulter [la page d'aide des problèmes fréquents](troubleshooting.md#erreur-dupload)

{:style="counter-reset:none"}
7. Admirer la led clignoter 🎉 ![clignote](resources/tp2-led-interne-clignote.gif)

----
[⬅️ TP 1](tp1.md) :: [TP 3 ➡️](tp3.md)
