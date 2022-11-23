---
title: "TP 5 Bis : Code réponse"
nav_exclude: true
schema: true
---

# TP 5 Bis : Code

```c
void setup() {
  Serial.begin(9600);
  Serial.flush();
  pinMode(A0, INPUT);
  pinMode(D0, OUTPUT);
  pinMode(D5, OUTPUT);
  pinMode(D6, OUTPUT);
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
  value = analogRead(input);
  Serial.println(value);
  sensorValue = (value > 1800) ? 1 : 0;
  Serial.println(sensorValue);
  state_machine(sensorValue);
}
```
