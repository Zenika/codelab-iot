---
title: "TP 5 : Pilotage d'un feu 🚦"
nav_order: 8
schema: true
---

# TP 5 : Faire clignoter le feu tricolore

{: .objectiv }
Faire clignoter le feu tricolore

{: .warning }
⚠️ Avant toutes manipulations de composants, il faut **débrancher** le câble USB.

Nous allons maintenant faire clignoter le feu tricolore fourni.
Le cycle souhaité est :
 - Rouge : 5  secondes
 - Vert : 7 secondes
 - Orange : 2 secondes
 ...

N'hésitez pas à séparer le controle de chaque led dans des méthodes

## Optionnel : Utiliser le capteur de lumière pour passer le feu au rouge

{: .objectiv }
Ajouter un controle pour un passage au rouge plus rapide

Comme les boutons pour déclencher une traversée d'un piéton ou les capteurs magnétiques sous la chaussée, nous allons maintenant utiliser le capteur de lumière du TP précédent pour accélerer le passage au rouge du feu.

Lors de l'activation du capteur, le feu devra passer au orange au maximum dans les 2 secondes puis continuer son cycle normal.

![feu tricolore](resources/feu.jpg)
