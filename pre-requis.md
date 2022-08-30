# Installations de l'IDE

{: .tip }
ℹ️ Pendant les phases de téléchargement, vous pouvez [réaliser le TP 1](tp1.md)

1. Installer Arduino IDE : https://www.arduino.cc/en/software
2. Ajouter les cartes ESP8266 à l'IDE. La [documentation officielle du projet est très riche](https://arduino-esp8266.readthedocs.io/en/latest/).
  - Démarrer _Arduino IDE_ et aller dans _Preferences_;
  - Dans le champs _Additionnals Boards Managers URLs_ mettre `https://arduino.esp8266.com/stable/package_esp8266com_index.json`. S'il y a déjà une URL, utiliser la virgule en tant que séparateur;
  ![preferences](resources/arduino-ide-preferences.jpg)
  - Aller dans _Tools_ > _Board: .*_ > _Boards Manager..._
  ![menu](resources/arduino-ide-board-menu.jpg)
  - Dans le champs de recherche en haut de la fenêtre, saisir `esp8266`, sélectionner le premier résultat puis cliquer sur le bouton _install_ (ℹ️ continuer sur [le TP 1](tp1.md) en attendant)
  ![install](resources/arduino-ide-board-install.jpg)
  - Terminer en cliquant sur le bouton _close_

----
[⬅️ Composants](composants.md) :: [TP 1 ➡️ ](tp1.md)
