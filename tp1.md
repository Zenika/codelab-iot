---
title: "TP 1 👾 Simulation d'un ESP"
nav_order: 21
schema: true
---

# TP 1 : Simulation d'un ESP avec une LED

{: .objectiv }
Découvrir le language de programmation utilisé sur les Arduinos

1. Pour se familiariser avec le code "à la Arduino", nous allons débuter avec un outil en ligne permettant de simuler un _Sketch_ (= programme Arduino) sur un ESP avec une LED et une résistance afin de faire clignoter une LED ➡️ [suivre ce tutorial](https://wokwi.com/projects/305566932847821378){:target="_blank"}
![simulation](resources/tp1-simulation.jpg)

{: .tip }
Si vous voulez aller plus loin, [la documentation détaille](https://docs.arduino.cc/learn/programming/sketches){:target="_blank"} bien la structure des sketchs.

{:style="counter-reset:none"}
3. Les fonctions [`pinMode()`](https://www.arduino.cc/reference/en/language/functions/digital-io/pinmode/){:target="_blank"} et [`digitalWrite()`](https://www.arduino.cc/reference/en/language/functions/digital-io/digitalwrite/){:target="_blank"} sont utilisées respectivement pour configurer le sens entrée/sortie de la broche et pour mettre `0` (état bas ou `LOW`) ou `5 V` (état  haut ou `HIGH`) sur cette broche.

4. Voici le code commenté du TP :

```c
/*
 définition d'une constante nommée LED valant 18,
 un rechercher/remplacer sera effectué par le pre-processeur au moment de la compilation.
 */
#define LED 18

// méthode exécutée au démarrage du micro-controleur (µC)
void setup() {
  pinMode(LED, OUTPUT);    // configuration de la patte 18 en sortie pour lui affecter OV ou 5V
}

// programme principal : une boucle infinie.
// Le µC n'exécutera que cette fonction jusqu'au son débranchement électrique ou reboot.
void loop() {
  digitalWrite(LED, HIGH); // mise en tension de la sortie 18 à 5V
  delay(500);              // attente de 500 ms
  digitalWrite(LED, LOW);  // 0V sur la sortie
  delay(500);              // attente de 500 ms
}
```

----
[TP 2 ➡️](tp2.md)
