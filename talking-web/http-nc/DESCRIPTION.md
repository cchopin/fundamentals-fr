On sait déjà faire des requêtes HTTP (et on en fait sans doute depuis longtemps sans le savoir !).
Apprenons maintenant à écrire le HTTP _vraiment_.
Le protocole HTTP lui-même, c'est-à-dire les données exactes envoyées sur le réseau, est étonnamment lisible et facile à écrire à la main.
Dans ce défi, on apprend à l'écrire.
Ce défi utilise un programme appelé « netcat » (commande `nc`), un programme simple qui communique via une connexion réseau.
L'usage de base de netcat prend deux arguments : le _nom d'hôte_ (l'adresse du serveur, par exemple www.google.com pour Google) et le port (le port HTTP standard est le 80).

Au démarrage, netcat se connecte au serveur et ouvre un canal brut pour communiquer avec lui.
On parle alors _directement avec le serveur web_, sans intermédiaire !
C'est génial, non ?

Retrouver le format d'une requête HTTP, puis faire une requête GET vers l'endpoint `/` (les autres endpoints viendront plus tard) pour obtenir le flag !

----
**INDICE :**
Pas sûr que netcat se connecte ?
Utiliser l'option `-v` pour afficher des informations supplémentaires !

**INDICE :**
La requête GET est tapée, et rien ne se passe après Entrée ?
Une requête HTTP se termine par _deux_ retours à la ligne.
Appuyer à nouveau sur Entrée !

**Une réflexion...**
Avant ce moment, a-t-on déjà vraiment fait du HTTP à la main ?
