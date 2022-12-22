---
title: "TP 4 : Code réponse"
nav_exclude: true
schema: true
---

# TP 4 : Code

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
