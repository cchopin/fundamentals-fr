Dans les scénarios de sécurité réels, il arrive que l'attaquant ne dispose pas de certaines informations, comme les noms des tables qu'il veut interroger !
Heureusement, chaque moteur SQL permet d'interroger des _métadonnées_ sur les tables (même si, de façon confuse, chaque moteur le fait différemment !).
SQLite utilise une table spéciale, `sqlite_master`, dans laquelle il stocke des informations sur toutes les autres tables.
Peut-on trouver le nom de la table qui contient le flag, puis l'interroger ?
