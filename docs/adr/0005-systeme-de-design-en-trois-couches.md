# Système de design en trois couches

**Statut : accepté.** Le système de design sépare les tokens visuels, les composants propres à Libria et les écrans ; ceux-ci ne dépendent pas directement des composants Material. Cette couche intermédiaire demande de maintenir des composants internes, mais préserve la cohérence de l’interface et limite le couplage aux briques d’interface de Flutter, afin de faciliter leur évolution ou leur réutilisation.
