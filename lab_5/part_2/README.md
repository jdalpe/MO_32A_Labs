# Laboratoire 5 / Partie 2


## Partie 2:

- Communication avec servomoteur


Pour le servomoteur, nous allons utiliser les `Timers` à l'interne. 
Le branchement sera très simple aussi
 ```
// Brun -> GND
// Rouge -> 5V
// Orange -> 2
```

Le tout fonctionne avec un module à impulsion.

Voici le code utilisé:

```
#define RESET_20 2000
#define MAX_RES 200
#define MIN_RES 50


volatile int fired = 0;
volatile int value = 0;
volatile int real = 0;

void setup() {
  //https://www.8bit-era.cz/arduino-timer-interrupts-calculator.html
  cli(); // stop interrupts
  TCCR1A = 0; // set entire TCCR1A register to 0
  TCCR1B = 0; // same for TCCR1B
  TCNT1  = 0; // initialize counter value to 0
  // set compare match register for 100000 Hz increments
  OCR1A = 159; // = 16000000 / (1 * 100000) - 1 (must be <65536)
  // turn on CTC mode
  TCCR1B |= (1 << WGM12);
  // Set CS12, CS11 and CS10 bits for 1 prescaler
  TCCR1B |= (0 << CS12) | (0 << CS11) | (1 << CS10);
  // enable timer compare interrupt
  TIMSK1 |= (1 << OCIE1A);
  sei(); // allow interrupts 

  pinMode(2, OUTPUT);

  Serial.begin(115200);
}

// Timer interrupt
ISR(TIMER1_COMPA_vect){
  if (value < real)
    fired = 1;
  else
    fired = 0;
  value += 1;
  if (value >= RESET_20)
  {
    value = 0;
  }
  
}

void loop() {
  if (fired)
  {
    digitalWrite(2, HIGH);
  }
  else
  {
    digitalWrite(2, LOW);
  }

  if (Serial.available()) {
    int number = Serial.parseInt();
    if (number != 0) {
      real = number + MIN_RES;
      Serial.print("You entered: ");
      Serial.println(number);
      Serial.print("Value: ");
      Serial.println(value);
      Serial.print("Real: ");
      Serial.println(real);
      Serial.print("Fired: ");
      Serial.println(fired);
      
    }
  }
}
```


> $\color{gray}{\text{MANIPULATION}}$ **Utilisation du programme**
>
> Le programme s'utilise avec le port Sérielle à 9600. Entrer une valeur de 1 à 200.
>
> Tester le programme et brancher l'oscilloscope sur la pin 2. Prenez un moment pour comprendre le programme. Le lien URL servira a expliquer le calcul.
>
>


> $\color{darkred}{\text{À VÉRIFIER}}$ **Explication du programme et oscilloscope**
>
> Expliquer à l'enseignant le programme.
> 


> $\color{darkgreen}{\text{QUESTION}}$ **Question.docx**
> 
> Remplir les questions de la partie 2 et capturer l'oscilloscope
> 



