# Laboratoire 1 / Partie 3


## Partie 3:
- Exemple Pulse Width Modulation


# PWM

Le PWM est un fonction très utile qui permet de minimaliser une procédure `difficile` en une simple fonction.

Voici un exemple sans librairie:


```
#define DELTA 200 // ms 
#define RATIO DELTA/1024 
#define OUTPUT_PWM 3

int sensorPin = A0; 
int sensorValue = 0;  
int conversion = 0;  

void setup() {
  //analogReference(EXTERNAL);
  Serial.begin(9600);
  pinMode(OUTPUT_PWM, OUTPUT);
}

void loop() {
  sensorValue = analogRead(sensorPin);
  conversion = (int)((float)sensorValue * RATIO);
  Serial.print("Value: ");
  Serial.println(conversion);

  digitalWrite(OUTPUT_PWM, HIGH);
  delay(conversion);
  digitalWrite(OUTPUT_PWM, LOW);
  delay(DELTA-conversion);
}
```

Dans l'utilisation d'un LED, pas besoin de compliquer le tout et on peut directement utiliser `analogWrite`.

https://docs.arduino.cc/learn/microcontrollers/analog-output/

https://docs.arduino.cc/language-reference/en/functions/analog-io/analogWrite/

![](gui/circuit2.JPG)

> $\color{gray}{\text{MANIPULATION}}$ **PWM**
>
> Utiliser l'exemple sur le site de Arduino (analogWrite).
> 
> Voici les changements:
> - Brancher une DEL à la pin 3.
> - Utiliser la lecture analog sur `A0`.
> - Envoyer la valeur via le `Serial Monitor`.
> 


> $\color{darkred}{\text{À VÉRIFIER}}$ **PWM Eval**
>
> Montrer à l'enseignant le `Serial Monitor`, la DEL ainsi que le signal sur la pin 3 (La DEL). 
> Décrivez dans vos mots ce qui se produit dans ce programme.
