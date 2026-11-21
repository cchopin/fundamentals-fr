*Introduction ajoutée pour cette traduction, hors traduction directe.*

Ce module apprend à parler HTTP, le protocole qui fait fonctionner le web, en utilisant les outils de la ligne de commande et le navigateur.
On commence par consulter une page avec le navigateur, puis on regarde ce qui se cache dans le code source et dans les en-têtes.
On apprend ensuite à envoyer soi-même des requêtes GET et POST, d'abord avec netcat, qui écrit la requête à la main, puis avec curl et la bibliothèque requests de Python.
Les derniers défis mènent à l'écriture d'un petit serveur web, puis à l'usage de JavaScript pour récupérer et faire sortir une donnée d'une page.

Les défis suivent à peu près cet ordre :

- le navigateur, le code source de la page et les en-têtes ;
- les requêtes GET, avec et sans paramètres, puis les requêtes POST avec des formulaires ;
- l'en-tête `Host`, qui permet à un même serveur d'héberger plusieurs sites ;
- l'écriture de requêtes à la main avec netcat, puis leur envoi avec curl et requests ;
- les redirections, suivies automatiquement par curl et requests ;
- l'écriture d'un serveur web qui reçoit une requête, puis la redirection d'un client vers un autre serveur ;
- JavaScript : `fetch()` pour récupérer des données, puis l'inclusion d'un script et l'exfiltration d'une donnée.

Chaque défi indique l'outil à utiliser. Certains donnent des indices, qui sont signalés comme tels.
