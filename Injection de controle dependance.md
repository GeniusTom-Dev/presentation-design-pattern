# Design pattern : Injection de contrôle/dépendance
***


## Introduction :

> L'Injection de Contrôle (Control Injection) et l'Injection de Dépendance (Dependency Injection) sont deux concepts cruciaux en programmation orientée objet, fréquemment employés dans la conception et l'architecture logicielle.

## Injection de dépendance (DI) :

Le principe de l'injection de dépendance (DI - Dependency Injection) en Java est une technique de conception visant à réduire le couplage entre les différentes parties d'un programme. Son principe fondamental est de fournir les dépendances nécessaires à un objet plutôt que de les laisser créer ces dépendances elles-mêmes.

Dans le contexte de Java, cela implique que les dépendances d'un objet sont injectées en lui plutôt que d'être instanciées à l'intérieur de celui-ci. Cette injection se réalise généralement à travers des constructeurs, des méthodes, ou des propriétés.

Cette approche permet de dynamiser la création de relations entre objets en mettant en œuvre le principe de l'inversion de contrôle. Concrètement, elle permet de rendre les dépendances entre les classes moins rigides et plus adaptables à l'exécution du programme.

Les dépendances ne sont donc plus explicitement définies dans le code source, mais plutôt déterminées de manière dynamique lors de l'exécution du programme. Cette souplesse offre un cadre de développement plus flexible, où les changements et les adaptations deviennent plus aisés à effectuer.

L'utilisation de ce design pattern implique souvent l'introduction d'interfaces pour encapsuler les méthodes spécifiques que la classe A peut invoquer sur la classe B. En adoptant cette approche, on signale que la classe B satisfait les exigences de l'interface, permettant ainsi de substituer les références directes à B par des références à l'interface au sein de la classe A.

## Qu'est-ce qu'une dépendance ?

Une dépendance se produit lorsque l'objet A dépend d'un autre objet B pour que l'objet A puisse être créé. Plusieurs conditions permettent de déterminer si un objet A dépend de B :
- La dépendance par composition, lorsque A possède un attribut de B;
- La dépendance par héritage, lorsque A est de type B;
- La dépendance par transitivité, lorsque A dépend d'un autre objet de type C qui dépend lui-même d'un objet de type B ;

Mais il a aussi la dépendance lorsqu’une méthode de A  appelle une méthode de B.
***
## Les différentes types d’injection

> Il existe quatre types d'injections de dépendances dans ce contexte :
### L'injection par constructeur

| ![constructeur](https://github.com/GeniusTom-Dev/presentation-design-pattern/blob/main/assets/constructeur.png?raw=true) |
|--------------------------------------------------------------------------------------------------------------------------|

#### Avantages :
- Clarté du code : les dépendances sont explicitement spécifié dans le constructeur ce qui rend le code plus lisible
- Evite les dépendances nulles
- Facilité de test : Il est facile de simuler des situations différentes en donnant des mocks au constructeur  
#### Désavantages :
- Complexité quand il y a un grand nombre de dépendances
- Tout changement dans les dépendances nécessite la modification du constructeur

### L'injection par mutateur
> Un mutateur est une méthode de la classe qui permet de modifier la valeur d’un attribut

| ![mutateurInjection](https://github.com/GeniusTom-Dev/presentation-design-pattern/blob/main/assets/mutateurInjection.png?raw=true) |
|--------------------------------------------------------------------------------------------------------------------------------------|

#### Avantages :
- Flexibilité : Permet de modifier une dépendance d'un objet après son instanciation, ce qui offre la possibilité de changer plusieurs la dépendance de l'objet durant l'execution.
#### Désavantages :
- Null Pointer Exeption : La dépendance peut être appelé alors qu'elle n'a pas encore été intialisé ce qui peut créer des erreurs.

### L'injection par interface

| ![interfaceInjection](https://github.com/GeniusTom-Dev/presentation-design-pattern/blob/main/assets/interfaceInjection.png?raw=true) |
|--------------------------------------------------------------------------------------------------------------------------------------|

#### Avantages :
- Flexibilité : L'attribut de dépendance peut contenir n'importe quels objets tant que sa classe implémente l'interface
#### Désavantages :
- Complexité : Réduit la clarté du code, surtout dans le cas où il y a plusieurs dépendances.

## Utilisation

L'injection de dépendances, dans le cadre de la programmation en Java, est une approche qui dynamise la création de relations entre objets en mettant en œuvre le principe de l'inversion de contrôle. Concrètement, elle permet de rendre les dépendances entre les classes moins rigides et plus adaptables à l'exécution du programme.

L'essence de l'injection de dépendance réside dans le fait que les dépendances ne sont plus explicitement définies dans le code source, mais plutôt déterminées de manière dynamique lors de l'exécution du programme. Cette souplesse offre un cadre de développement plus flexible, où les changements et les adaptations deviennent plus aisés à effectuer.

L'utilisation de ce design pattern implique souvent l'introduction d'interfaces pour encapsuler les méthodes spécifiques que la classe A peut invoquer sur la classe B. En adoptant cette approche, on signale que la classe B satisfait les exigences de l'interface, permettant ainsi de substituer les références directes à B par des références à l'interface au sein de la classe A.

## Exemple d’utilisation d’une injection de dépendance(Injection de dépendance avec un constructeur)

|Exemple sans DI : | Exemple avec DI : |
|---|---|
| ![sans-di](https://github.com/GeniusTom-Dev/presentation-design-pattern/blob/main/assets/sans-di.png?raw=true) | ![avec-di](https://github.com/GeniusTom-Dev/presentation-design-pattern/blob/main/assets/avec-di.png?raw=true) |

## Injection de Contrôle (IoC)

### Définition
Le terme peut être interprété comme une forme de renversement de contrôle (Inversion of Control, IoC), où le contrôle du flux d'exécution est déplacé de l'application principale vers un cadre (framework : ensemble de bibliothèques, d'outils et de conventions utilisés pour créer une structure logicielle) ou un système sous-jacent.

### Principe
Transférer le contrôle de certaines parties d'un programme à un cadre ou un conteneur, souvent pour améliorer la modularité et la testabilité.

### Utilisation
Souvent utilisé dans les frameworks et bibliothèques pour standardiser le comportement de certaines fonctions, comme la gestion d'événements ou de requêtes.

Elle constitue une approche majeure dans le développement logiciel. Elle déplace le contrôle du flux d'exécution d'une application du code applicatif vers un framework ou une couche logicielle sous-jacente. Cette méthode permet à l'application de définir des blocs de code à utiliser via une interface fournie par le framework, allégeant ainsi le programme principal de la gestion directe du flux d'exécution.

Dans le cas d'utilisation classique où une application interagit avec l'utilisateur pour obtenir des informations, l'approche traditionnelle implique que le programme contrôle non seulement l'interface homme-machine (IHM : la manière dont les utilisateurs interagissent avec une application logicielle via des interfaces visuelles ou des commandes) mais aussi la séquence d'exécution. En revanche, avec l'IoC, le framework prend en charge la gestion du flux d'exécution tandis que le programme principal se concentre sur le traitement et les composants IHM. Cette séparation permet une meilleure organisation du code et facilite sa maintenance.

| Exemple sans IOC :                                                                                               | Exemple avec IOC :                                                                                               |
|------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
| ![sans-ioc](https://github.com/GeniusTom-Dev/presentation-design-pattern/blob/main/assets/sans-ioc.png?raw=true) | ![avec-ioc](https://github.com/GeniusTom-Dev/presentation-design-pattern/blob/main/assets/avec-ioc.png?raw=true) |

