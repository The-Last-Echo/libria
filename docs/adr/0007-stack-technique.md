# Stack technique

**Statut : accepté.** Libria utilise Flutter et Dart, SQLite avec Drift pour le stockage local, Riverpod pour la gestion d’état et go_router pour la navigation. La logique métier reste dans des classes Dart indépendantes de Riverpod, afin que le choix de l’outil d’état puisse évoluer sans imposer de réécrire le domaine.
