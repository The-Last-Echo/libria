# Archive de bibliothèque versionnée indépendamment de la base

**Statut : accepté.** L’export complet de la bibliothèque utilise une archive ZIP contenant les données JSON et les images, avec une version de format indépendante de celle de la base locale ; l’import accepte les formats antérieurs. Les réglages de l’application restent hors de l’archive, tandis que le CSV constitue un export complémentaire. Ce choix permet de faire évoluer le stockage local sans rendre les sauvegardes des utilisateurs dépendantes du schéma de la base.
