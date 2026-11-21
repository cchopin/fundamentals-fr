Et, naturellement, `fetch()` permet aussi de faire des requêtes POST.
Cela permet à notre JavaScript de simuler l'envoi d'un formulaire, et c'est très pratique !
On s'exerce avec ce défi.
On peut chercher soi-même comment passer des arguments avancés à `fetch()`, mais voici quelques éléments qui _doivent_ apparaître tels quels dans le JavaScript :

- `{`
- `method: "POST"`
- `body`
- `new URLSearchParams`
- `}`

Bonne chance !

----
**NOTE :**
Il existe plusieurs façons d'envoyer des paramètres POST.
Ce module a présenté l'envoi de données de formulaire, mais il en existe d'autres, et chacune se récupère différemment avec flask.
S'assurer d'envoyer des données de formulaire dans la requête POST, et non autre chose : sinon, le serveur, tel qu'il est implémenté, ne les verra pas !
