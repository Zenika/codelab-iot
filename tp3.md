---
title: "TP 3 : LED externe"
nav_order: 5
schema: true
---

# TP 3 : LED externe

{: .objectiv }
Câbler une LED et la faire clignoter

{: .warning }
⚠️ Avant toutes manipulations de composants, il faut **débrancher** le câble USB.

Une LED se branche toujours avec une résistance en série pour la protéger, ici, nous utilisons une valeur de 220 Ω (ohms). Celle ci est branchée sur la broche `D1`.
Le schema électronique pour faire brancher la led est le suivant :

![schema-tp3](resources/tp3-schema.jpg)

Voici le câblage correspondant :

![montage-tp3](resources/tp3-montage.jpg)

Reprendre le sketch du TP2 pour utiliser la sortie `D1` au lieu de `LED_BUILTIN` :

TODO mettre en spoiler le code
```c
void setup() {
  pinMode(D1, OUTPUT);
}

void loop() {
  digitalWrite(D1, HIGH);
  delay(1000);
  digitalWrite(D1, LOW);
  delay(500);
}
```

{: .tip }
Si la LED ne clignote pas, commencer par tester en l'inversant, elle ne grillera pas ;-) (tout de suite)

----
[⬅️ TP 2](tp2.md) :: [TP 4 ➡️](tp4.md)
