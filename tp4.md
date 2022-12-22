---
title: "TP 4 : Communication série"
nav_order: 24
schema: true
---

# TP 4 : Communication série

{: .objectiv }
Afficher un message de debug sur la console série

1. Pour la communication série, il faut utiliser [`Serial`](https://www.arduino.cc/reference/en/language/functions/communication/serial/){:target="_blank"} :
  - `Serial.begin()` permettant de configurer la vitesse de communication dans la fonction `setup()`
  - `Serial.print()` et `Serial.println()` pour afficher des infos depuis l'emplacement voulu dans le code. <br> Exemple :

```c
void setup() {
  Serial.begin(9600);
  Serial.flush();
}

void loop() {
  Serial.println("Hello world !!");
  delay(100); // attente de 100 millisecondes pour éviter de flooder la console
}
```

{:style="counter-reset:none"}
2. Coté IDE Arduino, utiliser le moniteur série en cliquant sur le bouton suivant :
![bouton](resources/tp4-bouton.jpg)

3. Dans la console qui vient de s'ouvrir, sélectionner la vitesse dans le menu déroulant en bas à droite de la fenêtre en adéquation avec la vitesse définie dans le sketch via l'instruction `Serial.begin(9600);` où `9600` est la vitesse en _baud_ par seconde.
![console](resources/tp4-serial.jpg)

----
[⬅️ TP 3](tp3.md) :: [TP 5 ➡️](tp5.md)
