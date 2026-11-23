# Laboratoire 5 / Partie 3


## Partie 3:

- Communication avec servomoteur 2

**EDIT**: cette section ici va changer pour ne pas utiliser BLE car Android est la seule plateforme qui supporte Bluetooth 2.0.



> $\color{gray}{\text{MANIPULATION}}$ **Servo 2**
>
> À l'aide de l'exemple de Servomoteur. Créé un oscillateur entre 2 valeurs.
> Le temps d'oscillation peut-être défini en secondes/millisecondes via un DEFINE.
>
> Garder l'interrupt et la section qui contrôle le digitalWrite. 
> Enlever la section du Serial.print dans le loop.
>
> Placer votre calcul et changement pour l'oscillateur dans: `ISR(TIMER1_COMPA_vect)`
> 
>
> Si votre code est trop gros, utiliser d'autres variable `volatile` pour finaliser le calcul dans `loop`.


> $\color{darkred}{\text{À VÉRIFIER}}$ **Eval**
>
> Montrer à l'enseignant votre code et expliquer ce qu'il fait.
> 

**Laboratoire fini**

