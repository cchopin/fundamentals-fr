Au début du web, le HTML, bien qu'_Hyper_, était assez statique.
Il décrivait les mises en page, et c'était tout.
Dans les années 1990, les acteurs de l'internet se sont demandé : « Et si les pages web pouvaient exécuter de la logique ? » Ainsi naquit JavaScript.

JavaScript est un langage de programmation qui permet aux pages web de prendre des décisions et d'agir dynamiquement.
C'est, sans contestation (et malheureusement, car il est exécrable), le langage de programmation le plus important qui existe, même s'il n'est pas le plus utilisé. Et même si on essaie de l'éviter (on a dit qu'il était exécrable ?), il faut en tenir compte dès qu'on parle de sécurité web.
Le HTML indique le JavaScript à exécuter avec la balise `<script>`.
Cette balise indique au navigateur que son contenu est du JavaScript, qu'il exécute.
Il existe de nombreuses ressources en ligne sur l'écriture de balises `<script>` et sur le JavaScript. Leur recherche est laissée en exercice à l'apprenant.
Ici, on s'exerce à une chose très précise : utiliser JavaScript pour rediriger le navigateur vers une autre page web.

Comme précédemment, le navigateur du client affichera la page reçue, mais il commencera par aller sur `http://challenge.localhost/~hacker/solve.html`.
Ici, on rend hommage aux serveurs partagés d'autrefois : `http://challenge.localhost/~hacker/anything` est servi à partir du sous-dossier `public_html` du répertoire personnel.
Créer `/home/hacker/public_html/solve.html`, y écrire le JavaScript nécessaire pour rediriger le navigateur, et obtenir le flag !

----
**INDICE :**
L'objet JavaScript recherché est `window.location`.
Lui affecter une chaîne de caractères redirige le navigateur vers une nouvelle adresse.

**INDICE :**
Le débogage peut être délicat avec le navigateur intégré.
Essayer avec Firefox du dojo ! On ne peut pas obtenir le flag final avec, mais on peut vérifier que la redirection fonctionne.
