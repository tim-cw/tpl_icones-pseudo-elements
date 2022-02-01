[< Retour au readme](../readme.md)

# 6. Liens identifiés

L'objectif de cet exercice est de mettre en application une règle importante d'accessibilité. Lorsque nous avons des liens externe ou des liens de téléchargement pdf, il est important d'afficher une icône à la fin du lien pour aider à la compréhension.

Il faut réfléchir à notre structure actuelle. `On ne veut pas ajouter dans le HTML` une icône dans tous les liens de la page lorsque c'est nécessaire. Nous voulons avoir une manière automatique d'y ajouter l'icône appropriée. Les étapes suivante vous guideront dans l'accomplissement de ce numéro.

1. Changer les puces pour avoir des carré à la place
2. Faire en sorte que les liens à l'intérieur de la liste ajoutent un souligné en hover

Vous devrez utiliser des [sélecteurs d'attribut](https://developer.mozilla.org/fr/docs/Web/CSS/Attribute_selectors) pour réussir les prochaines étapes

3. Cibler les liens qui commence par `http`
   - Faire en sorte d'ajouter un `&::after`
     - Ajouter la propriété essentielle pour un pseudo élément
     - Mettre un background-image vers l'icône `external.svg` qui est dans le dossier `assets/icons/`
     - Une hauteur et une largeur de `1em` _// Ceci fera en sorte que l'icône ait la largeur/hauteur de la typographie_
     - background-size: `100%`
     - Une marge à gauche de `10px`
4. Pour changer la hauteur d'un pseudo élément qui est de type inline
   . Vous devez faire en sorte que le pseudo élément ait les avantages d'un élément inline et block. L'avantage du inline permet à l'icône de suivre le texte et l'avantage du block permet de changer la hauteur.
5. Cibler les liens qui se terminent par `.pdf`
   - Répéter les propriétés de l'étape #3
   - Mettre un background-image vers l'icône `pdf.svg` qui est dans le dossier `assets/icons/`

[< Retour au readme](../readme.md)
