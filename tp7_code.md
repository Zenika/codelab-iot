---
title: "Réponse : Capteur de distance"
nav_exclude: true
schema: true
---

# Réponse : Capteur de distance

## Mesure de distance

1. La documentation utilisée est celle ci : [https://randomnerdtutorials.com/esp8266-nodemcu-hc-sr04-ultrasonic-arduino/](https://randomnerdtutorials.com/esp8266-nodemcu-hc-sr04-ultrasonic-arduino/){:target="_blank"}

2. Le schéma est le suivant :

![schéma](resources/tp8.1-schema.jpg)

{:style="counter-reset:none"}
3. Le montage correspondant est :

![montage](resources/tp8.1-montage.jpg)

{:style="counter-reset:none"}
4. Voici le code du sketch :

```c
/*********
  Rui Santos
  Complete project details at https://RandomNerdTutorials.com/esp8266-nodemcu-hc-sr04-ultrasonic-arduino/

  Permission is hereby granted, free of charge, to any person obtaining a copy
  of this software and associated documentation files.

  The above copyright notice and this permission notice shall be included in all
  copies or substantial portions of the Software.
*********/

#define ECHO_PIN D1
#define TRIGGER_PIN D2

//define sound velocity in cm/uS
#define SOUND_VELOCITY 0.034

long duration;
float distance;

void setup() {
  Serial.begin(115200); // Starts the serial communication
  Serial.flush();
  pinMode(TRIGGER_PIN, OUTPUT); // Sets the TRIGGER_PIN as an Output
  pinMode(ECHO_PIN, INPUT); // Sets the ECHO_PIN as an Input
}

void loop() {
  // Clears the TRIGGER_PIN
  digitalWrite(TRIGGER_PIN, LOW);
  delayMicroseconds(2);
  // Sets the TRIGGER_PIN on HIGH state for 10 micro seconds
  digitalWrite(TRIGGER_PIN, HIGH);
  delayMicroseconds(10);
  digitalWrite(TRIGGER_PIN, LOW);

  // Reads the ECHO_PIN, returns the sound wave travel time in microseconds
  duration = pulseIn(ECHO_PIN, HIGH);

  // Calculate the distance
  distance = duration * SOUND_VELOCITY/2;

  // Prints the distance on the Serial Monitor
  Serial.print("Distance (cm): ");
  Serial.println(distance);

  delay(500);
}
```

{: .warning }
Ne pas oublier de changer la vitesse de communication en `baud` de la console série.

La sortie de console est alors :

![schema](resources/tp8.1-console.jpg)

----
[⬅️ Retour à l'énoncé](tp7.md)

## Indicateur de distance

1. Le schéma est le suivant :

![schéma](resources/tp8.2-schema.jpg)

{:style="counter-reset:none"}
2. Le montage correspondant est :

![montage](resources/tp8.2-montage.jpg)

{:style="counter-reset:none"}
3. Voici le code du sketch :

```c
/*********
  Rui Santos
  Complete project details at https://RandomNerdTutorials.com/esp8266-nodemcu-hc-sr04-ultrasonic-arduino/

  Permission is hereby granted, free of charge, to any person obtaining a copy
  of this software and associated documentation files.

  The above copyright notice and this permission notice shall be included in all
  copies or substantial portions of the Software.
*********/

#define LED_RED D6
#define LED_ORANGE D5
#define LED_GREEN D0

#define ECHO_PIN D1
#define TRIGGER_PIN D2

//define sound velocity in cm/uS
#define SOUND_VELOCITY 0.034

long duration;
float distance;

void setup() {
  Serial.begin(115200); // Starts the serial communication
  Serial.flush();
  pinMode(TRIGGER_PIN, OUTPUT); // Sets the TRIGGER_PIN as an Output
  pinMode(ECHO_PIN, INPUT); // Sets the ECHO_PIN as an Input
  pinMode(LED_GREEN, OUTPUT);
  pinMode(LED_ORANGE, OUTPUT);
  pinMode(LED_RED, OUTPUT);
}

void loop() {
  // Clears the TRIGGER_PIN
  digitalWrite(TRIGGER_PIN, LOW);
  delayMicroseconds(2);
  // Sets the TRIGGER_PIN on HIGH state for 10 micro seconds
  digitalWrite(TRIGGER_PIN, HIGH);
  delayMicroseconds(10);
  digitalWrite(TRIGGER_PIN, LOW);

  // Reads the ECHO_PIN, returns the sound wave travel time in microseconds
  duration = pulseIn(ECHO_PIN, HIGH);

  // Calculate the distance
  distance = duration * SOUND_VELOCITY/2;

  // Prints the distance on the Serial Monitor
  Serial.print("Distance (cm): ");
  Serial.println(distance);

  if (distance >= 12) {
    green();
  } else if (distance < 12 && distance > 7) {
    orange();
  } else {
    red();
  }

  delay(500);
}

void green() {
  digitalWrite(LED_GREEN, HIGH);
  digitalWrite(LED_ORANGE, LOW);
  digitalWrite(LED_RED, LOW);
}

void orange() {
  digitalWrite(LED_GREEN, LOW);
  digitalWrite(LED_ORANGE, HIGH);
  digitalWrite(LED_RED, LOW);
}

void red() {
  digitalWrite(LED_GREEN, LOW);
  digitalWrite(LED_ORANGE, LOW);
  digitalWrite(LED_RED, HIGH);
}
```

----
[⬅️ Retour à l'énoncé](tp7.md)
