---
title: "TP 9 📟 Appel HTTP"
nav_order: 30
schema: true
---

# TP 9 : Faire un appel HTTP

{: .objectiv }
Appeler un endpoint en HTTP sur [Mockbin.org](https://mockbin.org/){:target="_blank"} depuis l'ESP

[Mockbin.org](https://mockbin.org/){:target="_blank"}  est un service de test de endpoint sur lequel il est possible de créer des urls customs, des paramètres attendus ainsi qu'une réponse personnalisée... Le site fournit également une page [d'historique des appels via l'interface pour retrouver son appel]({{ site.endpoint.https }}/log){:target="_blank"}.

![historique](resources/tp10-historique.jpg)

## Appel en HTTP
Parcourir les exemples disponibles dans l'IDE sous _File_ > _Examples_ > _ESP8266HTTPClient_ pour implémenter un sketch appelant l'url [{{ site.endpoint.https }}]({{ site.endpoint.https }}){:target="_blank"} en GET.

[{{ site.code-spoiler }}](tp9_code.md#appel-en-http)

## Appel en HTTPs

Pour aller plus loin, réaliser un sketch effectuant un appel en HTTPs sur le même endpoint.

----
[{{ site.code-spoiler }}](tp9_code.md#appel-en-https)

----
[⬅️ TP 8](tp8.md) :: [Fin 🎉 ➡️](z-fin.md)
