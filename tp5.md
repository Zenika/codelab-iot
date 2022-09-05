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

Coté code, les instructions de contrôle d'exécution habituel sont disponibles : `if`, `then`, `else`...

TODO mettre en spoiler le code
```c
void setup() {
  Serial.begin(9600);
  Serial.flush();
  pinMode(A0, INPUT);
  pinMode(D1, OUTPUT);
}

void loop() {
  double ldr = analogRead(A0);
  Serial.print(String("valeur : "));
  Serial.println(ldr);
  if (ldr < 350) {
    digitalWrite(D1, HIGH);
  } else {
    digitalWrite(D1, LOW);
  }
  delay(50);
}
```

----
[⬅️ TP 4](tp4.md) :: [TP 6 ➡️](tp6.md)
