Maintenant, les choses se compliquent.
On a peut-être remarqué : les constantes de mot de passe de ce module sont précédées de la lettre `b`.
Python dispose de deux types de constantes proches des chaînes : les `str`ings (écrites `"asdf"`) et les `bytes` (écrits `b"asdf"`).
Parlons des `bytes` dans ce niveau.

Les `bytes` sont ce qui est réellement stocké dans la mémoire de l'ordinateur.
Comme on le sait, les ordinateurs pensent en binaire : une suite de uns et de zéros.
Pour des raisons historiques, on regroupe ces uns et ces zéros (les « bits ») par paquets de 8, et chaque paquet de 8 s'appelle un « octet » (byte).
Ce nombre est purement arbitraire : les premiers ordinateurs (avant les années 1960 environ) n'avaient pas ce regroupement, ou en avaient d'autres, tout aussi arbitraires.
On peut imaginer un univers parallèle où un octet compterait 16, 32 bits ou n'importe quel autre nombre (même si, pour des raisons mathématiques, il restera probablement une puissance de 2).

Un seul bit peut représenter deux valeurs (`0` et `1`), deux bits peuvent en représenter quatre (`00`, `01`, `10` et `11`), trois bits en représentent huit (`000`, `001`, `010`, `011`, `100`, `101`, `110` et `111`), et quatre bits en représentent seize.
En comparaison, un chiffre décimal peut représenter 10 valeurs (de `0` à `9`).
Dix valeurs correspondent à environ `log2(10) == 3.3219...` bits, ce qui donne des situations étranges : le binaire `1001` vaut le décimal `9`, mais le binaire `1100` (toujours 4 chiffres binaires) vaut `12` (_deux_ chiffres décimaux !).
Autrement dit, le décimal ne possède pas de _frontières de bits_ nettes.

L'absence de frontières de bits rend le raisonnement sur la relation entre décimal et binaire complexe.
Par exemple, il est difficile de convertir de tête des nombres entre décimal et binaire : on peut établir que `97` vaut `110001`, mais ce n'est pas immédiatement évident.

Il est beaucoup plus facile de convertir de tête entre des bases dont les chiffres s'alignent mieux.
Par exemple, un seul chiffre hexadécimal (base 16) peut représenter 16 valeurs (`0`, `1`, `2`, `3`, `4`, `5`, `6`, `7`, `8`, `9`, `a`, `b`, `c`, `d`, `e`, `f`) : le même nombre de valeurs que quatre chiffres binaires !
Cela permet une correspondance très simple :

| Hex | Binaire | Décimal |
|-----|---------|---------|
| `0` | `0000` | `0`     |
| `1` | `0001` | `1`     |
| `2` | `0010` | `2`     |
| `3` | `0011` | `3`     |
| `4` | `0100` | `4`     |
| `5` | `0101` | `5`     |
| `6` | `0110` | `6`     |
| `7` | `0111` | `7`     |
| `8` | `1000` | `8`     |
| `9` | `1001` | `9`     |
| `a` | `1010` | `10`    |
| `b` | `1011` | `11`    |
| `c` | `1100` | `12`    |
| `d` | `1101` | `13`    |
| `e` | `1110` | `14`    |
| `f` | `1111` | `15`    |

Cette correspondance entre un chiffre hexadécimal et 4 bits se retient facilement (le plus important est de retenir `1`, `2`, `4` et `8`, et l'on en déduit rapidement le reste).
Mieux encore, deux chiffres hexadécimaux font **8** bits, soit un octet !
Contrairement au décimal, où il faudrait retenir 16 correspondances pour 4 bits et 256 pour 8 bits, avec l'hexadécimal on retient les 16 correspondances pour 4 bits, et il suffit de les accoler pour obtenir 8 bits, puisqu'il s'agit simplement de deux chiffres hexadécimaux juxtaposés !
Quelques exemples :

| Hex  | Binaire     | Décimal |
|------|-------------|---------|
| `00` | `0000 0000` | `0`     |
| `0e` | `0000 1110` | `14`    |
| `3e` | `0011 1110` | `62`    |
| `e3` | `1110 0011` | `227`   |
| `ee` | `1110 1110` | `238`   |

Le charme de la chose apparaît mieux ici.
Il devient encore plus évident dès qu'on dépasse un octet en entrée, mais on le découvrira dans les défis suivants !

Parlons maintenant de la notation.
Comment distinguer `11` en décimal, `11` en binaire (qui vaut `3` en décimal) et `11` en hexadécimal (qui vaut `17` en décimal) ?
Pour les constantes numériques, la notation de Python place `0b` devant les nombres binaires, `0x` devant les nombres hexadécimaux, et laisse les nombres décimaux tels quels : on a donc `11 == 0b1011 == 0xb`, `3 == 0b11 == 0x3` et `17 == 0b10001 == 0x11`.
Mais pour les `bytes`, comme dans ce défi, on peut les écrire avec des _séquences d'échappement_.
La séquence d'échappement commence par `\x` et est suivie de deux chiffres hexadécimaux, ce qui place dans la constante `bytes` un octet ayant cette valeur !

Armé de ces connaissances, il ne reste plus qu'à coder en hexadécimal pour obtenir le flag !

---
**Anecdotes :**
Quelques autres particularités de Python qui peuvent être utiles :

- Si l'on fait `print(n)` sur un nombre, ou si on le convertit en chaîne avec `str(n)`, le nombre s'affiche en base 10.
- On obtient la représentation hexadécimale d'un nombre avec `hex(n)`.
- On obtient la représentation binaire d'un nombre avec `bin(n)`.
- Convertir une chaîne en nombre avec `int(s)` la lit en base 10 par défaut.
- On peut indiquer une autre base avec un second argument : `int(s, 16)` interprète la chaîne en hexadécimal, `int(s, 2)` en binaire.
- On peut tenter de détecter automatiquement la base avec `int(s, 0)`, ce qui impose un préfixe à la chaîne (`0b` pour le binaire, `0x` pour l'hexadécimal, rien pour le décimal).
