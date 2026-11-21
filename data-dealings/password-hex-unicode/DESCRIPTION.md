Quand l'informatique est devenue internationale et que les emojis sont apparus, il a fallu pouvoir utiliser plus de 256 caractères possibles.
Aujourd'hui, ce problème est en grande partie résolu par le codage [UTF-8](https://en.wikipedia.org/wiki/UTF-8).
L'UTF-8 est un codage précis de l'[Unicode](https://en.wikipedia.org/wiki/Unicode), un jeu de caractères normalisé mondialement, qui contient pratiquement tous les caractères connus de l'humanité, ainsi que les emojis que l'on connaît et que l'on aime.
Il existe plusieurs façons de coder l'Unicode, et l'UTF-8 en est une.
Unicode (jeu de caractères) est à l'UTF-8 (codage) ce que l'anglais (jeu de caractères) est à l'ASCII standard (codage).

L'UTF-8 est heureusement compatible avec l'ASCII standard (les valeurs d'octets de l'ASCII standard représentent le même caractère en UTF-8), mais dans certaines situations il utilise _plusieurs octets_ pour représenter un seul caractère.
Cela permet à l'UTF-8 de disposer de possibilités pratiquement illimitées (il peut toujours interpréter davantage d'octets !) : il prend actuellement en charge bien plus de 1 000 000 de caractères !

L'UTF-8 est, par défaut, le codage des chaînes de caractères en Python, ce qui permet d'écrire par exemple `my_string = "💥"`.
On obtient la représentation en octets de cette chaîne (telle qu'elle est stockée en mémoire) avec `my_string.encode("utf-8")`, ce qui donne, pour cet emoji, les bytes `b'\xf0\x9f\x92\xa5'`.
Ces quatre octets représentent cet emoji en UTF-8.

Dans ce défi, il faut fabriquer les octets d'emojis en UTF-8, les coder en hexadécimal, puis envoyer ces valeurs hexadécimales.
Est-ce possible ?

---
**Note du dojo :**
À cause d'un bogue d'affichage Unicode dans le terminal du bureau graphique, on recommande d'utiliser l'espace de travail VSCode pour ce défi (et pour tous les défis qui dépendent des emojis !).
