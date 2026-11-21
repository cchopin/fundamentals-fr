JavaScript peut faire beaucoup de choses dans le contexte d'une page web, et peut donc mener à des situations inattendues et à des compromissions de sécurité.
Quelques-unes de ces situations seront explorées dans le module Web Security, mais ce module pose déjà les bases.

Dans ce défi, `/challenge/client` n'affiche plus la page web, et `/challenge/server` ne renvoie plus une page HTML contenant le flag, mais un script JavaScript qui définit une variable globale `flag` avec la valeur du flag.
Il faut créer une page web qui _inclut_ ce script (la documentation se trouve sans peine : indice, `src` est impliqué), puis écrire un autre script qui fait sortir cette information de la page (_exfiltrer_).
L'exfiltration consiste à faire sortir des données sensibles sous le nez de leurs propriétaires : ici, `/challenge/client` et `/challenge/server`.
Le script exécuté sur la page a évidemment accès à la variable `flag`, mais il faut la transmettre au monde extérieur.
Plusieurs moyens existent. Le plus simple est sans doute de rediriger le navigateur du client (avec le truc `window.location` vu précédemment) vers une URL qui contient le flag, comme le client l'a fait fuiter quelques défis plus tôt, et de faire en sorte que cette requête atterrisse là où l'on peut voir le journal des URL, par exemple celui de `/challenge/server` ou celui de son propre serveur web.

Cela semble beaucoup, mais c'est tout à fait faisable.
Notre fichier HTML de référence ne fait que 150 octets !
Comme précédemment, on peut déboguer sa solution avec son propre navigateur, et l'exécuter en root en mode pratique pour pouvoir inclure le script du flag.
