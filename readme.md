# TP 2 - Ludwig SILVAIN

## 1 - Les données

Il y a champs nom qui semble super-flu : n'est pas responsable de la survie ou non d'un passager. Cela serait plus un
facteur de sur-apprentissage. On constate la même chose pour le champs ticket.

- `Survived` : boolean pour savoir si le passager à survécu ou non (0 = mort, et 1 = survive)
- `Pclass` : Formule ( 1 = Premier classe, 2 = Seconde classe, et 3 = Troisième classe )
- `Name` : Nom du passager
- `Sex` : Sex du passger
- `Age` : Age du passager
- `SibSp` : Nombre de frères/soeurs/conjoints qui est abord du Titanic
- `Parch` : Nombre de parents/enfants qui est abord du Titanic
- `Ticket` : Numéro de ticket
- `Fare` : Tarif
- `Cabin` : Numéro de Cabine
- `Embarked` : Port d'embarquement (C = Cherbourg, Q = Queenstown, S = Southampton)

## 2 - Premier modéle de niveau 0

On utilise la validation croisée, car on essaye de compenser le faire de ne pas avoir un gros échantillon pour la
phase d'apprentissage.

On note que l'on dispose de 342 personnes qui ont survécu contre 549. On peut donc dire que l'échantillon est équilibré,
on n'a pas classe qui est fortement majoritaire au détriment de l'autre.

## 3 - Deuxième modéle

1) On remarque que la propriété de la troisième classe à une grosse importante par rapport à l'information de la seconde
   ou la première classe. Car pour la 1er et 2nd classe on note environ 50% de survivants et 50% de victimes, alors que
   pour la troisième classe, on observe un grand nombre de victimes. On peut donc en conclure que la propriété de la
   classe est important particulièrement dans le cas de la troisième classe.

2) On note qu'avec l'information de la classe, on obtient un meilleur score. Cela s'expliquer par le fait que cette
   nouvelle propriété permet une meilleure généralisation.

3) Cela confirme la précédente hypothèse, car on note que l'information ce la troisième classe à une influence
   négativement sur le fait de survivre.

## Partie 3 - Deuxième modèle

3) On note que l'information sur le sex à une très forte influence. On constate que le fait d'être une femme donne une
   plus grande chance survie contrairement au fait d'être un homme. On note également que grâce à cette nouvelle
   information, l'importance de la 1er classe augmente contrairement à celle de la 3ème classe qui elle diminue.

4) On observe que la probabilité de survivre est plus forte avec un âge compris entre 0 et 10ans. Alors qu'à l'inverse,
   il y a plus de chance de mourir lorsque l'on a entre 20 et 45 ans. Après cet âge, on a une probabilité de survivre
   d'environ 50%. On peut donc en déduire que l'introduction de cette nouvelle propriété va pouvoir influencer le modèle
   de facon positif.

6) Cela confirme l'hypothèse précédente, car on obtient un meilleur score. Cela peut également se vérifier un traçant
   les coefficients de la régression logistique, on note en effect que le fait d'être considéré comme un enfant à une
   très grande importance dans le fait de survivre ou non.

## Partie 4 - Troisiéme modéle

## Partie 5 - Selection de variable

    "#1 - brute force\n",
    "#2 - binariser toute les variables\n",
    "#3 - On fait comme pour Pclass pour toute les valeurs => One Hot Enconding\n",
    "#4 - \n",

## Partie 6 - Random Forest

# Partie 7 - Gradient Boosting

On note que l’on obtient un meilleur score avec Gradient Boosting qu’avec Random forest. Random Forest = Constuit tous
les abres puis répercuté les erreurs Gradient Boosting = arbre un a un => il répercute Cela s’explique que Gradient
Boosting utilise l’erreur des arbres qui la construit avant pour la répercutér sur ceux qu’il va constuire par la suite.