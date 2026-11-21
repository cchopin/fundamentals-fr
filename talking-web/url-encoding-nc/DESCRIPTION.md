Se rappeler que les requêtes HTTP contiennent des champs séparés par des espaces ?
Par exemple : `GET /solve HTTP/1.1`.
Et si le chemin (à la place de `/solve`) contient des espaces ?
C'est tout à fait possible, puisque ces chemins désignent souvent des dossiers, et que les noms de dossiers peuvent contenir des espaces !

Livrées à elles-mêmes, les espaces casseraient la requête HTTP.
Un serveur qui tente de comprendre `GET /solve my challenge HTTP/1.1` peut s'en sortir, mais un serveur qui lirait un mot à la fois lirait `my` à la place de `HTTP/1.1`, et paniquerait !

Pour éviter ces situations, les URL sont _encodées_ avec l'[encodage d'URL (URL Encoding)](https://en.wikipedia.org/wiki/Percent-encoding).
C'est un encodage simple, comparé à ce que l'on a vu dans [Traiter les données (Dealing with Data)](https://pwn.college/fundamentals-fr/data-dealings).
Chaque caractère délicat (comme l'espace) est simplement écrit en hexadécimal, précédé d'un `%`.
Comme le `%` lui-même devient alors un caractère délicat, il doit aussi être encodé.
Dans l'exemple ci-dessus, `/solve my challenge` devient `/solve%20my%20challenge`, car la valeur hexadécimale du caractère espace ASCII est `0x20`.

Pratiquons maintenant.
Des espaces ont été placés dans les chemins.
Peut-on encore obtenir le flag ?

----
**INFO :**
Il faut aussi encoder les URL avec curl, de la même façon (même si l'exercice ne l'impose pas).
La bibliothèque requests de Python, en revanche, encode automatiquement les URL. Très pratique !
