Les codages ASCII et UTF-8 sont destinés à des données très précises : du texte, ou des caractères qui s'en approchent.
Le codage hexadécimal est plus général : on peut l'appliquer à n'importe quelles données.
On utilise un codage comme l'hexadécimal pour transférer des informations par un support où il est difficile d'écrire du code binaire arbitraire, comme une feuille de papier ou certains protocoles de communication.
Il est toutefois terriblement inefficace : il _double_ la taille des données, puisqu'il produit deux chiffres hexadécimaux ASCII pour chaque octet !

L'hexadécimal est inefficace pour la même raison qu'il est pratique : chaque chiffre ne porte que 4 bits, et comme chaque chiffre en sortie occupe 8 bits à l'affichage (en ASCII), la taille des données double.
Heureusement, on peut rendre un codage plus efficace en augmentant le nombre de bits transportés par caractère de sortie.

Le nom « base64 » vient du fait que chaque caractère de sortie est choisi parmi 64 symboles.
Ces symboles peuvent varier, mais le codage base64 standard utilise un « alphabet » composé des lettres majuscules de `A` à `Z`, des lettres minuscules de `a` à `z`, des chiffres de `0` à `9`, et des symboles `+` et `/`.
On obtient ainsi 64 symboles en sortie, et chacun peut coder `2**6` (2 puissance 6) valeurs d'entrée possibles, soit 6 bits de données.
Pour coder un seul octet (8 bits) en entrée, il faut donc plus d'un caractère base64 en sortie.
Il en faut même _deux_ : un qui code les 6 premiers bits, et un qui code les 2 restants (4 bits de ce second caractère restent inutilisés).
Pour marquer ces bits inutilisés, les données en base64 ajoutent un `=` pour chaque tranche de deux bits inutilisés.
Par exemple :

```console
hacker@dojo:~$ echo -n A | base64
QQ==
hacker@dojo:~$ echo -n AA | base64
QUE=
hacker@dojo:~$ echo -n AAA | base64
QUFB
hacker@dojo:~$ echo -n AAAA | base64
QUFBQQ==
hacker@dojo:~$
```

Comme on le voit, 3 octets (`3*8 == 24` bits) se codent exactement en 4 caractères base64 (`4*6 == 24` bits).

Le base64 est un codage populaire, car il peut représenter n'importe quelles données sans utiliser de caractères délicats comme les retours à la ligne, les espaces, les guillemets, les points-virgules ou les caractères spéciaux non imprimables, et ainsi de suite.
Ces caractères peuvent poser des problèmes dans certains contextes, et coder les données en base64 évite proprement ces difficultés.

Les autres bases déjà vues sont la base 2 (le binaire) et la base 16 (l'hexadécimal) !

Maintenant, il faut décoder son chemin jusqu'au flag !

----
**Indice :**
On peut utiliser le module `base64` de Python (attention : les fonctions de décodage de ce module consomment et renvoient des bytes Python) ou l'utilitaire en ligne de commande `base64`.

**Anecdote :**
Le flag `pwn.college{FLAG}` est lui-même un texte chiffré encodé en base64.
On est bien engagé pour être capable de construire quelque chose comme le dojo !
