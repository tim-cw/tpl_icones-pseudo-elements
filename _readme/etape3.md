[< Retour au readme](../readme.md)

# 3. Un menu plusssse intéressant

<br>

## **Animation du logo**

1. À l'aide du snippet tim-icons, ajoutez une icône en remplacement à `[logo]` devant le texte Grillz
2. Cibler `nav__brand`
   - Ajoutez une transition de `.3s` sur la propriété `all` avec un `ease-out` sur lui-même et sur `.icon`
   - En `hover` sur le lien
     - Le lien doit rapetisser de `.99` et faire une translation sur l'axe des Y de `3px` (transform, scale, translate)
     - Changer de couleur pour la couleur-primaire
   - En `hover` sur le lien, l'icône doit
     - Grossir de `1.2` et faire une translation sur l'axe des Y de `-1px`

<br>

## **Animation du Menu 1**

<br>
Première étape, créez la ligne sous le menu

1. cibler `nav__item`
   - Faites en sorte d'y ajouter un `&::after`
     - Lui ajouter la propriété essentielle pour qu'un pseudo élément fonctionne
     - Ajoutez une hauteur de `4px`
     - Ajoutez une largeur de `100%`
     - La ligne ne devrait toujours pas apparaître. La mettre en display `block` devrait régler le problème

<br>

La ligne prend plus d'espace que le texte. C'est parce qu'il y a du padding sur nos `nav__item`. Vous allez faire en sorte qu'elle soit la bonne largeur.

2. Dans votre sélecteur de after
   - Modifier la largeur `100%` pour un calc
     - width: `calc(100% - 20px)` _pourquoi 20px? C'est la padding de gauche additionné au padding de droite_

<br>
La ligne prend maintenant toute l'espace, mais n'est pas bien alignée sous le texte. Le positionnement absolu à la rescousse.

3. Dans votre sélecteur de after
   - Faire en sorte qu'il soit positionné `absolu`
   - Vous pouvez enlever le `display: block`, il n'est plus nécessaire
   - Mettre dans le `bas 0px`
   - Mettre à `gauche 10px`
4. Il faut mettre un position `relative` sur le bon élément pour que la ligne soit à la bonne place
5. Un lien est un élément en ligne, donc il n'est pas possible de jouer sur les hauteurs et margin. Il faut donc ajouter un `display: flex` sur le `nav__item`

<br>
Vous allez maintenant créer l'état d'hover. Il faut donc faire en sorte de cacher la ligne et la faire apparaitre lors du survol.

6. Pour cacher la ligne
   - cibler le pseudo élément after
     - Faire une translation sur l'axe des Y de `100%` (transform, translate).
     - La ligne va descendre de toute sa hauteur en bas du `nav__item`

<br>

La ligne est maintenant plus basse, mais est toujours visible. Il faut mettre un `overflow: hidden` et un `display: flex` sur le `nav__item`. De cette manière tous ce qui ne se trouve pas à l'intérieur de la boîte de `nav__item` ne sera pas visible. Il ne reste plus qu'à la faire remonter lorsqu'on survol le lien.

7. En `hover` sur le lien le background doit
   - Remettre à sa valeur initiale la translation sur l'axe des Y, soit à `0`
8. Question d'ajouter de l'animation
   - Ajoutez une transition de `.3s` sur la propriété `transform` avec un `ease-out` sur le pseudo élément

<br>

Voilà! Dernière chose à modifier pour ce numéro, est de changer le sélecteur `nav__item` pour ciber le modificateur `nav__item--fat-bottom`. Ainsi, seulement le premier menu aurait cet effet.

<br>

## **Animation du Menu 2**

<br>
Première étape créer la ligne sous le menu

1. cibler le deuxième menu avec le bon modificateur
   - Faite en sorte d'y ajouter un `&::before`
     - Lui ajouter la propriété essentielle pour qu'un pseudo élément fonctionne
     - Ajouter un backgroud de la `couleur primaire`
     - Ajouter une hauteur de `100%`
     - Ajouter une largeur de `100%`
     - La masse d'arrière-plan ne devrait toujours pas apparaître, mettre en display `block` devrait régler le problème

<br>

La masse d'arrière-plan prend plus maintenant trop d'espace et n'est pas derrière le texte. Le positionnement absolu à la rescousse.

2. Dans votre sélecteur de before
   - Faire en sorte qu'il soit positionné `absolu`
   - Vous pouvez enlever le `display: block`, il n'est plus nécessaire
   - Mettre dans le `top 0px`
   - Mettre à `gauche 10px`
   - Pour mettre la masse derrière le texte il faut lui changer son `z-index` pour `-1`
3. Il faut mettre un position `relative` sur le bon élément pour que la ligne soit à la bonne place

<br>
Vous allez maintenant créer l'état d'hover. Il faut donc faire en sorte de cacher la masse et la faire apparaitre lors du survol.

4. Pour cacher la masse
   - cibler le pseudo élément before
     - Faire rapetisser sur l'axe des Y à `0` (transform, scale).

<br>
La ligne est maintenant disparue, il ne reste plus qu'à la faire apparaitre lorsqu'on survol le lien.

5. En `hover` sur le lien le before doit
   - Revenir à sa grosseur orginal de 1 (transform, scale)
6. Question d'ajouter de l'animation
   - Ajouter une transition de `.3s` sur la propriété `transform` avec un `ease-out` sur le pseudo élément

<br>

## **Animation du Menu 3**

<br>
Première étape créer la copie du texte

1. cibler le troisième menu avec le bon modificateur
   - Faite en sorte d'y ajouter un `&::after`
     - Vous êtes maintenant habitué d'ajouter `content:""`, au lieu des guillemets vide vous allez lui donner la valeur d'un attribut
       - ajouter dans le HTML un `data-hover-content="Menu 3"`
       - Ajuster la valeur de la propriété content pour : `attr(data-hover-content)`;

<br>

La nouveau texte est maintenant juste à côté de l'autre menu. Le positionnement absolu à la rescousse.

2. Dans votre sélecteur d'after
   - Faire en sorte qu'il soit positionné `absolu`
   - Mettre dans le `top 0px`
   - Mettre à `gauche 10px` _10px = le padding gauche du menu_
3. Il faut mettre un position `relative` sur le bon élément pour que la ligne soit à la bonne place

<br>
Vous avez maintenant créé l'état d'hover. Il faut donc faire en sorte de mettre le texte du pseudp sous le texte courant et le faire apparaitre lors du survol.

4. Pour cacher la masse
   - cibler le pseudo élément after
     - Faire une translation sur l'axe des Y de `100%` (transform, translate) pour le pousser à l'extérieur vers le bas.

<br>

Les texte est maintenant sous le menu, mais toujours visible. Il faut mettre un `overflow: hidden` et un `display: flex` sur votre lien. De cette manière tout ce qui ne se trouve pas à l'intérieur de la boîte du menu ne sera pas visible. Il ne reste plus qu'à la faire remonter lorsqu'on survol le lien.

5. En `hover` sur le lien l'after doit
   - Revenir à sa translation orginal de 0 (transform, translate)
6. Question d'ajouter de l'animation
   - Ajouter une transition de `.2s` sur la propriété `transform` avec un `ease-out` sur le pseudo élément

<br>

Ok c'est cool, mais le texte d'origine ne bouge pas. Il n'est pas possible de jouer avec le texte brut à l'intérieur d'un `<a>`. vous allez ajouter un `span` autour du texte

7. En `hover` sur le lien le span doit
   - Faire une translation sur l'axe des Y de `-100%` (transform, translate) pour l'envoyer vers le haut
8. Question d'ajouter de l'animation
   - Ajouter une transition de `.2s` sur la propriété `transform` avec un `ease-out` sur le span

<br>

## **Animation du Menu 4**

<br>
Première étape créer la ligne sous le menu

1. Refaire les étapes de l'animation du menu 1 pour avoir une ligne de `2px` de hauteur dans le bas du menu 4

<br>
Vous avez maintenant créé l'état d'hover. Il faut donc faire en sorte de cacher la ligne et la faire apparaitre lors du survol.

2. Pour cacher la ligne
   - cibler le pseudo élément after
     - Faire rapetisser sur l'axe des X de `0` (transform, scale).

<br>

La ligne n'est plus visible. Il ne reste plus qu'à la faire apparaitre au survol.

3. En `hover` sur le lien, le `&::after` doit
   - Revenir à sa grandeur initiale sur l'axe des Y, soit `1` (transform, scale).
4. Question d'ajouter de l'animation
   - Ajoutez une transition de `.3s` sur la propriété `transform` avec un `ease-out` sur le pseudo élément

<br>
Vous avez créé un effet intéressant. Est-ce que vous pouvez faire mieux? Vous allez faire arriver la ligne de la gauche au lieu du centre.

5. Dans votre règle du `::after`
   - Changer l'origine de la transformation pour gauche `transform-origin: left`

<br>
Ce n'est pas encore parfait. Il serait bien que lorsque vous ne survolez plus, la ligne parte vers la droite.

5. Dans votre règle du `::after`
   - Changez l'origine de la transformation pour droite `transform-origin: right`
   - Ajouter une transition de `.3s` sur la propriété `transform` avec un `ease-in`
6. Dans votre règle du survol du lien, modifier le `::after` pour:
   - Changez l'origine de la transformation pour droite `transform-origin: left`
   - Ajouter une transition de `.5s` sur la propriété `transform` avec un `ease-out`

Voilà! Maintenant lorsque vous survolez la transition se fait de la gauche vers la droite et lorsque vous ne survolez plus elle quitte vers la droite. Il est primordial de comprendre que lorsqu'on mets des propriétés dans un :hover, elles sont appliquées seulement lors du survol sinon reprennent les valeurs qui ne sont pas mis en survol.

<br>

## **Animation du Menu 5**

Pour ce numéro vous aurez quelques indications pour créer les deux lignes, mais vous devrez recréer l'animation avec les techniques précédentes.

1. Vous devez utiliser deux pseudo-éléments soit le before et le after pour créer l'effet
   - La largeur des deux pseudos devrait être de `calc(50% - 10px)` _// 10px égal la valeur de padding d'un côté_
   - Un pseudo doit être à gauche et l'autre à droite
2. Ensuite appliquer la technique du menu 4 pour créer l'effet de gauche à droite (before) et droite à gauche (after).

<br>

## **Animation du bouton**

Vous avez toutes les techniques pour créer cet effet, voici quelques informations pour le recréer.

- Ajoutez l'icône `arrow` suite au texte
- Les transitions sont de `.3s` sur la propriété `all` avec un `ease-out`
- la couleur d'hover est blanche
- L'icône se déplace vers la droite de `4px` et rotation de `-5deg`

[< Retour au readme](../readme.md)
