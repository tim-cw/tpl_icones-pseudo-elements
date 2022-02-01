[< Retour au readme](../readme.md)

# 7. Citations « big and bold »

Pour cet exercice, vous allez ajouter des guillemets de manière plus créative à une citation.

1. Styler le blockquote

   - Typographie: `50px`

2. Créer un `&::before`

   - Mettre le content à `"«"`
   - Mettre la typographie à `6em`
   - Mettre le line-height à`0` // _Pour enlever l'espace en haut et en bas d'un texte_
   - Mettre l'opacité à `0.05`
   - Postionnez `absolu` avec le top et le left à `0`

3. Ajouter le positionnement `relatif` au bon endroit

4. Créer un `&::after`
   - Mettre le content à `"»"`
   - Mettre la typographie à `6em`
   - Mettre le line-height à`0` // _Pour enlever l'espace en haut et en bas d'un texte_
   - Mettre l'opacité à `0.05`
   - Postionnez `absolu` avec le bottom et le right à `0`

C'est intéressant tout ça, mais que se passe-t-il si nous avons un site français/anglais? Il faudrait alterner entre » et ". Il y a un moyen super facile

5. Sur le `&::before` mettre le content à `open-quote`;
6. Sur le `&::after` mettre le content à `close-quote`;

Vous pouvez tester en changeant l'arribut lang de la balise `<html>` pour `en`.  
Presque fini, il reste juste à optimiser le code un petit peu.

7. Dans un sélecteur qui regroupe le `&::before` et le `&::after` y regrouper TOUTES les propriétés qui sont identique de l'étape 2-3 afin d'optimiser votre code.

[< Retour au readme](../readme.md)
