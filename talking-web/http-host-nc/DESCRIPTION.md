Dernière étape : voir comment l'en-tête Host est réellement envoyé sur le réseau avec nc.
C'est un peu plus délicat. On peut utiliser `curl` comme source d'information !
L'option `-v` de curl affiche exactement les en-têtes envoyés (et ceux reçus).
Les observer, les recopier avec nc, et obtenir le flag !
