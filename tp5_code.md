---
title: "Réponse : Capteur de lumière"
nav_exclude: true
schema: true
---

# Réponse : Capteur de lumière

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
[⬅️ Retour à l'énoncé](tp5.md)
