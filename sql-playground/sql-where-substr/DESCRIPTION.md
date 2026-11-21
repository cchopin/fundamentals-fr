Passons à un filtrage plus avancé.
Dans ce défi, l'étiquette du flag a été supprimée : il faut filtrer sur les valeurs réelles des données du flag !
Heureusement, `SQLite` (et, de façon générale, tous les moteurs SQL) fournit des fonctions pour manipuler les chaînes, et ce défi utilise la fonction `substr`.
`substr(some_column, start, length)` extrait `length` caractères à partir de `start` de la colonne `some_column` (le premier caractère est en position `1`, et non `0` comme dans un langage raisonnable).
On peut utiliser le résultat partout où la requête accepte des expressions, par exemple dans la clause `WHERE`, pour comparer la valeur obtenue à une chaîne, comme dans le défi précédent !
