============= DOCUMENTATION BRIEF 2 ===============


1 : À quoi sert le fichier responsive.css ?
Il adapte la mise en page du site aux écrans plus larges que le téléphone : tablette, ordinateur portable et grand écran. Il ne contient que ce qui change par rapport à la version mobile.

2 : Que veut dire « mobile first » ?
Le site est d'abord écrit pour le téléphone dans styles.css. Ensuite, responsive.css ajoute des règles pour les écrans plus larges. On n'écrit une règle que là où le rendu change.

3 : Quels sont les points de rupture ?
768px pour la tablette, 1024px pour l'ordinateur portable et 1280px pour le grand écran. Ils s'écrivent @media (min-width: 768px), @media (min-width: 1024px) et @media (min-width: 1280px).

4 :Que signifie min-width: 768px ?
À partir de 768px de large, et au-delà. Les règles du bloc s'appliquent dès que la fenêtre atteint 768px.

5 : Les trois blocs @media s'additionnent-ils ?
Oui. En dessous de 768px, aucun bloc ne s'applique. Entre 768px et 1023px, le bloc tablette s'applique. Entre 1024px et 1279px, les blocs tablette et portable s'appliquent. À partir de 1280px, les trois s'appliquent. Si un bloc plus large redéfinit une propriété, c'est lui qui gagne.

6 :Pourquoi les blocs 1024 et 1280 sont-ils plus courts que celui de 768 ?
Parce qu'ils héritent du bloc précédent. Ils ne contiennent que ce qui change : une taille de titre, un nombre de colonnes, une marge.

7 : Qu'est-ce que --gutter ?
C'est la marge à gauche et à droite de la page. Elle est utilisée pour le menu, le hero, les cartes, l'atelier, les avis et le CTA. Sa valeur est de 24px sur mobile, 20px en tablette, 24px en portable et 32px en grand écran.

8 :Qu'est-ce que --nav-h ?
La hauteur de la barre de navigation, soit 76px. Elle sert à calculer la hauteur du hero : calc(100svh - var(--nav-h)).

9 : Quelles variables de couleur le fichier utilise-t-il ?
Quatre variables venant de variables.css : --raw-green-650 pour le fond de la section atelier, --raw-green-900 pour le bandeau foncé derrière le CTA, --raw-surface-mint pour le fond du bloc texte de l'atelier et --raw-terracotta-720 pour le petit titre de l'en-tête du manifeste.


10 : Qu'est-ce qu'une media query ?
Une condition qui applique des règles seulement si l'écran correspond. Par exemple, @media (min-width: 768px) { ... } n'applique son contenu qu'à partir de 768px de large.

11 :À quoi servent var(), calc() et repeat() ?
var() lit une variable, par exemple padding: 0 var(--gutter). calc() calcule une valeur, par exemple calc(100svh - var(--nav-h)). repeat() répète une colonne de grille, par exemple repeat(2, 1fr) pour deux colonnes égales.

12 :Quelles unités le fichier utilise-t-il ?
Les pixels (`px`), les pourcentages (`%`), `fr` (une part de l'espace disponible dans une grille), `em` (relatif à la taille de la police), `vh` (1% de la hauteur de la fenêtre), `svh` (1% de la hauteur visible de la fenêtre) et `vmax` (1% de la plus grande dimension de la fenêtre).

13 :Que veut dire `1fr` ? Que veut dire `repeat(3, 1fr)` ?
fr est une fraction de l'espace disponible. 1fr 1fr donne deux colonnes égales, repeat(3, 1fr) en donne trois, et 1.15fr 1fr donne une première colonne un peu plus large que la deuxième.

14 : Quelles sont les principales propriétés Flexbox ?
À mettre sur un parent en display: flex. flex-direction choisit row (en ligne) ou column (en colonne). flex-wrap: wrap autorise le retour à la ligne. flex: 1 donne à l'élément une part égale de l'espace libre. justify-content aligne sur l'axe principal et align-items sur l'axe secondaire. gap fixe l'espace entre les éléments. order: -1 place l'élément avant les autres.


15 :Quelles sont les propriétés Grid 
À mettre sur un parent en display: grid. grid-template-columns définit les colonnes. gap et column-gap fixent l'espace entre les lignes et les colonnes. grid-column place un élément dans une colonne : 1 / -1 signifie toute la largeur. grid-row le place dans une ligne : 2 / span 4 signifie quatre lignes à partir de la ligne 2. justify-self et align-self alignent un seul élément.

16 : Quelle est la différence entre align-items et align-content 
align-items aligne chaque élément dans sa cellule. align-content aligne toute la grille dans son conteneur.

17 : les sélecteurs :
Les classes (`.`), les identifiants (`#`), les groupes séparés par des virgules (`.p1, .p2, .p3`), les descendants (`.card .h3`), les enfants directs avec `>`  et `:nth-of-type()` (`body > article:nth-of-type(2)` pour le deuxième article enfant du `body`).




