Maintenant, il faut _décoder_ de l'hexadécimal plutôt que de l'encoder.
Peut-on déterminer ce dont le programme a besoin ?

---
**Note :**
L'une des parties les plus difficiles de ce défi consiste à envoyer des données binaires brutes sur l'entrée standard du programme.
Il existe plusieurs façons de le faire :

1. Écrire un script Python qui affiche les données sur la sortie standard, puis rediriger cette sortie vers l'entrée standard du défi.
   Cela suppose d'utiliser l'interface d'octets bruts de la sortie standard : `sys.stdout.buffer.write()`.
2. Écrire un script Python qui lance le défi et interagit directement avec lui.
   On recommande d'utiliser pwntools pour cela : `import pwn`, `p = pwn.process("/challenge/runme")`, `p.write()` et `p.readall()`.
   Un ancien élève de pwn.college a créé un [aide-mémoire pwntools](https://gist.github.com/anvbis/64907e4f90974c4bdd930baeb705dedf) très utile.
3. Pour une solution de plus en plus bricolée, `echo -e -n "\xAA\xBB"` affiche des octets sur la sortie standard, qu'on peut rediriger.
