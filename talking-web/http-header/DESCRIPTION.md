HTTP transporte à la fois des _données_ (par exemple le HTML que `/challenge/server` renvoie) et des _métadonnées_ (des données sur les données).
Ces dernières passent par les _en-têtes_ (headers) : des champs d'une requête ou d'une réponse HTTP qui donnent des instructions supplémentaires au serveur ou au navigateur.
Ici, le flag se trouve dans un en-tête. Peut-on le trouver ?

----
**INDICE :** les outils de développement de Firefox permettent d'inspecter les en-têtes (≡, puis `More Tools`).
L'onglet Réseau (Network) affiche toutes les connexions HTTP. Il faut parfois recharger la page après avoir ouvert les outils pour que la connexion apparaisse.
Chaque connexion a un sous-onglet `Headers`, qui affiche les en-têtes envoyés par le navigateur (`Request Headers`) et ceux reçus dans la réponse (`Response Headers`).
Le flag se trouve dans l'en-tête correspondant !
