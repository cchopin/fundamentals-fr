Passons maintenant aux `str`ings !
En Python, les chaînes de caractères sont destinées à la lecture humaine.
Une chaîne est une suite de caractères qu'un humain pourrait écrire, lire, prononcer ou rêver.
Cela inclut les lettres de l'alphabet, mais aussi des éléments comme 🕴️.
Quand on pense au nombre de lettres des différents alphabets, aux emojis et au reste, il est clair qu'il existe _des milliers_ de possibilités pour chaque caractère d'une chaîne.

La représentation d'un caractère lisible par un humain sous forme d'octets en mémoire est encore un _codage_ (employé ici comme nom).
Un caractère, comme 🐉, est « encodé » (employé ici comme verbe) par des octets en mémoire, et ces octets se « décodent » en ce caractère.
Dans cet usage des termes « encoder » et « décoder », les données restent les mêmes, mais leur interprétation change : le codage est appliqué, par exemple, par le terminal en ligne de commande pour traduire les octets envoyés par le programme en caractères et emojis affichés à l'écran.

En Python, on convertit une `str` en son équivalent `bytes` avec `my_string.encode()`.
Si l'on dispose d'octets que l'on veut interpréter comme une chaîne, on peut écrire `my_bytes.decode()`.
Mais comment les caractères d'une chaîne sont-ils associés à des valeurs d'octets ?

Dans les premiers temps de l'informatique (disons avant 2000), quand le calcul était moins international et qu'on écrivait encore `:-)` au lieu de 🙂, on ne se souciait guère de la limite de caractères qu'un seul octet peut représenter.
Les premiers codages associaient donc chaque caractère à un seul octet, avec une limite de 256 caractères possibles.
Comme l'informatique naissante était surtout américaine et ouest-européenne, le codage le plus populaire, conçu pour représenter les caractères de l'alphabet latin par différentes valeurs d'octets, était [_ASCII_](https://en.wikipedia.org/wiki/ASCII), datant de 1963 (de l'histoire ancienne pour l'informatique !).

L'ASCII est assez simple : chaque caractère occupe un octet. Les lettres majuscules valent `0x40+letter_index` (par exemple A vaut `0x41`, F vaut `0x46` et Z vaut `0x5a`), les lettres minuscules valent `0x60+letter_index` (a vaut `0x61`, f vaut `0x66` et z vaut `0x7a`), et les chiffres (les caractères numériques que l'on voit ne sont _pas_ des octets de ces valeurs : ce sont des chiffres codés en ASCII) valent `0x30+number`, donc 0 vaut `0x30` et 7 vaut `0x37`.
Des caractères spéciaux utiles sont répartis dans la table : la barre oblique (`/` vaut `0x2f`), l'espace vaut `0x20`, et le saut de ligne vaut `0x0a`.
Comme les pionniers de l'informatique improvisaient, certains caractères ASCII ne sont pas vraiment des caractères : `0x07` est une _sonnerie_ ; quand on l'« affiche », le terminal émet littéralement un bip !
D'autres « caractères de contrôle » font des choses plus surprenantes : `0x08`, par exemple, _supprime le dernier caractère_ du terminal au lieu d'être un caractère lui-même.

Les valeurs d'octets inférieures à `0x80` (`128`), qui forment l'« ASCII standard », étaient définies de façon presque universelle, y compris dans les pays non anglophones.
On peut consulter cette définition complète de l'ASCII standard avec `man ascii` !
On peut aussi utiliser l'ASCII standard en Python pour encoder des chaînes : `my_string.encode("ascii")`.
Attention toutefois : l'ASCII standard ne définit pas les valeurs au-delà de `0x80`. Si l'on _décode_ des octets qui ont ces valeurs, une exception est levée !
Par exemple, cela ne fonctionne pas : `b"\x80".decode("ascii")`.

Les valeurs _au-delà_ de `0x80` (« ASCII étendu ») étaient utilisées par différents pays pour leurs propres caractères, ce qui a créé un certain chaos, avec des valeurs d'octets en conflit.
Aux États-Unis, le codage ASCII étendu le plus courant s'appelait [Latin 1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1), et il définissait un caractère pour chacune des 256 valeurs d'octets possibles.
C'est utile ici, car on peut utiliser « latin1 » pour convertir facilement entre les `bytes` et les chaînes de Python, par exemple : `b"\x80".decode("latin1")`.

Dans ce défi, il faut donner les valeurs hexadécimales ASCII (anecdote : indiquer des valeurs d'octets en hexadécimal s'appelle « codage hexadécimal » !), et le programme les comparera au mot de passe.
Bonne chance !

---
**Note :**
En lisant le défi pour comprendre la valeur à envoyer, on remarque que certaines parties de la constante `bytes` définie pour `correct_password` paraissent… étranges.
Chaque octet de `correct_password` représente un octet en mémoire, mais beaucoup portent des informations utiles pour un humain.
Écrire _chaque_ octet avec des séquences d'échappement, bien que valide, serait moins utile pour un humain, même si les octets ne sont _pas vraiment_ destinés à la lecture humaine.
Les développeurs de Python ont donc décidé de représenter les `bytes` en ASCII standard.
Les `bytes` Python s'écrivent avec des caractères ASCII, les octets plus inhabituels, « non imprimables » (par exemple tout ce qui dépasse `0x80`, et quelques autres), s'écrivant avec des _séquences d'échappement_ `\x`.
Cela fonctionne aussi pour les caractères ordinaires : `\x41` code bien le `A`.
D'autres caractères spéciaux ont leurs propres séquences : par exemple, `\n` code un saut de ligne (équivalent à `\x0a`).
On trouve d'autres séquences d'échappement dans `man ascii`.
Comme `\` sert d'élément d'échappement, Python (et les autres langages qui utilisent ce mécanisme, c'est-à-dire presque tous) doit écrire un antislash _réel_ sous forme d'échappement (`\\` code un octet `\` de valeur `0x5c`).

Voilà beaucoup d'informations.
Il est temps de les mettre en pratique !
