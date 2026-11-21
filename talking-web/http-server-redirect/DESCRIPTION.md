On a suivi des redirections ; il faut maintenant en provoquer une.
Faire en sorte que le serveur web redirige `/challenge/client` vers le bon emplacement de `/challenge/server`.
Il faut trois fenêtres de terminal pour cela :

1. La première fenêtre lance `/challenge/server`, qui écoute sur le port 80 et prépare le flag.
2. La deuxième fenêtre lance son propre serveur web, qui écoute sur le port 1337 et prépare la redirection du client.
3. La troisième fenêtre lance `/challenge/client`.

C'est complexe, mais c'est faisable !
