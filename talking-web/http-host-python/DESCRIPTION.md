Malheureusement, une bonne partie d'internet fonctionne sur l'infrastructure d'une poignée d'entreprises, et un même serveur de ces entreprises peut héberger les sites de plusieurs dizaines de noms de domaine.
Comment le serveur décide-t-il quel site servir ? Grâce à l'en-tête `Host`.

L'en-tête `Host` est un en-tête de _requête_ envoyé par le client (navigateur, curl, etc.), en général égal au nom de domaine saisi dans la requête HTTP.
Quand on va sur `https://pwn.college`, le navigateur définit automatiquement l'en-tête `Host` à `pwn.college`, et le serveur sait ainsi qu'il doit renvoyer le site de pwn.college, et non un autre.

Jusqu'ici, les défis avec lesquels on a interagi ne vérifiaient pas cet en-tête. Ce n'est plus le cas.
Définir le bon en-tête `Host` et obtenir le flag !
