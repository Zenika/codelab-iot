---
title: "TP 5 Bis : Code réponse"
nav_exclude: true
schema: true
---

# TP 5 Bis : Code

```c
// state of the traffic light
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
//  pinMode(SENSOR, INPUT);
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

void state_machine(uint8_t sensor) {
  switch (state)
  {
    case STOP:
      stop();
      delay(4000);
      state = GO;
      break;
    case CAUTION:
      caution();
      delay(2000);
      state = STOP;
      break;
    case GO:
      if (sensor == 1) {
        state = CAUTION;
      } else {
        go();
        delay(7000);
        state = CAUTION;
      }
      break;
  }
}

void loop() {
  uint8_t value = analogRead(SENSOR);
  Serial.println(value);
  uint8_t sensorValue = 0; //(value > 1800) ? 1 : 0;
  Serial.println(sensorValue);
  state_machine(sensorValue);
}
```
