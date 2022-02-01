[< Retour au readme](../readme.md)

# 4. Des boutons vraiment cool

<br>

## **Animation du bouton 1**

Pour cet exercice vous avez toutes les techniques nécessaires pour reproduire l'effet désiré. Voici quelques indications supplémentaires pour vous aider.

**_(Exercice de référence : Numéro 3, menu 2)_**

- Lorsque vous changerez le z-index à -1 sur votre before. Vous ne verrez plus votre masse. Vous devez mettre un z-index: 1 sur votre bouton pour que ça fonctionne.
- Les transitions sont de `.7s` sur la propriété `transform` avec un `ease-out`
- la couleur de la masse est blanche
- La masse est positonnée au départ complètement à gauche et avec un skew de `45deg` (transform, translate skew)

<br>

## **Animation du bouton 2**

Première étape créer la masse blanche en arrière

1. cibler le bouton avec le bon modificateur

   - Faire le code nécessaire pour y ajouter un `&::after`
     - largeur et hauteur `100%`
     - top et left : `5px`
     - background blanc
   - Sur le bouton le background est de #111

2. C'est normal si vous n'arrivez pas à mettre la bordure par dessus la masse blanche. La prochaine étape va régler tout ça

Pour animer la bordure qui descend, il faut prendre une chose en considération. Si vous animez directement la balise `<a>`, l'animation effectuera un _glitch_ lorsque la souris ne sera plus sur le lien. Vous devez suivre les prochaines étapes pour éviter ce problème.

3. Dans le HTML
   - Ajouter un span qui englobe le texte du lien
4. En CSS, lui ajouter une bordure de `2px`, `couleur primaire` et `solid`

Ce n'est pas encore parfait. La bordure est collée sur le texte et nous voyons encore la bordure autour du bouton. Pour cette raison il faut retirer la classe `button` de notre bouton. Des fois, il faut réaliser qu'un bouton est trop différent pour garder toute les propriétés initiales.

- Enlever la classe `button`
- Change le padding du span pour `5px 30px`
- Le mettre en display `block`

Votre mise en place est faite. Il reste seulement à ajouter de l'animation.

5. En `hover` sur le lien le span doit
   - Se déplacer de 5px vers le bas et 5px vers gauche(transform, transform)
6. Question d'ajouter de l'animation
   - Ajouter une transition de `.5s` sur la propriété `transform` avec un `ease-out`

<br>

## **Animation du bouton 3**

Pour cet exercice vous avez toutes les techniques nécessaires pour reproduire l'effet désiré. Voici quelques indications supplémentaires pour vous aider.

**_(Exercice de référence : Numéro 3, menu 2 et 4)_**

- Lorsque vous changerez le z-index à -1 sur votre before. Vous ne verrez plus votre masse. Vous devez mettre un z-index: 1 sur votre bouton pour que ça fonctionne.
- Les transitions sont de `.2s` sur la propriété `transform` avec un `ease-out` ou `ease-in`
- la couleur de la masse et de la bordure est blanche

<br>

## **Animation du bouton 4**

Pour cet exercice vous avez toutes les techniques nécessaires pour reproduire l'effet désiré. Voici quelques indications supplémentaires pour vous aidez.

- Ajouter l'icône `arrow-right` suite au texte
- Padding modifié sur le bouton : `5px 30px`;
- Une technique pour centrer un élement en position absolu comme une icône
  - top: `50%` et left: `50%`
  - transform: `translateY(-50%, -50%)`
- L'icône et le span se déplacent de `-10px` sur l'axe des X
- Les transitions sont de `.3s` sur la propriété `transform` avec un `ease-out`

[< Retour au readme](../readme.md)
