# Principes POO

L'objectif de la POO est de rendre les programmes plus modulaires, plus réutilisables, plus simples à comprendre, plus simples à entretenir pour les faire évoluer, plus maintenables.

La POO se base sur quelques principes qu'il est nécessaire de connaître et correctement appliquer. Cela permettra de structurer le logiciel et il en résultera des éléments de code plus simples et plus réutilisables. Le résultat final sera plus lisible, plus compréhensible, plus robuste, plus évolutif et davantage maintenable.

Voici les principes de la POO qu'il faut connaître et bien comprendre :

- La responsabilité unique
- L'encapsulation
- L'héritage
- L'abstraction
- Le polymorphisme
- Le couplage entre classes
- La réutilisabilité
- KISS
  
## La responsabilité unique, clairement définie

Ce concept très basique est probablement le plus important en termes de _Programmation Orientée Objets_.

Son principe est simple :

- **Une classe ne devrait avoir qu’une seule et unique responsabilité, clairement définie**

Elle se concentrera sur quelques aspects bien définis, focalisés, et donc plus simples à réaliser. Elle sera également plus facile à comprendre, à tester et à maintenir. Cela réduira également le risque d'erreurs lors de modifications.

Exemples :

- une classe `Adresse` dont le seul but est de transporter des informations d'addresse, sans aucun traitements possibles.
- une classe `RandomGenerator` qui doit permettre de générer des nombres aléatoires de plusieurs façons, mais rien d'autre.
- une classe `Commande` qui représentera une commande faite par un client et qui permettra de faire ce qu'on peut faire avec une commande (l'annuler, la payer, y rajouter ou supprimer un élément) et rien d'autre.

## L'encapsulation

L'encapsulation permet à une classe de n'exposer au monde extérieur que les informations et les traitements souhaités.

Cela permet de réaliser des classes dont la compréhension et dont l'utilisation sont simples car elles n'exposent que ce qui est nécessaire et utile à l'utilisateur (public), sans l'embarasser avec des détails inutiles qui resteront cachés au monde extérieur (private) ou des informations qui doivent être protégés d'un accès non autorisé (attributs).

Ce principe de la POO permet de réaliser des classes plus simples à utiliser, focalisées sur leur responsabilité unique, en permettant justement de cacher tout le reste.

Exemples :

- une classe `Apprenti` dont la seule méthode visible et utilisable serait `afficheDetails()`, alors qu'en interne cette classe aurait de nombreux attributs cachés (private) dont son `id` unique, ainsi qu'une méthode cachée (private) utilisée par `afficheDetails()` pour récupérer toutes les informations "à jour" de cet apprenti (id) directement dans la base de données.  
        Facile à comprendre et à utiliser, car on ne peut faire qu'une seule chose avec un tel apprenti.

## L'héritage

L'héritage est l'un principe clé les plus importants de la POO.

Ce principe permet de dire qu'une classe **hérite** d'une autre classe, ce qui transmettra l'ensemble des attributs et du savoir-faire de la classe mère à la classe fille.

Ce principe de la POO est très utile pour **étendre** ou pour **progressivement raffiner** des comportements et des savoir-faire dans les classes filles.

Il fonctionne comme dans la vie réelle et est facile à se représenter : un apprenti est un humain, un humain est un mammifère, un mammifère est un être-vivant.

Exemples :

- on pourrait donc dire que `Apprenti` hérite de `Humain`, que `Humain` hérite de `Mammifere`, que `Mammifere` hérite de `EtreVivant`. Grâce à l'héritage, en plaçant la fonctionnalité `manger()` ou la caractéristique `Date dateDeNaissance` dans la classe `EtreVivant`, toutes les classes filles en bénéficieront automatiquement, sans avoir à écrire une ligne de code supplémentaire. Du coup un `Apprenti` aura une date de naissance (provenant de Humain ayant hérité de cette caractéristique de Mammifere qui l'a héritée de EtreVivant).
- on pourrait créer la classe `StringMalin` qui hériterait de la classe `String`, qui fournirait une fonctionnalité supplémentaire `vireTousLesEspaces()` que le classe `String` ne fournit pas.

Ce principe de la POO permet généralement aussi une économie de code car les savoir-faire pourront être placés au "bon étage" dont toutes les autres classes bénéficieront automatiquement ensuite sans avoir à l'écrire (comme dans l'exemple ci-dessus avec la date de naissance et le savoir-faire manger()).

**ATTENTION :** il est impératif de toujours bien vérifier qu'on puisse toujours dire **"IS-A"** lorsque de l'héritage est en jeu. En effet, on doit pouvoir dire qu'un `Apprenti` **est 100% un** `Humain`. Dans le cas contraire, si ça ne sonne pas bien à l'oreille, c'est qu'il y a un souci et que l'héritage n'est pas l'outil adéquat.

## L'abstraction

Ce principe de la POO permet de se concentrer sur le "quoi" plutôt que sur le "comment".

L'abstraction consiste à **généraliser** certains comportements toujours présents (quoi) mais réalisés potentiellement différemment (comment) d'une situation à une autre. Il en résulte des classes plus simples et plus légères, avec des responsabilités également plus simples et mieux définies.

Exemples :

- un `Rectangle`, un `Cercle`, un `Carre` et un `Losange` ont bien évidemment tous le savoir-faire (le quoi) de calculer leur propre surface et de calculer leur propre périmètre.
- Par contre, il est également bien clair que l'implémentation de ces méthodes, c'est-à-dire la façon de calculer ces informations (le comment) sera très différente dans chacune de ces situations.
- Fort de ce constat, on pourrait donc **généraliser** et réaliser une _abstraction_ à l'aide d'une classe `Forme` prevoyant cela. La classe `Forme` prévoira deux méthodes `calculeSurface()` et `calculePerimetre()` permettant à toute forme (dont Rectangle, Carre, Cercle...) de calculer ces deux informations, sans toutefois être capable de le faire à leur place (et donc ces deux méthodes seront donc abstraites/`abstract` = sans code).
- Cette abstraction, cette généralisation, nous permettra d'avoir une collection d'objets `Forme` et de leur demander de faire des choses, de manière "standardisée".

## Le polymorphisme

Le mot polymorphisme vient du grec et signifie “qui peut prendre plusieurs formes”.

Ce principe de la POO permet aux objets de différents types de répondre de manière différentes à des appels de méthodes ayant le même nom. Cela permet de **modifier le comportement** d'une classe à l'autre en **surchargeant** l'une ou l'autre de ses méthodes.

Exemples :

- la méthode `toString()` automatiquement héritée de la classe `Object`, prévue pour être surchargée par tous les objets de nature différente afin de correctement se représenter sous forme de chaîne de caractères.
- la méthode `calculeNoteFinale()` de la classe `Cours` dont le code nécessaire est de calculer la moyenne des notes obtenues lorsqu'il s'agit de maths, physique, chimie, mais de chercher la note la plus grande lorsqu'il s'agit de modules.

On distingue:
-  Le polymorphisme ad hoc, qui est une surcharge de fonction, c'est à dire des fonctions de même nom mais de signature différente, en proposant des paramètres différents en type ou/et en nombre.
  
-  Le polymorphisme de sous-typage ou héritage, pour lequel des classes qui héritent d'une classe de base en redéfinissent certaines méthodes.

- Le polymorphisme par implémentation d'interface. Les interfaces permettent de définir un "contrat" que les classes doivent respecter.
 Une classe qui implémente une interface doit fournir des implémentations pour toutes les méthodes déclarées dans l'interface. Par conséquent le comportement de méthodes de cette interface pourra être différent.

## Le couplage entre classes

Les classes peuvent dépendre les unes des autres. Suivant la difficulté à séparer deux classes, on parlera de couplage faible (souhaitable) ou de couplage fort (moins souhaitable).

Si la suppression d’une classe implique beaucoup de modifications dans l’autre classe, on parle de couplage fort. A l’inverse, si le système a bien été pensé afin de rendre les classes assez indépendantes, on parle de couplage faible.

Si le couplage est fort, le code est difficile à faire évoluer car en cas de modification les répercussions peuvent être énormes sur les autres classes dont on dépend ou qui dépendent de nous (couplage).

À l'extrême, si dans une application le couplage entre les classes est fort partout, les liens qui unissent ces classes forment un vrai “plat de spaghettis”.

Supprimer tout couplage dans une application est impossible : il y en aura toujours. Il faut simplement veiller à éviter le couplage fort lorsque cela est possible :

- Un couplage fort est présent dans le cas d'une **composition**.
- Le couplage est plus faible dans le cas d'une **aggrégation**.
- Le couplage est le plus faible lorsqu'on utilise des **interfaces**.

## La réutilisabilité

Dupliquer du code tend à indiquer qu'il est mal conçu. Il est nécessaire de factoriser au maximum son code afin d'éviter toutes répétitions inutiles.

La réutilisabilité du code simplifie la lisibilité, la maintenance, la recherche et résolution de bugs.

Les principes de POO présentés ci-dessus sont des outils très efficaces pour tendre vers une plus grande réutilisabilité du code.

## KISS: Keep It Simple and Stupid

Votre code doit être “tout bêtement simple”. En effet, si votre code/architecture est compliqué à comprendre, c’est très certainement parce que quelque chose a mal été pensé ou pas assez pensé.

Alors à chaque fois que vous codez, gardez cette notion en tête ! Choisissez bien vos noms et faites quelque chose de simple à comprendre et à manipuler !
