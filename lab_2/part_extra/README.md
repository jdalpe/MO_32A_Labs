# Laboratoire 2 / Partie 6


## Partie Extra:
- UART Extra


# UART / Parité

Le protocole UART vient avec une mesure de sécurité optionnel, la parité.

Une parité `Odd` (Impair), utilisera un bit supplémentaire pour la somme du nombre de `1`. S'il l'est impair, le signal sera à `1`, sinon `0`.

Une parité `Even` (Pair), fera le comportement opposé, la somme des `1` doit être pair pour un `1`.

Dans le cas de 0 `1` (Par exemple: 0x00), la parité sera toujours à zero.


Voici un exemple:

|            | Parity Odd | Parity Even |
| ---------- | ---------- | ----------- |
| 0b00110100 | 1          | 0           |
| 0b00000000 | 0          | 0           |
| 0b11111110 | 1          | 0           |
| 0b11000000 | 0          | 1           |
| 0b10101010 | 0          | 1           |


![](gui/uart1.jpg)

> $\color{gray}{\text{MANIPULATION}}$ **UART + Parity**
>
> 
> Écrire ce code dans un nouveau programme (Celui de la partie 3)
> ```
> char receivedChar;
> boolean newData = false;
> 
> void setup() {
>     Serial.begin(9600);
>     Serial.println("<Arduino is ready>");
> }
> 
> void loop() {
>     recvOneChar();
>     showNewData();
> }
> 
> void recvOneChar() {
>     if (Serial.available() > 0) {
>         receivedChar = Serial.read();
>         newData = true;
>     }
> }
> 
> void showNewData() {
>     if (newData == true) {
>         Serial.print(receivedChar);
>         newData = false;
>     }
> }
> ```
> 
> Comme l'arduino IDE n'a pas les options avancés, vous devez les simuler.
> 
> Avec le code de départ, contrôler l'arrivée des datas (via `recvOneChar`)
> pour un data à 7 bits. À chaque envoie, avec un nombre aléatoire, envoyer une parité au hazard.
>
> Un caractère plus grand que 0X80 via `recvOneChar` ne sera pas valide et n'activera jamais `newData`.
> 
> Avant d'imprimer le tout (via `showNewData`), vérifier la parité (Parity Even) en ajoutant au Serial.print si la parité est respecté ou pas. (Le code peut envoyer plusieurs `Serial.print` ou `Serial.println` pour le formattage)
>
>
> 


> $\color{darkred}{\text{À VÉRIFIER}}$ **Point d'extra**
>
> Une fois le tout fonctionnel, montrer à l'enseignant le système avec une 
> détection de parité. 
>
> Le data doit aussi être visible à l'oscilloscope et à l'encodeur. (Parity Even, Lenght 7)
> 
> 

