# TP 4 : Capteur de lumière

{: .objectiv }
Brancher la LDR et lire sa valeur

{: .warning }
⚠️ Avant toutes manipulations de composants, il faut **débrancher** le câble USB.

La LDR est une resistance dont la valeur varie en fonction de la lumière : plus il fait sombre, plus sa résistance est élevée (> 1MΩ), moins il y a de courant, plus la tension aux bornes du composant est élevée.

Nous utiliserons un pont diviseur de tension afin de lire la tension aux bornes de la résistance via la broche `A0` de l'ESP et envoyer la valeur lue sur la console série.

Le schema électronique est le suivant :

![schema-tp4](resources/tp4-schema.jpg)

Voici le câblage correspondant :

![montage-tp4](resources/tp4-montage.jpg)

L'API à utiliser pour mesurer la tension est [`analogRead()`](https://www.arduino.cc/reference/en/language/functions/analog-io/analogread/). Pour la communication série, il faut utiliser [`Serial`](https://www.arduino.cc/reference/en/language/functions/communication/serial/) et notamment `Serial.begin()` et `Serial.println()`.

Une attente de quelques millisecondes peut être ajoutée en fin de boucle pour éviter de flooder la console via l'instruction [`delay()`](https://www.arduino.cc/reference/en/language/functions/time/delay/).

TODO mettre en spoiler le code
```c
void setup() {
  Serial.begin(9600);
  Serial.flush();
  pinMode(A0, INPUT);
}

void loop() {
  double ldr = analogRead(A0);
  Serial.print(String("valeur : "));
  Serial.println(ldr);
  delay(50);
}
```

----
[⬅️ TP 3](tp3.md) :: [TP 5 ➡️](tp5.md)
