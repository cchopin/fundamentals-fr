L'UTF-8 est le roi actuel des codages.
Il est utilisé, par exemple, par la [grande majorité](https://en.wikipedia.org/wiki/Popularity_of_text_encodings) des sites Web.

Mais ce n'est pas le seul codage en usage.
En dehors du Web, d'autres codages sont très présents.
Pour diverses raisons techniques (discutables), les systèmes Windows utilisent souvent un autre codage Unicode : l'UTF-16.
Ce codage représente les mêmes caractères Unicode _avec d'autres valeurs d'octets_ !
Cela crée une grande confusion, et provoque parfois des failles de sécurité.

Une façon courante dont les confusions de codage mènent à des failles consiste à décoder incorrectement des données pour effectuer des vérifications de sécurité, puis à les décoder correctement (et différemment) plus tard, pour exécuter l'action sensible.
Si les vérifications de sécurité portent sur de mauvaises données, des données dangereuses peuvent passer inaperçues.

C'est le cas dans ce défi.
Est-il possible d'obtenir le flag ?

---
**Note du dojo :**
À cause d'un bogue d'affichage Unicode dans le terminal du bureau graphique, on recommande d'utiliser l'espace de travail VSCode pour ce défi (et pour tous les défis qui dépendent des emojis !).
