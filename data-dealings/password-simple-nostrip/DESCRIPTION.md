Les défis précédents étaient assez simples, comme celui-ci.
Mais celui-ci fait une chose légèrement différente : il ne supprime pas le retour à la ligne produit par la touche Entrée quand on saisit le mot de passe.
Le `entered_password` contient donc un saut de ligne, et comme `correct_password` n'en contient pas, la comparaison échoue !

Ce genre de chose, des délimiteurs égarés dans les données, arrive TOUT le temps, et peut faire perdre énormément de temps.
Plusieurs solutions existent dans ce niveau :

1. Chercher comment terminer la saisie du terminal _sans_ appuyer sur Entrée.
   C'est très facile à trouver en ligne !
2. Se rappeler, depuis le Luminarium Linux, comment rediriger un `echo` (avec des arguments qui désactivent le saut de ligne) vers l'entrée standard de `/challenge/runme`.
3. Créer un fichier sans saut de ligne, puis se rappeler du Luminarium Linux pour rediriger ce fichier vers l'entrée standard de `/challenge/runme`.

Bonne chance !
