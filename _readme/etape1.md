[< Retour au readme](../readme.md)

# 1. Menu avec icône

Nous avons inclu un snippet pour l'utilisation du système d'icônes (icons.svg)

1. À l'aide du snippet tim-icons, ajoutez une icône en remplacement à `[logo]` devant le texte Grillz
2. Utilisez l'icône `grill` qui provient du fichier `grill.svg`
3. Il existe 5 _modifier_ pour gérer les tailles d'icônes qui sont définis dans `components/icons.scss`. Utilisez le _modifier_ `icon--md`
4. Créez un effet de survol où vous modifiez que la couleur sur `.nav__brand`. Ajoutez une transition pour adoucir l'effet sur la propriété couleur. Une transition de `.3s` sur la propriété `color` avec un `ease-out`.

Dans `icons.scss`, il est déclaré que la propriété `fill` (couleur pour les svg), utilise la valeur `currentColor`. Ce qui veut dire qu'il hérite de la couleur du parent (inherit). Le changement de couleur utilisera donc la valeur de `.nav__brand` incluant le changement causé par la transition css.
