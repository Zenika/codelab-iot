---
title: "TP 5 : LED + LDR"
nav_order: 7
schema: true
---

# TP 5 : Allumer la LED en fonction de la luminosité

{: .objectiv }
Allumer la LED si une ombre est détectée.

{: .warning }
⚠️ Avant toutes manipulations de composants, il faut **débrancher** le câble USB.

Le schema électronique est un mélange des 2 TPs précédents :
  - la LED + résistance sur le port `D1`
  - pont de résistances sur `A0`

![schema-tp5](resources/tp5-schema.jpg)

Voici le câblage correspondant :

![montage-tp5](resources/tp5-montage.jpg)

Coté code, les instructions de contrôle d'exécution habituelles sont disponibles : `if`, `then`, `else`...

[{{ site.code-spoiler }}](tp5_code.md)

----
[⬅️ TP 4](tp4.md) :: [TP 6 ➡️](tp6.md)
