Jusqu'ici, on a passé son temps à lire le code des serveurs web et à apprendre à leur parler.
Maintenant, on apprend à _écouter_.

Dans ce défi, il faut écrire un petit serveur qui recevra la requête pour le flag.
Il suffit de copier le code du serveur du tout premier module, d'en retirer ce qui est superflu, et de construire un serveur web qui écoute sur le port 1337 (et non le 80, car un utilisateur non administrateur ne peut pas écouter sur le port 80) et sur le nom d'hôte `localhost`.
Une fois prêt, lancer `/challenge/client` : il ouvrira un navigateur interne et visitera `http://localhost:1337/` pour recevoir le flag !
