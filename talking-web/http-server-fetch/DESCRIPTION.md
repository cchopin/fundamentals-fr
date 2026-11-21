Voilà maintenant la partie difficile...
Souvent, ce qu'il faut exfiltrer se trouve ailleurs, accessible au JavaScript de la page, mais il faut faire des requêtes HTTP pour le récupérer.
En JavaScript moderne, les requêtes HTTP se font avec la fonction `fetch()`.
Elle fonctionne à peu près ainsi :

```javascript
fetch("http://google.com").then(response => response.text()).then(website_content => ???);
```

Le `???` est, bien sûr, le code à exécuter sur le contenu du site.
Cette API semble absurde parce que JavaScript l'est, mais aussi parce qu'elle doit résoudre un problème difficile : exécuter de la logique dans un environnement où les erreurs réseau, la charge du processeur, la mise en veille de l'ordinateur, les pare-feux et d'autres phénomènes peuvent perturber le chargement des ressources dont elle dépend.
Le code ci-dessus utilise les « promesses » (promises) de JavaScript, un modèle de programmation complexe qui permet d'écrire une logique qui _sera_ exécutée sur des données qui ne sont pas _encore_ disponibles, quand elles le deviendront enfin.
Le `.then()` précise ce qui sera exécuté plus tard.
Le déroulement est à peu près le suivant :

1. `fetch()` renvoie une promesse et commence à récupérer `http://google.com`.
   Cela peut prendre du temps, échouer ou réussir immédiatement.
   Dans tous les cas, l'appel renvoie un objet `promise` dont la méthode `then()` s'exécutera quand la réponse sera disponible.
2. La réponse arrive et le code promis s'exécute.
   Ce code appelle `response.text()`, qui récupère le contenu _complet_ renvoyé par `http://google.com`.
   Comme ce chargement peut aussi prendre du temps, cet appel renvoie _à son tour_ une promesse, avec sa propre méthode `.then()`.
3. Enfin, tout le contenu est disponible, et le dernier code promis s'exécute.
   Ce code peut faire n'importe quoi, mais le plus souvent, c'est là qu'on exfiltre les données, comme dans les défis précédents.

Ce mécanisme peut être très difficile à comprendre et à déboguer.
Il faut être prêt à le déboguer dans Firefox, en mode pratique.

Dans ce défi, le flag n'est plus enveloppé dans du JavaScript.
C'est simplement du texte. Il faut le récupérer et l'exfiltrer pour marquer des points.
Bonne chance !
