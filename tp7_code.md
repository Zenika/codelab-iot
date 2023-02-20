---
title: "Réponse : faire clignoter un feu tricolore 🚦"
nav_exclude: true
schema: true
---

# Réponse : faire clignoter un feu tricolore 🚦

```c
#define STOP 0
#define CAUTION 1
#define GO 2

// pinout
#define SENSOR A0
#define LED_RED D6
#define LED_ORANGE D5
#define LED_GREEN D0

uint8_t state = STOP;

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

#define SHORT_DURATION 100
#define THRESHOLD 800 // ajuster le seuil en fonction des conditions lumineuses
void wait_if_no_action(uint16_t duration) {
  Serial.print("Sensor values: ");
  for (uint8_t i = 0; i < (duration / SHORT_DURATION); i++) {
    uint8_t light = analogRead(SENSOR);
    Serial.print(light);
    Serial.print(" ");
    if (light < THRESHOLD) {
      Serial.println("object detected !!");
      return;
    }
    delay(SHORT_DURATION);
  }
  Serial.println();
}

void loop() {
  switch (state)
  {
    case STOP:
      stop();
      delay(5000);
      state = GO;
      break;
    case CAUTION:
      caution();
      delay(2000);
      state = STOP;
      break;
    case GO:
      go();
      wait_if_no_action(7000);      
      state = CAUTION;
      break;
  }
}
```

----
[⬅️ Retour à l'énoncé](tp7.md)
