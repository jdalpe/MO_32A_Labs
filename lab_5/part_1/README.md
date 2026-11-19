# Laboratoire 5 / Partie 1


## Partie 1:

- Communication avec module BLE

Pour la section Bluetooth, nous allons utiliser une librairie: `ArduinoBlue` by **Jae An**

Pour cette section, le code utilisé sera dans les exemples: `Examples/ArduinoBlue/HM10_console`.

Effectuer le branchement suivant: 

![](gui/hm10.JPG)

> $\color{gray}{\text{MANIPULATION}}$ **BLE**
>
> 
> Utiliser une tension de 5V pour l'alimentation. À l'aide de l'exemple et de la documentation. Connecter une paire TX et RX fonctionnel
> 

> $\color{gray}{\text{MANIPULATION}}$ **BLE Téléphone**
>
> 
> Aller dans le App Store et télécharger:
>
> - Android: `Serial Bluetooth Terminal`
> - iOS: `Arduino Bluetooth Control`
> 

Dans le but d'utiliser les applications. Votre matériel dois être 'PAIR' avec votre téléphone.

Voici la procédure de base. 

- Aller dans les paramètres Bluetooth. Le matériel sera HC-06 ou HC-05. Assurez-vous que ce soit le votre, alimenter le votre seulement quand vous être prêt à le connecter.
- Au moment du `pairing`, s'il y a un mot de passe demander, écrire: `1234`. C'est le mot de passe par défaut des appareils Bluetooth.
- Une fois `paired`. Utiliser l'application et connectez-vous au module. Une fois brancher, utiliser la fonction `READ` ou `WRITE` du service de base.
- **TRÈS IMPORTANT** Quand vous avez fini, utiliser la fonction `Unpair` dans vos paramètre Bluetooth. Cela va empecher de connecter à un module en tout temps de façon automatique.

> $\color{gray}{\text{MANIPULATION}}$ **Comm**
>
> 
> À l'aide de l'oscilloscope, valider l'envoi et la réception de data sur la pin Rx et Tx
> 


> $\color{darkred}{\text{À VÉRIFIER}}$ **Comm Eval**
>
> Montrer à l'enseignant la communication Bidirectionnel des données via l'application et l'oscilloscope
> 


> $\color{darkgreen}{\text{QUESTION}}$ **Question.docx**
> 
> Remplir les questions de la partie 1 et capturer l'oscilloscope
> 




