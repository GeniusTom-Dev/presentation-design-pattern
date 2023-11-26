# Design pattern : Observateur
***

## Principe

Le patron Observateur (ou Observer en anglais) fait partie de de la famille des patrons comportementaux, c'est-à-dire qui se concentre sur les problèmes liés aux comportements et à l'interaction entre les classes.  
Plus en particulier, il se base sur l'interception d'événements (détecter des changements ou des actions spécifiques qui se produisent dans un système logiciel) pour les traiter.
Il est utilisé pour envoyer un signal à des modules qui jouent le rôle d'observateurs. En cas de notification, les observateurs effectuent alors l'action adéquate en fonction des informations qui parviennent depuis les modules qu'ils observent (les observables).

### Structure  

La structure de ce pattern repose sur deux entités principales : les observateurs et les objets observés (observables). Chaque objet observable maintient une liste d'observateurs qui sont avertis lors de changements d'état via une méthode de notification. Cette méthode permet de signaler à tous les observateurs inscrits qu'un changement s'est produit, et chaque observateur réagit en conséquence, effectuant des modifications ou des affichages spécifiques.

| ![observer](https://github.com/GeniusTom-Dev/presentation-design-pattern/blob/main/assets/observer.png?raw=true) |
|------------------------------------------------------------------------------------------------------------------|

### Explication  

Le principe est que chaque classe observable contient une liste d'observateurs ; ainsi, à l'aide d'une méthode de notification, l'ensemble des observateurs est prévenu. La classe observée hérite de Observable qui gère la liste des observateurs. La classe Observateur est quant à elle purement abstraite, la fonction de mise à jour ne pouvant être définie que par une classe spécialisée.

## Contexte et Utilité du Design Pattern Observateur : 

Le patron Observateur est recomandé dès qu'il est nécessaire de gérer des évènements ou quand une classe déclenche l'exécution d'une ou plusieurs autres.  
Dans de nombreuses applications logicielles, il est souvent nécessaire que certains objets réagissent aux changements survenus dans d'autres objets, mais uniquement dans des circonstances spécifiques ou pendant une période définie. Le pattern Observateur permet justement cette liaison dynamique, où les observateurs peuvent s'ajouter ou se retirer de la liste des observateurs selon leurs besoins. Il permet aussi de pouvoir faires plusieurs traitements, tous différents, d'un même évènement ; ce qui est, dans le patron Observateur, représenté par une liste d'observateurs héritant tous de la classe Observable mais qui possèdent chacunes des contenus de méthodes qui leur sont propre.

## Avantages et limites :

Les avantages de l'utilisation du design pattern Observateur résident dans la gestion efficace des événements, réduisant le couplage entre les modules dont n'est observé que l'état et le comportement en particulier (un couplage faible signifie que des modifications dans une partie du code n'affectent pas spécialement les autres parties) et simplifiant la gestion de plusieurs observateurs.  
Cependant, ce design pattern reste limitant, en particulier sur la manière dont il doit être implémenté : Dans la majeure partie des langages de programmation dont Java et C++, l'interface observateur ne peut être implémentée qu'avec l'héritage donc la composition n'est pas une option pour l'utilisation de ce type de patron dans du code. Il existe aussi d'autres limites et problèmes en lien avec le design pattern Observer, on peut notamment rencontrer des problèmes tels que des fuites de mémoire pouvant survenir en particulier avec le problème des observateurs n'étant pas correctement retirés de la liste d'observateurs, ce qui entraîne des problèmes de performance et d'optimisation. De plus, l'ordre aléatoire des notifications peut aussi poser des défis conséquents dans certains scénarios.

## Implémentations dans des langages de programmation :

La bibliothèque intégrée API de Java met déjà à disposition des classes et des moyens d'implémentation du pattern observateur avec notamment les classes ```java.util.Observable``` et ```java.util.Observer``` qui sont notamment souvent utilisées pour la réalisation d'interface graphiques en JavaFX.  
Cependant, ces classes déjà prédéfinies ne sont que rarement utilisées puisque la plupart du temps, l'implémentation du code est simple et les développeurs ne veulent pas être limités pour l'héritage de comportements particuliers ne provenant pas de d'objets Observable ou Observer. En effet, Java ne permet pas l'héritage multiple dans les classes, d'où l'implémentation directe par les développeurs pour garder la possibilité de faire de l'hérédité avec des classes ne suivant pas le design Observer.

### Exemple :

Voici un exemple d'implémentation du design pattern Observer en utilisant les classes de l'API Java.  
| ![observer](https://github.com/GeniusTom-Dev/presentation-design-pattern/blob/main/assets/example-java.png?raw=true) |
|----------------------------------------------------------------------------------------------------------------------------|

## Conclusion :

En somme, le design pattern Observateur représente une approche puissante pour gérer les interactions entre les objets en notifiant les observateurs des changements d'état. Son utilisation permet de concevoir des systèmes flexibles et réactifs, bien que des précautions doivent être prises pour éviter des problèmes potentiels tels que les fuites de mémoire. La compréhension de ce design pattern offre un outil essentiel pour la conception de logiciels modulaires et extensibles.
