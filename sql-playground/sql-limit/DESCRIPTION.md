Jusqu'ici, la clause `WHERE` suffisait à réduire le résultat à exactement une ligne, mais dans ce défi, on a retiré les étiquettes de flag qui permettaient de filtrer les faux flags !
Heureusement, les requêtes SQL simples renvoient en général les données dans l'ordre où elles ont été insérées dans la base, et le vrai flag a été inséré avant les faux flags (mais après certaines données parasites).
Il suffit de limiter la requête à `1` seul résultat avec `LIMIT`, et ce résultat doit être le flag !
Le défi renvoie vers la documentation de `LIMIT` si besoin !
