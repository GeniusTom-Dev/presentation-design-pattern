# Design pattern : Injection de contrôle/dépendance
***


## Introduction :

> L'Injection de Contrôle (Control Injection) et l'Injection de Dépendance (Dependency Injection) sont deux concepts cruciaux en programmation orientée objet, fréquemment employés dans la conception et l'architecture logicielle.

## Injection de dépendance (DI) :

Lors de la conception d'un programme en Java, une pratique courante consiste à structurer le code en plusieurs classes, chacune ayant son fichier dédié. Bien que cette approche vise à rendre le code plus lisible et plus facile à entretenir, elle peut rendre délicate la substitution d'une classe par une autre. Pour remédier à ce problème, particulièrement en Java, l'injection de dépendance est souvent utilisée. Elle facilite grandement le remplacement d'une classe par une autre et autorise la configuration de diverses options pour l'application.

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

### L'injection par interface

| ![interfaceInjection](https://github.com/GeniusTom-Dev/presentation-design-pattern/blob/main/assets/interfaceInjection.png?raw=true) |
|--------------------------------------------------------------------------------------------------------------------------------------|


### L'injection par mutateur
> Un mutateur est une méthode de la classe qui permet de modifier la valeur d’un attribut

| ![interfaceInjection](https://github.com/GeniusTom-Dev/presentation-design-pattern/blob/main/assets/interfaceInjection.png?raw=true) |
|--------------------------------------------------------------------------------------------------------------------------------------|







