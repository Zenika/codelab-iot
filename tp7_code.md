---
title: "Réponse : faire clignoter un feu tricolore 🚦"
nav_exclude: true
schema: true
---

# Réponse : faire clignoter un feu tricolore 🚦

```c
// pinout
#define SENSOR A0
#define LED_RED D6
#define LED_ORANGE D5
#define LED_GREEN D0

 // ajuster le seuil en fonction des conditions lumineuses
#define AMBIENT_LIGHT_THRESHOLD 800

void setup() {
  Serial.begin(9600);
  Serial.flush();
  pinMode(SENSOR, INPUT);
  pinMode(LED_GREEN, OUTPUT);
  pinMode(LED_ORANGE, OUTPUT);
  pinMode(LED_RED, OUTPUT);
}

void go() {
  digitalWrite(LED_GREEN, HIGH);
  digitalWrite(LED_ORANGE, LOW);
  digitalWrite(LED_RED, LOW);
}

void caution() {
  digitalWrite(LED_GREEN, LOW);
  digitalWrite(LED_ORANGE, HIGH);
  digitalWrite(LED_RED, LOW);
}

void stop() {
  digitalWrite(LED_GREEN, LOW);
  digitalWrite(LED_ORANGE, LOW);
  digitalWrite(LED_RED, HIGH);
}

// attente vérifiant toutes les 100 ms qu'un objet est détecté
void wait_if_no_object_detected(uint16_t duration) {
  Serial.print("Sensor values: ");
  for (uint8_t i = 0; i < (duration / 100); i++) {
    uint8_t light = analogRead(SENSOR);
    Serial.print(light);
    Serial.print(" ");
    if (light < AMBIENT_LIGHT_THRESHOLD) {
      Serial.println("object detected !!");
      return;
    }
    delay(100);
  }
  Serial.println();
}

void loop() {
  go();
  wait_if_no_object_detected(7000);      

  stop();
  delay(5000);

  caution();
  delay(2000);
}
```

----
[⬅️ Retour à l'énoncé](tp7.md)
