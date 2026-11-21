*Introduction ajoutée pour cette traduction, hors traduction directe.*

Les données ne sont jamais que des suites d'octets, et leur signification dépend de la façon dont on les interprète.
Ce module montre comment un même contenu peut être présenté sous différentes formes : texte, hexadécimal, binaire, base64, ou encodages de caractères comme l'ASCII et l'UTF-8.

On commence par lire un programme simple pour trouver la donnée qu'il attend, puis on apprend à passer d'une représentation à l'autre, dans les deux sens.
Les défis suivants introduisent les `bytes` et les `str` de Python, les emojis et l'UTF-8, puis les confusions d'encodage qui peuvent créer des failles de sécurité.
Le module se termine par l'obfuscation par codage, qui cache des données sans les protéger, et par la façon de les récupérer quand on connaît le codage utilisé.

La progression va du plus simple au plus technique : chaque défi reprend les notions vues plus tôt pour les appliquer à une nouvelle situation.
