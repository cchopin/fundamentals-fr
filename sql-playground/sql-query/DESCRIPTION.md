Ce défi marque le début du parcours SQL.
Dans ce défi, et tout au long de ce module, on utilise un moteur SQL appelé [SQLite](https://sqlite.org/).
SQLite est un moteur SQL très léger qui, au lieu d'utiliser un processus serveur SQL complexe pour héberger les bases, interagit directement avec les fichiers de base de données.
Cela le rend très pratique pour prototyper des applications, et on l'utilise pour presque tous nos besoins SQL dans les défis de pwn.college, mais on ne le choisirait pas pour un site Web en production…
Dans le fichier du défi (`/challenge/sql`), on remarque l'utilisation de SQLite via la classe TemporaryDB.
On peut ignorer le fonctionnement interne de cette classe : on s'en sert simplement comme d'une enveloppe pour exécuter des requêtes SQL et obtenir des résultats.
Il faut se concentrer sur le reste du code !

Ce défi commence par une requête très simple.
La requête que l'on découvre est `SELECT`.
On utilise `SELECT` pour (😎) _sélectionner_ des données dans les tables de sa base.
Sa syntaxe de base est `SELECT what FROM where`, où `what` et `where` sont des éléments qu'on précise.
Le `where` est en général une table de la base, et le `what` désigne les colonnes que la requête doit récupérer.
Si l'on ne veut pas se soucier des colonnes à sélectionner, on peut écrire `SELECT *` !

Il faut lire le code pour comprendre la structure de la base interrogée, puis sélectionner le flag !

----
**Note :**
Ce défi, comme les autres de la série, renvoie vers la documentation SQLite pertinente.
Cette documentation peut être assez sèche et dense.
On peut aussi consulter d'autres ressources.
Il existe énormément de guides SQL sur Internet : si nous en avons écrit un, c'est uniquement pour donner un aperçu accéléré des parties de SQL dont les élèves auront besoin pour les défis de pwn.college !
