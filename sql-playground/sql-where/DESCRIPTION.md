Toute base non triviale contient suffisamment de données pour qu'il faille être _sélectif_ (🥁) sur ce qu'on lit.
Heureusement, une requête `SELECT` peut être filtrée avec la clause `WHERE` !
Ce défi oblige à filtrer les données, car la base contient désormais beaucoup de données parasites !

Le défi renvoie vers la documentation SQLite de la clause WHERE, qu'il faut lire.
En résumé, pour commencer, on peut ajouter `WHERE condition` à la requête, où `condition` est une expression que l'on définit, comme `some_column < 10` (pour des comparaisons d'entiers), `some_column = 'pwn'` (pour des comparaisons de chaînes), ou une expression du même genre.

Il faut analyser le code pour comprendre ce qui distingue le flag des données parasites, puis filtrer dessus !
Indice : c'est la nouvelle colonne qui a été ajoutée.
Peut-on trouver le bon filtre pour ne garder que le flag ?
