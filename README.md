# Connaissances requises pour réaliser un TM de programmation d'un jeu vidéo

Ce document décrit les connaissances théoriques et techniques qu'il faut avoir pour mener à bout un projet de TM de réalisation d'un jeu vidéo.

Il n'est pas obligatoire de _tout_ maîtriser avant de commencer, mais il faudra tout maîtriser à un moment où un autre.
Cette charge de travail n'est pas compressible, il est fortement conseillé d'avoir un maximum de bagage avant de commencer pour pouvoir consacrer le temps du TM à la conception/réalisation/test du jeu.

## Programmation

Maitriser un _langage de programmation_. Syntaxe, variables, constantes, commentaires, structures de contrôle, structures de données, modules, fonctions, classes (voir Framework / librairie).

Exemples d'utilisation de structures de données :

- Projectiles en vol (_list_)
- Objets dans un inventaire (_set_)
- Niveau du personnage pour différentes habiletés (_dict_)
- Position d'un objet (_tuple_)

## Framework / Librairie

Il est rare de programmer un jeu vidéo _directement_ avec le langage de programmation choisi.

Il existe de nombreuses librairies ou frameworks qui facilitent le travail de programmation (par exemple en offrant une aide pour afficher des sprites, éléments qui se déplacent sur un écran sans abimer les éléments graphiques qui se trouvent dans le fond de la scène).

Par exemple pour programmer un jeu en python on pourrait utiliser _pygame_, _arcade_, etc.

Souvent ces frameworks introduisent des classes avec des comportements par défaut qu'il faudra surcharger pour obtenir le comportement qu'on veut pour son jeu. Il faut donc maitriser les concepts de _classe_, _hiérarchie_, _héritage_, _méthode_.

## Programmation orientée événements

Un jeu est interactif, quand on le programme on doit réagir aux commandes de l'utilisateur (déplacement, tir, pause, etc.) et aux évènements du jeu (collision avec un projectile, niveau de vie qui arrive à 0, etc.).

Ce style de programmation est très différent de ce que vous avez probablement vu en cours, où vous écrivez des programmes simples qui se déroulent linéairement : Ils commencent (peut-être en demandant quelques valeurs à l'utilisateur), puis calculent ou dessinent, puis affichent un résultat et finalement s'arrêtent.

Il vous faudra donc vous familiariser avec cette manière de programmer en fonction des événements, qui amène beaucoup de complexité car l'exécution du programme n'est pas parfaitement prévisible (ce qui explique pourquoi même les jeux des grands éditeurs contiennent de nombreux bugs).

## Gestionnaire de paquets

Les frameworks et librairies viennent sous forme de _paquets_.

Pour que votre jeu soit testable / utilisable sur un autre ordinateur que le vôtre, il faudra utiliser _gestionnaire de paquets_ : à partir d'une liste des paquets requis par votre jeu, cet outil se chargera d'installer / mettre à jour / désinstaller les paquets sur l'ordinateur.

Deux exemples de gestionnaires de paquets pour python sont _pip_ et _uv_.

## Maîtrise de la géométrie analytique (maths)

Que le jeu soit en 2D ou en 3D, la position des éléments de la scène sera représentée sous forme de coordonnées (x,y) ou (x, y, z).

Il est important de bien comprendre les concepts de repère, coordonnées, translation, homothétie et d'en avoir une bonne intuition.

Pour un jeu en 3D il faudra en plus maîtriser les rotations autour de 3 angles.

## Maîtrise de la dynamique du point (physique)

Presque tous les jeux vidéo contiennent une partie simulation physique :

- Par exemple un vaisseau va voir sa position changer en fonction du vecteur représentant sa vitesse.
- Parfois les éléments à l'écran sont soumis à la gravitation (comme Mario qui saute). L'accélération de la gravité va faire varier la composante verticale de la vitesse, la vitesse va à son tour faire varier la position.

La simulation physique consiste à intégrer numériquement les accélérations pour obtenir des vitesses pour finalement arriver aux positions des objets.

Si le jeu est simple on peut le faire soi-même avec assez peu de code. Pour un jeu avec beaucoup d'éléments mobiles qui interagissent il vaut mieux utiliser une _librairie_ spécialisée: un Physics engine.
Dans les deux cas il faudra maîtriser les concepts pour être capable d'affiner les paramètres de cette simulation.

## Connaissances en édition d'image

Les éléments visibles à l'écran vont venir soit d'un outil de création d'image / modèle 3D, soit d'une librairie publique d'_assets_ de jeu.

Même si vous ne créez pas vous-même toutes les images, vous devez être capable de les modifier pour changer la taille, modifier la couleur, gérer la transparence, etc.

## Connaissances en son et musique digitale

On ne s'attend pas à ce que vous composiez toute la musique / capturiez tous les sons qu'on va entendre dans le jeu.
Là aussi il se peut que vous preniez ces fichiers dans une librairie publique (sans oublier de référencer la source).

Il faut que vous soyez capable de faire des modifications de ces sons (couper, allonger, adapter le volume, etc.)

## IDE

Choisir et maîtriser un environnement de développement intégré (IDE).

Il en existe de nombreux qui sont gratuits, par exemple _VSCode_ et _PycharmCE_.
Vous allez passer beaucoup de temps avec cet outil, prenez le temps de le maîtriser.

## Gestion de projet

Le TM va se dérouler sur une longue période et il y aura un très grand nombre de tâches à analyser, planifier, réaliser, tester.

Il est _possible_ de gérer ces tâches avec une feuille excel ou un document word, mais il vaut mieux utiliser un outil simple de gestion de projet comme trello (gratuit et online).

Si vous êtes plusieurs à réaliser le TM, la gestion de projet prendra une place encore plus importante, car il faudra attribuer les tâches à chacun·e, se synchroniser, éventuellement réorganiser les tâches.

## Contrôle de version

Nous utiliserons _git_ pour contenir le code source et les artefacts (images, sons, textes) qui composent le jeu.
Cet outil permet :

- D'avoir une copie de votre travail en cas de fausse manipulation / perte de votre ordinateur / etc.
- De partager le code avec votre répondant
- Si vous êtes plusieurs dans le TM, de partager le code entre vous pour vérifier que tout fonctionne comme prévu (on parle d'intégration)
- De voir la progression au fil du temps (intéressant par exemple pour écrire la partie rétrospective du rapport)
- De revenir à une version précédente si vous avez fait fausse route
- D'expérimenter différentes possibilités sans impact sur le reste de votre travail

Il faut maîtriser conceptuellement et pratiquement ces opérations : _commit_, _push_, _fetch_, _merge_, _pull-requests_, _versions_, _branches_, _remotes_, _.gitignore_.

l'IDE que vous avez choisi offre très certainement de l'outillage permettant de faire tout ça. Les concepts ne sont pourtant pas complètement intuitifs, vous devrez rechercher sur internet des tutoriels pour bien comprendre.

Il vous faut un compte https://github.com (si vous en avez déjà un inutile d'en recréer un spécifiquement pour le TM, votre compte github vous représente comme individu qui peut avoir de nombreux projets différents).
