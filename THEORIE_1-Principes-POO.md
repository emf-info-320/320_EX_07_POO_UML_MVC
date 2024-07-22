# Principes POO

L'objectif de la POO est de représenter les éléments du monde réel sous forme d'objet. De plus elle permet de représenter les interactions entre ces objets.
Afin de réaliser une conception lisible, évolutif et maintenable il est nécessaire de connaître et d'appliquer les principes suivants:

- La responsabilité unique
- L'encapsulation
- L'abstraction
- L'héritage
- Le polymorphisme
- Le faible couplage
- La réutilisabilité
- KISS
  

La force de la POO, lorsqu'elle est bien utilisée, est de rendre les programmes modulaires, réutilisables et maintenables.

## La responsabilité unique
Ce concept très basique est probablement le plus important en termes de Programmation Orientée Objet. Son principe est simple :
- **Une classe ne doit avoir qu’une seule et unique responsabilité**

Cela signifie que chaque classe doit se concentrer sur une seule tâche ou aspect du logiciel. 

Une classe avec une seule responsabilité est plus facile à comprendre, à tester et à maintenir. Cela réduit également le risque d'erreurs lors des modifications.

## L'encapsulation
L'encapsulation présente toutes les informations importantes d'un objet à l'intérieur de l'objet et n'expose que les informations choisies au monde extérieur.
Cette propriété garantit que les informations d'un objet sont cachées au monde extérieur en regroupant dans une classe les caractéristiques ou attributs qui ont un accès privé, et les comportements ou méthodes qui ont un accès public.

Elle permet donc de cacher les détails internes et de protéger les données contre les accès non autorisés.

## L'abstraction
L'abstraction consiste à simplifier des concepts complexes en ne montrant que les aspects essentiels et en cachant les détails d'implémentation. Elle se concentre sur le "quoi" plutôt que sur le "comment".

L'abstraction facilite la maintenance d'un code volumineux, en cachant les détails complexes à l'utilisateur d'une classe donnée. Il s'agit d'une extension de l'encapsulation.

## L'héritage
L'héritage définit des relations hiérarchiques entre les classes, de sorte que les attributs et méthodes communs peuvent être réutilisés. En définissant des attributs et des comportements de base dans une classe, il est possible de créer des classes secondaires qui étendent la fonctionnalité de la classe principale et ajoutent des attributs et des comportements supplémentaires. C'est l'une des clés de la programmation orientée objet.

## Le polymorphisme
Le mot polymorphisme vient du grec et signifie “qui peut prendre plusieurs formes”.
C'est un concept qui permet aux objets de différents types de répondre de manière différentes à des appels de méthodes ayant le même nom.

On distingue:
-  Le polymorphisme ad hoc, qui est une surcharge de fonction, c'est à dire des fonctions de même nom mais de signature différente, en proposant des paramètres différents en type ou/et en nombre.
  
-  Le polymorphisme de sous-typage ou héritage, pour lequel des classes qui héritent d'une classe de base en redéfinissent certaines méthodes.

- Le polymorphisme par implémentation d'interface. Les interfaces permettent de définir un "contrat" que les classes doivent respecter.
 Une classe qui implémente une interface doit fournir des implémentations pour toutes les méthodes déclarées dans l'interface. Par conséquent le comportement de méthodes de cette interface pourra êre différent.

## Le faible couplage
Les classes peuvent dépendre les unes des autres. Suivant la difficulté à séparer deux classes, on parlera de couplage faible ou fort. Si la suppression d’une classe implique beaucoup de modifications dans l’autre classe, on parle de couplage fort. A l’inverse, si le système a bien été pensé afin de rendre les classes assez indépendantes, on parle de couplage faible.

Si le couplage est fort, le code est difficile à faire évoluer. En cas de modification d’une classe, les répercussions peuvent être énormes sur les autres classes, et les liens qui unissent les classes de l’applications forment un vrai “plat de spaghettis”.

Un couplage fort est présent dans le cas d'une composition. Le couplage est plus faible dans le cas d'une aggrégation et encore plus faible lors d'utilisation d'interface.

## La réutilisabilité
Dupliquer du code indique qu'il est mal conçu. Il est nécessaire de factoriser au maximum son code afin d'éviter toutes répétitions.
La réutilisabilité du code simplifie la lisibilité, la maintenance, la rechercher et résolution de bug. 

En POO, nous disposons d'outils très efficace pour appliquer la réutilisabilité: les classes et l'héritage.

## KISS: Keep It Simple and Stupid
Votre code doit être “tout bêtement simple”. En effet, si votre code/architecture est compliqué à comprendre, c’est très certainement parce que quelque chose a mal été pensé. Alors à chaque fois que vous codez, gardez cette notion en tête, et faites quelque chose de simple à comprendre et à manipuler !



