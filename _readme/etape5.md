[< Retour au readme](../readme.md)

# 5. Cartes interactives

<br>

La carte (cards) est une composante qui peut visuellement être très intéressante pour regrouper un « extrait » de contenu de façon logique. Une carte est généralement un élément cliquable qui nous emmène sur une autre page ou déclanche une action afin d'afficher de l'information complémentaire. Nous allons donc la rendre cliquable et visuellement intéressante.

Vous aller travailler sur une seule carte et ensuite, vous pourrez la dupliquer pour reproduire les colonnes.

1. Vous aller créer une disposition de 3 colonnes pour y mettre nos cartes, créez un div `.cards` (au pluriel hin.. vous en aurez plusieurs et il contiendra des `.card`).
   - Cards devra utiliser la grille css pour 3 colones avec un espacement de 20px entre ses enfants

<br>

## **Maintenant, créez la structure d'une carte à l'aide de emmet**

`.card>.card__media+.card__content>span.card__surtitle{catégorie}+h2.card__title{titre}`

Le fait d'avoir un conteneur pour l'image et un autre pour le contenu nous permet plus de flexibilité au niveau des animations. Pensez à toujours utiliser une structure du genre pour une carte avec image.
Vous aller travailler sur le contenu html d'une carte, ensuite vous la rendrez plus jolie.

2. Mettez l'image utilisant `ski1.jpg` dans `.media__container`.
   - Ajustez ensuite le contenu alternatif pour quelque chose qui fait du sens.

<br>

## **Le contenu**

3. Positionnez le `.card__container` en absolu de sorte à ce qu'il prenne tout l'espace disponible

   - Absolu, top/left: 0, width/height: 100%

4. Vous devez mettre un position `relative` sur `.card` pour contraindre le `.card__content` qui est maintenant en absolu.

   - Mettez aussi tout de suite un color: `white` sur `.card`

5. Le contenu est collé dans `.card__content`, ajoutez un `padding` de `20px`.

   - Pensez à utiliser les variables de spacing pour avoir une uniformité dans les espacements, jettez un oeil dans `settings/spacing.scss`, il en existe un de 20px.

6. Vosu devez espacer le `surtitle` et le `title` sur la carte.

   - Dans `.card__content` :

     - flex en direction column
     - Mettez de `l'espace-entre` les éléments pour les repousser

<br>

## **Le surtitre**

Vous allez maintenant créer un surtitre ou l'espace à droite du texte sera comblée par un trait (pseudo-element) qui va s'étendre jusqu'à l'extrémité de la card

7. Créez un style pour `.card__surtitle`
   - typo, taille de `20px`, poids de `500` et letter-spacing de `.2em` et mettre en majuscule

Trouvez-vous que le texte est illisible? Vous allez régler ça avec un pseudo-element dans `.card__media`

8. Créez un sélecteur `.card__media` et à l'intérieur, imbriquez un `&::after` qui vous servira de trame pour foncir notre image.
   - Ajoutez la propriété essentielle pour un pseudo-element
   - Il doit couvrir tout l'espace :
     - position `absolute`, top/left: `0`, width/height: `100%
     - mettez une couleur d'arrière-plan noire à 20% d'opacité

Regardez en bas de l'image dans votre navigateur, le `&::before` dépasse un peu. Mettez un display `block` sur l'image dans votre sélecteur `.card__media` afin de régler ce problème.

<br>

**Retour à `.card__surtitle` et au trait que vous allez ajouter**

9. Créez un pseudo `&::after` dans `.card__surtitle`
   - Ajoutez la propriété essentielle pour un pseudo-element
   - arrière-plan `blanc`, hauteur de `2px` et largeur de `100%`, display `block`

La ligne est sous le surtitre, vous devez la mettre à droite en utilisant du flex.

10. Mettez du flex sur `.card__surtitle`.

- `align-items` pour la centrer verticalement avec le texte
- Mettez un espace de `20px` entre la ligne et le texte à l'aide de `gap: 20px;`
- Maintenant qu'on a mis du flex, le display `block` sur le `&::after` n'est plus nécessaire

11. La ligne doit aller jusqu'à l'extrêmité de le carte, mais le padding sur `.card__content` vous en empêche

- Mettez une marge négative à droite sur le `&::after` équivalente au padding que vous avez mis dans votre carte

<br>

## **Le titre**

12. Créez un sélecteur `.card__title`.

- couleur `white
- enlevez les marges pour qu'il soit collé sur le padding de la carte

13. À l'intérieur du h2, on va ajouter l'icône de la flèche `arrow-right-square` à l'aide de la technique des icônes.

14. Vous devez aligner l'icône toujours à droite, en bas dans le titre.

- Sur `.card__title`, display `flex`, align-items `flex-end`
- Pour espacer un peu l'icône du texte, ajoutez aussi `gap: 20px`

<br>

## **Retour à l'image**

Vous allez préparer l'image dans le but de l'animer

15. Dans `.card__media`, vous aller faire grossir l'image sur le survol et faire en sorte qu'elle ne s'affiche pas a l'extérieur de la carte

- position `relative` et overflow `hidden`

16. Vous avez imbriquez un sélecteur img dans `.card__media`, dans le but de fixer l'image pour l'animer, ajoutez-y :

- width/height `100%`, object-fit `cover`

17. Vous devez changer le ratio de la carte pour qu'elle soit un peu moins haute.

- Toujours dans `img` sous `.card__media` :
  - Afin de forcer un ratio constant à l'image, on va ajouter la déclaration : `aspect-ratio: 3/4;`

<br>

## **Passons aux choses sérieuses.. L'animation**

18. Vous devez faire grossir l'image lors d'un survol de la souris.

- Dans `.card`, ajoutez un sélecteur `&:hover .card__media img{}` et faire grossir légèrement l'image avec `transform: scale(1.1);`

Passez votre souris sur la carte, c'est un peu sec. Ajoutez une transition.

19. Dans le sélecteur `img` de `.card__media` :

- Ajoutez `transition: transform 0.6s ease-in-out;` afin de créer une transition entre le scale de 1 à 1.1

Maintenant, sur le survol de la carte, il faut diminuer l'opacité de notre trame noire pour mieux voir l'image

20. Dans `.card`, ajoutez un sélecteur `&:hover .card__media::after {}` où il faut diminuer la valeur de l'alpha de l'arrière-plan `background: rgba(0, 0, 0, 0.2);`

Passez votre souris sur la carte, c'est un peu sec. Ajoutez une transition.

21. Dans le sélecteur `&::after` de `.card__media` :

- Ajoutez `transition: background 0.6s ease-in-out;` afin de créer une transition entre le scale de 1 à 1.1

Finalement, il faut faire bouger l'icône vers la droite, toujours au survol.

22. Dans `.card`, ajoutez un sélecteur `&:hover .card__title .icon` où il faut diminuer la valeur de l'alpha de notre arrière-plan `background: rgba(0, 0, 0, 0.2);`

Passez votre souris sur la carte, c'est un peu sec. Ajoutons une transition.

21. Dans le sélecteur `&::after` de `.card__media` :

Bon, c'est encore sec non? Où devrait-on mettre la dernière transition pour que ça soit plus smooth?

22. À vous de choisir

[< Retour au readme](../readme.md)
