# Design pattern : Observateur
***

## Introduction

>Le patron Observateur (ou Observer en anglais) fait partie de de la famille des patrons comportementaux, c'est-à-dire qui se concentre sur les problèmes liés aux comportements et à l'interaction entre les classes.
Plus en particulier, il se base sur l'interception d'événements (détecter des changements ou des actions spécifiques qui se produisent dans un système logiciel) pour les traiter.
Il est utilisé pour envoyer un signal à des modules qui jouent le rôle d'observateurs. En cas de notification, les observateurs effectuent alors l'action adéquate en fonction des informations qui parviennent depuis les modules qu'ils observent (les observables).

| ![observer](https://github.com/GeniusTom-Dev/presentation-design-pattern/blob/main/assets/observer.png?raw=true) |
|------------------------------------------------------------------------------------------------------------------|

## Contexte et Utilité du Design Pattern Observateur : 
Dans de nombreuses applications logicielles, il est souvent nécessaire que certains objets réagissent aux changements survenus dans d'autres objets, mais uniquement dans des circonstances spécifiques ou pendant une période définie. Le pattern Observateur permet cette liaison dynamique, où les observateurs peuvent s'ajouter ou se retirer de la liste des observateurs selon leurs besoins

## Exemple :

| ![observer](https://github.com/GeniusTom-Dev/presentation-design-pattern/blob/main/assets/example-java.png?raw=true) |
|----------------------------------------------------------------------------------------------------------------------------|

## Explications :

Le principe est que chaque classe observable contient une liste d'observateurs ; ainsi, à l'aide d'une méthode de notification, l'ensemble des observateurs est prévenu. La classe observée hérite de Observable qui gère la liste des observateurs. La classe Observateur est quant à elle purement abstraite, la fonction de mise à jour ne pouvant être définie que par une classe spécialisée.

## Structure et fonctionnement :

La structure de ce pattern repose sur deux entités principales : les observateurs et les objets observés (observables). Chaque objet observable maintient une liste d'observateurs qui sont avertis lors de changements d'état via une méthode de notification. Cette méthode permet de signaler à tous les observateurs inscrits qu'un changement s'est produit, et chaque observateur réagit en conséquence, effectuant des modifications ou des affichages spécifiques.



## Implémentations dans des langages de programmation :

La bibliothèque intégrée API de Java met déjà à dispositions des classes et des moyens d'implémentation du pattern observateur avec notamment les classes ```java java.util.Observable``` et ```java java.util.Observer```.
Cependant, ces classes déjà prédéfinies ne sont que rarement utilisées puisque la plupart du temps, l'implémentation du code est simple et les développeurs ne veulent pas être limités pour l'héritage de comportements particuliers ne provenant pas de d'objets Observable ou Observer. En effet, Java ne permet pas l'héritage multiple dans les classes d'où l'implémentation directe par les développeurs pour garder la possibilité de faire de l'hérédité avec des classes ne suivant pas le design Observer.

## Avantages et limitations :

Les avantages de l'utilisation du design pattern Observateur résident dans la gestion efficace des événements, réduisant le couplage entre les modules (un couplage faible signifie que des modifications dans une partie du code n'affectent pas spécialement les autres parties) et simplifiant la gestion de plusieurs observateurs. Cependant, des limitations telles que les fuites de mémoire peuvent survenir, notamment avec le problème des observateurs n'étant pas correctement retirés de la liste d'observateurs, entraînant des problèmes de performance et d'optimisation. De plus, l'ordre aléatoire des notifications peut poser des défis dans certains scénarios.

## Conclusion :

En somme, le design pattern Observateur représente une approche puissante pour gérer les interactions entre les objets en notifiant les observateurs des changements d'état. Son utilisation permet de concevoir des systèmes flexibles et réactifs, bien que des précautions doivent être prises pour éviter des problèmes potentiels tels que les fuites de mémoire. La compréhension de ce design pattern offre un outil essentiel pour la conception de logiciels modulaires et extensibles.
