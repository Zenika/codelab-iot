---
title: "TP 6 : Wifi"
nav_order: 9
schema: true
---

# TP 6 : Connecter l'ESP au Wifi

{: .objectiv }
Configurer le Wifi sur l'ESP puis afficher son adresse IP.

L'API pour configurer le WIFI est riche, le [quick start de la documentation](https://arduino-esp8266.readthedocs.io/en/latest/esp8266wifi/readme.html){:target="_blank"} fournit un exemple de sketch à mettre en oeuvre. Le Wifi à utiliser est soit celui de la cité des congrès soit votre 4G.

{: .tip }
Il n'est pas nécessaire de modifier le câblage des composants.

Ne pas oublier de configurer la vitesse de communication de la console série en adéquation avec l'instruction `Serial.begin(115200);`.

[{{ site.code-spoiler }}](tp6_code.md)

----
[⬅️ TP 5](tp5.md) :: [TP 7 ➡️](tp7.md)
