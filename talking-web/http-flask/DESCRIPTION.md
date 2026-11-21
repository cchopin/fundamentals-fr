Très bien, la démarche de base est comprise.
Il reste une chose à faire : lire et comprendre le code source du défi !
Les serveurs web _routent_ les requêtes HTTP vers différents _points de terminaison_ (endpoints) : `http://challenge.localhost/pwn` peut mener au point de terminaison qui traite le chemin `/pwn`, et `http://challenge.localhost/college` peut mener à celui qui traite le chemin `college`.
Ce défi utilise un nom de point de terminaison tiré au hasard.
Il faut lire le code de `/challenge/server`, le comprendre, et déterminer quel point de terminaison visiter dans le navigateur !

----
Un doute ?
Les serveurs web de pwn.college sont implémentés avec la bibliothèque [flask](https://flask.palletsprojects.com/en/stable/quickstart/).
Sa documentation permet de comprendre le code, ou de l'expérimenter directement.
