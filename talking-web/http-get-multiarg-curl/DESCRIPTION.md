Passer plusieurs paramètres HTTP avec curl est un cas particulier, car `&` a un sens spécial dans le shell (il lance une commande en arrière-plan). Si l'on n'y prend pas garde, le shell se trompe sur ce `&`.
Il faut mettre l'URL complète, avec sa chaîne de requête, entre guillemets pour éviter ce problème.
Essayer maintenant.
