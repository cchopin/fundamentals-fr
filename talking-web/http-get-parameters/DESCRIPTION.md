Comme un appel de fonction dans un langage de programmation, ou une commande dans le shell, les requêtes HTTP peuvent contenir des _paramètres_.
Les requêtes GET envoient les paramètres à côté du chemin, dans une partie de l'URL appelée [chaîne de requête (query string)](https://en.wikipedia.org/wiki/Query_string).
Ce défi montre comment construire cette chaîne de requête.
Lire le code du défi pour savoir quel paramètre est attendu, puis l'envoyer !
Le client utilisé n'a pas d'importance : la démarche est essentiellement la même pour tous.

----
**NOTE DE SÉCURITÉ :**
On est tenté de comparer les paramètres HTTP aux paramètres d'un appel de fonction.
Pourtant, dans un programme écrit en C, en Python ou en Java, un attaquant ne peut en général pas appeler n'importe quelle fonction du programme avec les paramètres de son choix.
Avec HTTP, il le peut : il suffit d'envoyer des requêtes où il veut !
Cela a causé de nombreux problèmes de sécurité...
