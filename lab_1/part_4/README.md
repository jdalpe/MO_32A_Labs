# Laboratoire 1 / Partie 4


## Partie 4:
- Communication intermatérielle


# Émetteur [Tx] - Récepteur [Rx]

Les protocoles servent dans plusieurs configurations, que nous allons voir en classes théoriques. Mais le concept de base est d'envoyer de l'information entre A et B. Dans la plupart des prochains laboratoires, A et B seront 2 étudiants qui travaillent sur l'émetteur et le récepteur respectivement. 

Placez-vous avec un étudiant pour la dernière étape. Définissez votre rôle Émetteur (`Transmit [Tx]`) ou Recepteur (`Receive [Rx]`).

![](gui/circuit1.JPG)

> $\color{gray}{\text{MANIPULATION}}$ **En équipe**
>
> - Faire le circuit ci-dessus.
> - Placer la sonde 1 de l'oscilloscope sur le fil `vert`.
> - Placer la sonde 2 de l'oscilloscope sur le fil `orange`.
> 

> $\color{gray}{\text{MANIPULATION}}$ **Émetteur / Tx SEULEMENT**
>
> Écrire le code requis pour l'émetteur, voici la procédure a réaliser en pseudo-code
> ```
> setup()
>   Initialiser le terminal à 9600
>   Pin 2 input pull-up
>   Pin 3 output
>   Pin 3 = 0
> loop()
>   si pin 2 = 0
>      Terminal: "bouton activé"
>      pin 3 = 1
>      delai 500ms
>      Terminal: "bouton désactivé"
>      pin 3 = 0
>      
> ```

Pour le récepteur, nous allons aussi utiliser la broche 13 pour une DEL, mais au lieu de la brancher, nous allons profiter du Arduino Mega qui a déjà une lumière en `surface-mount`.

![](gui/led.JPG)

> $\color{gray}{\text{MANIPULATION}}$ **Récepteur / Rx SEULEMENT**
>
> Écrire le code requis pour le récepteur, voici la procédure a réaliser en pseudo-code
> ```
> setup()
>   Initialiser le terminal à 9600
>   Pin 2 input pull-up
>   Pin 3 output
>   Pin 13 output
>   Pin 3 = 0
>   Pin 13 = 0
> loop()
>   si pin 2 = 1
>      Terminal: "réception"
>      pin 3 = 1
>      pin 13 = 1
>      delai 500ms
>      Terminal: "réception terminer"
>      pin 3 = 0
>      pin 13 = 0
>      
> ```


> $\color{darkred}{\text{À VÉRIFIER}}$ **Rx/Tx Eval**
>
> Montrer à l'enseignant le `Serial Monitor`, la DEL ainsi que le signal sur la pin 3 (Oscilloscope sur la pin 3 des 2 Arduinos). 
> Décrivez dans vos mots ce qui se produit dans ce programme.
> 

Le print `réception` est placer avant la pin, le delai n'est cependant pas affecté, car la librairie `Serial` utilise les interruptions et les 
compteurs interne.

> $\color{gray}{\text{MANIPULATION}}$ **Récepteur Bloquant**
>
> Pour voir l'impact du temps de transmission du protocole UART, ajouter
> `Serial.flush();` entre l'envoi `Serial` et `pin 3 = 1`.
> 

> $\color{darkred}{\text{À VÉRIFIER}}$ **Rx/Tx Eval Bloquant**
>
> Montrer à l'enseignant le signal sur la pin 3 (Oscilloscope sur la pin 3 des 2 Arduinos). 
> 
> Au lieu de `réception`, écriver un très long message.
> Montrer à l'enseignant le signal sur la pin 3 (Oscilloscope sur la pin 3 des 2 Arduinos). 
> 

> $\color{darkgree}{\text{QUESTIONS}}$ **Remettez le document questions.docx rempli via Teams**
>
> Laboratoire 1 fini!