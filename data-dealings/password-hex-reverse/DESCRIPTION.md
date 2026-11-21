Jusqu'ici, nous avons vu plusieurs types de codages : UTF-8, UTF-16, ASCII étendu (latin-1) et codage hexadécimal.
Un codage transforme des données, qu'il s'agisse d'un concept comme un emoji 🎈 ou d'un octet réel en mémoire, en d'autres octets.
Que se passe-t-il si l'on modifie les données codées ?
Rien de bon !
En UTF-8, 🎈 s'encode ainsi :

```console
hacker@dojo:~$ ipython
In [1]: "🎈".encode("utf-8")
Out[1]: b'\xf0\x9f\x8e\x88'
```

Si l'on modifie les octets obtenus, puis qu'on les décode, on obtient évidemment autre chose :

```console
In [2]: b'\xf0\x9f\x8e\xaa'.decode("utf-8")
Out[2]: '🎪'

In [3]: b'\xf0\x9f\x8e\x42'.decode("utf-8")
---------------------------------------------------------------------------
UnicodeDecodeError                        Traceback (most recent call last)
Cell In[3], line 1
----> 1 b'\xf0\x9f\x8e\x42'.decode("utf-8")

UnicodeDecodeError: 'utf-8' codec can't decode bytes in position 0-2: invalid continuation byte
```

La première modification a donné un autre emoji, et la seconde a provoqué une erreur.
Selon le codage, toutes les valeurs d'octets ne peuvent pas être décodées correctement !
Pour l'UTF-8, cela tient à un algorithme complexe de représentation des données.
Pour le codage hexadécimal, seuls les chiffres de 0 à 9 et les lettres de A à F sont valides en hexadécimal !

Cela dit, n'importe quel codage _peut_ être modifié dans une certaine mesure, comme le montre le premier exemple ci-dessus.
Quand une faille de sécurité permet de corrompre des données, un attaquant peut transformer soigneusement ces données selon ses besoins.
Nous verrons plus tard comment protéger les données contre cela, mais pour l'instant, on s'entraîne à ce concept en modifiant de l'hexadécimal !
