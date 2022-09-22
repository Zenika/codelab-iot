---
title: "TP 5 : Code réponse"
nav_exclude: true
schema: true
---

# TP 5 : Code

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
  if (ldr < 25) {  // 25 dépend de la luminosité ambiante, à ajuster en fonction des valeurs lues avec et sans ombre
    digitalWrite(D1, HIGH);
  } else {
    digitalWrite(D1, LOW);
  }
  delay(100);
}
```
