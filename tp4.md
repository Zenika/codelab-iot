---
title: "TP 4 : Capteur de lumière"
nav_order: 6
schema: true
---

# TP 4 : Capteur de lumière

{: .objectiv }
Brancher le capteur de lumière et afficher sa valeur sur la console série.

{: .warning }
⚠️ Avant toutes manipulations de composants, il faut **débrancher** le câble USB.

La [LDR](https://en.wikipedia.org/wiki/Photoresistor), ou photo-résistance, est une resistance dont la valeur varie en fonction de la lumière : plus il fait sombre, plus sa résistance est élevée (> 1MΩ), moins il y a de courant qui passe, plus la tension aux bornes du composant est élevée.

Nous utiliserons un pont diviseur de tension afin de lire la tension aux bornes de la résistance via la broche `A0` de l'ESP et envoyer la valeur lue sur la console série.

Le schema électronique est le suivant :

![schema-tp4](resources/tp4-schema.jpg)

Voici le câblage correspondant :

![montage-tp4](resources/tp4-montage.jpg)

Pour la communication série, il faut utiliser [`Serial`](https://www.arduino.cc/reference/en/language/functions/communication/serial/) :
  - `Serial.begin()` permettant de configurer la vitesse de communication dans la fonction `setup()`
  - `Serial.print()` et `Serial.println()` pour afficher des infos où voulu dans le code.

Exemple :
```c
void setup() {
  Serial.begin(9600);
  Serial.flush();
}

void loop() {
  Serial.println("Hello devfest !!");
  delay(100);
}
```

Coté IDE Arduino, utiliser le moniteur série en cliquant sur le bouton suivant :
![bouton](resources/tp4-bouton.jpg)

Dans la console qui vient de s'ouvrir, sélectionner la vitesse dans le menu déroulant en bas à droite de la fenêtre en adéquation avec la vitesse définie dans le sketch via l'instruction `Serial.begin(9600);` où `9600` est la vitesse en _baud_ par seconde.

![console](resources/tp4-serial.jpg)

{: .tip }
L'attente de 100 millisecondes ajoutée en fin de boucle via l'instruction [`delay()`](https://www.arduino.cc/reference/en/language/functions/time/delay/) évite de flooder la console.

L'API à utiliser pour mesurer la tension aux bornes de la photo-résistance est [`analogRead()`](https://www.arduino.cc/reference/en/language/functions/analog-io/analogread/).

TODO mettre en spoiler le code
```c
void setup() {
  Serial.begin(9600);
  Serial.flush();
  pinMode(A0, INPUT);
}

void loop() {
  double ldr = analogRead(A0);
  Serial.print("valeur : ");
  Serial.println(ldr);
  delay(100);
}
```

----
[⬅️ TP 3](tp3.md) :: [TP 5 ➡️](tp5.md)
