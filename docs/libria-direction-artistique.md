# Fiche de direction artistique — Libria

**Identité : Indigo Graphite**  
Version 1.1 · Direction artistique et système de design · Flutter / Android

> **Changements de la v1.1** : navigation à 3 onglets en V1 ; ajout direct avec « Annuler » au scan ; filtres complétés ; icônes embarquées derrière une classe maison ; préréglages d'accent vérifiés ; bordures de champs conformes ; section 10 de compléments (couverture de remplacement, erreurs, annulation, formulaires, chargement, réglages, prêts, annotations). Les valeurs ajoutées en v1.1 sont des propositions à valider à l'usage sur téléphone.

---

## 1. Intention et ambiance

Libria adopte une identité minimaliste, élégante et contemporaine, inspirée des interfaces premium modernes.  
L'interface privilégie la précision, la lisibilité et une hiérarchie visuelle claire, sans surcharge décorative.  
L'indigo profond apporte une identité reconnaissable, tandis que les surfaces graphite créent une profondeur discrète.  
L'expérience est calme au repos, réactive et fluide lors des interactions.  

**À éviter :** esthétique vintage, textures papier, couleurs criardes, glassmorphism, ombres excessives, arrondis exagérés et animations spectaculaires.

## 2. Palette

La palette doit être centralisée dans des variables de thème. Aucun écran ne doit définir ses propres couleurs indépendamment du système.

L'identité repose sur trois variantes d'une même couleur d'accent :

- Clair : indigo sophistiqué `#6556B8`.
- Sombre : lavande indigo `#A99AFF`.
- AMOLED : lavande lumineuse `#B6AAFF`.

### Thème clair

| Token | Valeur HEX |
|---|---|
| Fond principal | `#F6F5FA` |
| Surface principale | `#FFFFFF` |
| Surface secondaire | `#F0EEF5` |
| Surface élevée | `#FFFFFF` |
| Texte principal | `#1B1A22` |
| Texte secondaire | `#5E5B68` |
| Texte atténué | `#6C6875` |
| Bordures | `#E1DEE8` |
| Accent principal | `#6556B8` |
| Texte sur accent | `#FFFFFF` |
| Fond accentué | `#EEEAFE` |
| Texte sur fond accentué | `#3D347F` |
| Succès | `#246B48` |
| Fond succès | `#E7F4EC` |
| Alerte | `#815400` |
| Fond alerte | `#FFF3D9` |
| Erreur | `#B3261E` |
| Fond erreur | `#FCE8E6` |

### Thème sombre

| Token | Valeur HEX |
|---|---|
| Fond principal | `#111116` |
| Surface principale | `#191920` |
| Surface secondaire | `#2C2B36` |
| Surface élevée | `#22222B` |
| Texte principal | `#F4F2FA` |
| Texte secondaire | `#C2BECF` |
| Texte atténué | `#A19CAE` |
| Bordures | `#393642` |
| Accent principal | `#A99AFF` |
| Texte sur accent | `#201A3A` |
| Fond accentué | `#2B2547` |
| Texte sur fond accentué | `#D7D0FF` |
| Succès | `#BFE8CE` |
| Fond succès | `#173A2B` |
| Alerte | `#FFD78A` |
| Fond alerte | `#4A3718` |
| Erreur | `#FFB4AB` |
| Fond erreur | `#521F1D` |

### Thème noir pur (AMOLED)

| Token | Valeur HEX |
|---|---|
| Fond principal | `#000000` |
| Surface principale | `#08080D` |
| Surface secondaire | `#1C1B25` |
| Surface élevée | `#12121A` |
| Texte principal | `#F4F2FA` |
| Texte secondaire | `#C2BECF` |
| Texte atténué | `#A19CAE` |
| Bordures | `#292732` |
| Accent principal | `#B6AAFF` |
| Texte sur accent | `#1E1837` |
| Fond accentué | `#241E3D` |
| Texte sur fond accentué | `#D8D1FF` |
| Succès | `#BFE8CE` |
| Fond succès | `#123425` |
| Alerte | `#FFD78A` |
| Fond alerte | `#493514` |
| Erreur | `#FFB4AB` |
| Fond erreur | `#4B1D1B` |

### Règles d'utilisation

- Le thème par défaut est **Automatique**, synchronisé avec Android.
- Les thèmes Clair, Sombre et Noir pur sont sélectionnables manuellement.
- Les fonds AMOLED doivent réellement utiliser `#000000`, et non un gris très foncé.
- La couleur d'accent doit être personnalisable dans les paramètres. En V1, proposer une sélection de couleurs prédéfinies avec leurs variantes adaptées à chaque thème.
- Les couleurs de succès, d'alerte et d'erreur ne doivent jamais être utilisées uniquement comme moyen de transmission d'information. Toujours associer une icône et un libellé.
- Les textes courants doivent respecter un contraste de 4,5:1 minimum ; les grands textes peuvent utiliser le seuil de 3:1 prévu par WCAG AA. Vérifier les couples de couleurs réellement utilisés, notamment les textes secondaires, les états désactivés et les éléments interactifs, avec un outil de mesure de contraste avant validation.

### Préréglages de couleur d'accent (V1) — proposition v1.1

Six préréglages, chacun avec ses trois déclinaisons. Tous les couples ont été vérifiés par calcul : texte sur accent ≥ 6,0:1, accent sur fond et sur surface secondaire ≥ 5,2:1, texte sur fond accentué ≥ 7:1. Les variantes sombres sont volontairement adoucies (pas de couleurs vives).

| Préréglage | Clair : accent / fond accentué / texte sur fond | Sombre : accent / sur accent / fond accentué / texte sur fond | AMOLED : accent / sur accent / fond accentué / texte sur fond |
|---|---|---|---|
| Indigo (défaut) | `#6556B8` / `#EEEAFE` / `#3D347F` | `#A99AFF` / `#201A3A` / `#2B2547` / `#D7D0FF` | `#B6AAFF` / `#1E1837` / `#241E3D` / `#D8D1FF` |
| Bleu | `#3C649D` / `#E8ECF3` / `#2F4F7C` | `#72A5EB` / `#121D2B` / `#272F40` / `#B6D3FB` | `#639BE9` / `#0D141E` / `#172030` / `#B6D3FB` |
| Sarcelle | `#296D67` / `#E5EDED` / `#205551` | `#45B5AC` / `#0F2422` / `#203236` / `#ADEBE5` | `#42AEA5` / `#0B1B19` / `#112325` / `#ADEBE5` |
| Vert | `#2A6F47` / `#E5EEE9` / `#215737` | `#45B775` / `#0F2217` / `#20322E` / `#ADEBC7` | `#42AE6F` / `#0A170F` / `#11231D` / `#ADEBC7` |
| Rose | `#A53E69` / `#F4E8ED` / `#813153` | `#ED80AD` / `#2B121D` / `#3B2937` / `#FBB6D3` | `#EA6EA2` / `#1D0C13` / `#2C1825` / `#FBB6D3` |
| Terracotta | `#905237` / `#F2EAE7` / `#73412B` | `#E98B63` / `#2B1A12` / `#3A2B2B` / `#FBCBB6` | `#E78155` / `#22140F` / `#2C1B19` / `#FBCBB6` |

En thème clair, le texte sur accent est `#FFFFFF`. Un nouveau préréglage n'est accepté qu'après la même vérification de contraste.

### Bordure de champ de saisie (v1.1)

Les bordures décoratives (`outline`) restent discrètes. Un champ de saisie utilise un jeton distinct, **`outlineStrong`**, à au moins 3:1 contre la surface et le fond :

| Thème | Valeur | Contraste sur surface / fond |
|---|---|---|
| Clair | `#85828F` | 3,76 / 3,47 |
| Sombre | `#797587` | 3,92 / 4,22 |
| AMOLED | `#6A6678` | 3,60 / 3,78 |

Le même jeton sert aux cases à cocher, interrupteurs et séparateurs porteurs de sens.

## 3. Typographie

Deux familles typographiques complémentaires, toutes deux sous **SIL Open Font License 1.1 (OFL)**.

### Police principale — Source Sans 3

- Famille : Source Sans 3.
- Type : sans-serif humaniste.
- Usage : interface, navigation, boutons, métadonnées et textes courants.
- Licence : SIL Open Font License 1.1.
- Dépôt officiel : <https://github.com/adobe-fonts/source-sans>
- Licence : <https://github.com/adobe-fonts/source-sans/blob/release/LICENSE.md>

Source Sans 3 apporte une typographie contemporaine, claire et adaptée aux interfaces.

### Police secondaire — Source Serif 4

- Famille : Source Serif 4.
- Type : serif contemporaine.
- Usage : titres de livres, citations et annotations.
- Licence : SIL Open Font License 1.1.
- Dépôt officiel : <https://github.com/adobe-fonts/source-serif>
- Licence : <https://github.com/adobe-fonts/source-serif/blob/release/LICENSE.md>

Source Serif 4 apporte une touche éditoriale aux contenus liés aux livres, sans donner une ambiance vintage à l'ensemble.

Les deux polices doivent être distribuées directement avec l'application. Aucun chargement depuis Google Fonts, Adobe Fonts ou un autre service externe à l'exécution. Les fichiers de licence et les mentions de copyright correspondantes doivent être conservés dans les ressources de l'application.

### Échelle typographique

Toutes les tailles sont exprimées en pixels logiques Flutter (dp / logical pixels).

| Style | Taille / hauteur de ligne | Graisse | Police |
|---|---:|---:|---|
| Titre principal | 28 / 36 | 700 | Source Sans 3 |
| Titre de section | 21 / 28 | 600 | Source Sans 3 |
| Sous-titre | 18 / 24 | 600 | Source Sans 3 |
| Titre de carte | 16 / 22 | 600 | Source Sans 3 |
| Corps principal | 16 / 24 | 400 | Source Sans 3 |
| Corps secondaire | 14 / 20 | 400 | Source Sans 3 |
| Libellé | 12 / 16 | 600 | Source Sans 3 |
| Métadonnées | 12 / 16 | 500 | Source Sans 3 |
| Boutons | 14 / 20 | 600 | Source Sans 3 |
| Gros indicateur | 30 / 36 | 700 | Source Sans 3 |
| Titre de livre éditorial | 18 / 25 | 600 | Source Serif 4 |
| Citation / annotation | 18 / 27 | 400 | Source Serif 4 |

Règles :

- Source Sans 3 est utilisée pour environ 90 % de l'interface.
- Source Serif 4 est réservée aux éléments éditoriaux.
- Ne pas multiplier les graisses.
- Les nombres de statistiques utilisent des chiffres tabulaires lorsque possible.
- Respecter le réglage de taille du texte Android, sans hauteur de composant rigide susceptible de couper le contenu.

## 4. Formes

Libria utilise des formes géométriques douces, avec des arrondis modérés. Les composants doivent être cohérents entre eux.

### Rayons

| Composant | Rayon |
|---|---:|
| Petits boutons / contrôles | 10 dp |
| Boutons principaux | 12 dp |
| Champs de saisie | 12 dp |
| Cartes classiques | 16 dp |
| Cartes principales | 18 dp |
| Couvertures de livres | 8 dp |
| Fenêtres modales | 20 dp |
| Bottom sheets | 24 dp (coins supérieurs) |
| Barre de navigation flottante | 26 dp |
| Chips / éléments entièrement arrondis | 999 dp |

### Bordures

- Épaisseur standard : 1 dp.
- Champs de saisie : bordure `outlineStrong` (voir section 2).
- Couleur issue du token `outline`.
- Utilisation discrète, pour séparer les surfaces sans tracer systématiquement le contour de chaque composant.
- Focus clavier ou accessibilité : contour accentué de 2 dp.

### Ombres et profondeur

Libria privilégie la séparation par les couleurs de surface plutôt que par les ombres.

- **Niveau 0 :** fond général.
- **Niveau 1 :** cartes et composants surélevés, différenciés par leur couleur de surface et éventuellement une bordure.
- **Niveau 2 :** éléments flottants comme la navigation inférieure et les fenêtres modales, avec une ombre légère.

Pour la navigation flottante en thème clair : ombre diffuse, opacité maximale de 8 %, flou de 20 dp, décalage vertical de 4 dp.

En sombre et AMOLED, privilégier les bordures et les surfaces plutôt que les ombres.

Éviter les effets de verre dépoli, les ombres multiples et les dégradés décoratifs.

## 5. Espacements

Échelle de base sur une unité de 4 dp :

`4 · 8 · 12 · 16 · 20 · 24 · 32 · 40 · 48 dp`

### Application pratique

| Emplacement | Espacement |
|---|---:|
| Padding horizontal des écrans | 20 dp |
| Padding écran compact | 16 dp |
| Espacement entre sections | 24 dp |
| Espacement entre cartes | 12 ou 16 dp |
| Padding intérieur des cartes | 16 dp |
| Espacement entre éléments liés | 8 dp |
| Espacement icône / libellé | 8 dp |
| Padding des boutons | 16 dp horizontal |
| Espacement des groupes secondaires | 32 dp |

Les zones tactiles interactives doivent mesurer au minimum 48 × 48 dp, même lorsque l'icône visible est plus petite.

## 6. Mouvement

Le mouvement constitue une partie importante de l'identité de Libria.

La règle principale : **une interface calme lorsqu'elle est immobile, mais vivante au moment des interactions.**

### Durées et courbes

| Interaction | Durée | Courbe |
|---|---:|---|
| Transition entre écrans | 280 ms | `easeInOutCubic` |
| Changement d'onglet | 220 ms | `easeInOutCubic` |
| Indicateur actif navigation | 200 ms | `easeInOutCubic` |
| Appui sur bouton | 90 ms | `easeOutCubic` |
| Retour après appui | 150 ms | `easeOutCubic` |
| Apparition des cartes | 220 ms | `easeOutCubic` |
| Ajout d'une couverture | 260 ms | `easeOutCubic` |
| Animation de progression | 320 ms | `easeOutCubic` |
| Ouverture d'un bottom sheet | 240 ms | `easeOutCubic` |
| Apparition d'un état vide | 200 ms | `easeOutCubic` |

Aucun rebond exagéré ni animation de ressort prolongée.

### Micro-interactions

| Événement | Comportement |
|---|---|
| Appui sur un bouton | Réduction d'échelle à 98 %, puis retour |
| Sélection d'un onglet | Indicateur actif animé, changement de remplissage de l'icône |
| Changement de thème | Fondu discret des surfaces et couleurs |
| Ajout d'un livre | Apparition progressive de la couverture avec léger agrandissement |
| Validation d'une action | Apparition d'une coche et changement de couleur |
| Modification d'une progression | Barre de progression animée |
| Ajout d'une annotation | Insertion avec fondu discret |
| Changement de filtre | Transition courte du contenu, sans rechargement visuel brutal |
| Scan ISBN réussi | Apparition douce de la fiche du livre détecté |
| État vide | Apparition progressive de l'icône, du texte et de l'action |

Les animations d'apparition des listes doivent être limitées aux éléments nouvellement affichés. Ne pas animer individuellement des dizaines de couvertures lors de chaque défilement.

### Accessibilité et performances

Le réglage Android « Supprimer les animations » doit être respecté. Flutter expose `MediaQueryData.disableAnimations`, qui permet de tenir compte du réglage de réduction des animations du système : <https://api.flutter.dev/flutter/widgets/MediaQueryData/disableAnimations.html>.

Lorsque cette option est activée :

- Supprimer les déplacements et agrandissements non essentiels.
- Remplacer les transitions complexes par un fondu très court, autour de 100 ms, ou un changement immédiat.
- Supprimer les apparitions décalées successives.
- Conserver les retours visuels indispensables aux actions.

Les animations doivent rester simples à calculer : transformations, opacité et transitions natives Flutter. Éviter les effets coûteux, les flous animés et les animations permanentes.

## 7. Barre de navigation inférieure

La navigation utilise une **barre flottante horizontale**, détachée des bords de l'écran.

### Dimensions et apparence

| Propriété | Valeur |
|---|---|
| Hauteur | 72 dp |
| Marge horizontale | 16 dp |
| Marge basse | 8 dp + zone de sécurité système |
| Rayon | 26 dp |
| Icônes | 21–22 dp |
| Libellés | 11 dp |
| Bouton + visible | 44 × 44 dp |
| Zone tactile minimale | 48 × 48 dp |

Le fond de la barre utilise une surface dédiée :

- Clair : `#FFFFFF`.
- Sombre : `#191920`.
- AMOLED : `#08080D`.

Une bordure très discrète permet de distinguer la barre du contenu.

### Organisation des onglets

**V1 : trois destinations**

1. **Accueil** : tableau de bord (lecture en cours, derniers ajouts, étagères).
2. **Bibliothèque** : livres, étagères, filtres, liste de souhaits et prêts.
3. **Réglages** : apparence, accent, données (export/import), à propos.

**V1.5 : une quatrième destination, « Activité »** : historique, statistiques, objectifs de lecture. L'ajout de cet onglet ne change pas la barre : même hauteur, mêmes marges.

Les prêts disposent d'une section « Prêtés » dans la bibliothèque, sans devenir un onglet. Le libellé « Bibliothèque » doit rester lisible avec un texte système agrandi (test à 130 % minimum) ; en cas de manque de place, seul l'onglet actif affiche son libellé.

### État actif

- Icône inactive : version Regular.
- Icône active : version Fill.
- Libellé actif : couleur d'accent.
- Fond actif : conteneur d'accent légèrement contrasté.
- Transition : 200 ms.

### Bouton +

Le bouton d'ajout est intégré à droite, sans constituer une cinquième destination de navigation.

Il utilise le fond accentué, une icône blanche et une forme arrondie.

Son appui ouvre un bottom sheet proposant trois actions :

- Scanner un ISBN.
- Rechercher un livre.
- Ajouter manuellement.

Il doit être accessible depuis tous les onglets.

## 8. Description de 5 écrans clés

### 8.1 Accueil

L'accueil est un tableau de bord éditorial aéré.

**Structure :**

- En-tête avec le titre de l'écran et accès aux actions principales.
- Carte principale « Lecture en cours », avec couverture, titre, auteur et progression.
- Aperçu des objectifs de lecture (V1.5 ; absent en V1, sans trou dans la mise en page).
- Activité récente (V1.5).
- Derniers livres ajoutés.

**Règles :**

- La lecture en cours est l'élément le plus important visuellement.
- Chaque section possède un titre explicite.
- Les statistiques restent discrètes.
- Pas de multiplication de petites cartes pour chaque information.
- Le bouton + reste disponible dans la navigation.

L'accueil doit être personnalisable plus tard, mais sa structure reste fixe en V1.

### 8.2 Bibliothèque

L'écran bibliothèque est pensé autour des couvertures.

**Structure :**

- Titre « Bibliothèque ».
- Recherche accessible en haut.
- Filtres sous forme de chips défilants horizontalement : Tous, À lire, En cours, Terminés, puis Abandonnés, En pause, Souhaits, Prêtés. Les quatre premiers sont visibles sans défilement.
- Contrôle de tri.
- Affichage grille par défaut.
- Possibilité de passer en liste.

**Grille :**

- Deux colonnes sur les écrans étroits.
- Trois colonnes lorsque la largeur disponible le permet.
- Couvertures au format 2:3.
- Images non déformées et non recadrées arbitrairement.
- Titre et auteur sous la couverture.
- Indicateur discret d'état de lecture.

La grille reste régulière en V1. La personnalisation de sa densité est disponible dans les paramètres.

Les livres prêtés sont accessibles via le filtre « Prêtés » et disposent de leur propre vue.

### 8.3 Fiche livre

La fiche livre met en valeur la couverture tout en restant pratique.

**Structure :**

- Grande couverture dans la partie supérieure.
- Titre en Source Serif 4.
- Auteur et informations bibliographiques.
- Statut de lecture.
- Bouton d'action principal.
- Progression de lecture lorsque pertinente.
- Description ou résumé.
- Annotations et passages sauvegardés.
- Historique de lecture.
- Informations de prêt si le livre est actuellement prêté.

**Actions principales selon l'état :**

- Ajouter à la liste de lecture.
- Commencer la lecture.
- Reprendre la lecture.
- Marquer comme terminé.
- Modifier les informations.
- Enregistrer ou gérer un prêt.

Une seule action principale doit ressortir visuellement.

### 8.4 Ajout par scan ISBN

L'écran de scan est immersif et fonctionnel.

**Structure :**

- Caméra occupant la majorité de l'écran.
- Cadre de détection fin, avec accent indigo.
- Instruction courte : « Placez le code-barres dans le cadre ».
- Bouton de lampe torche.
- Accès à la saisie manuelle.
- Bouton de fermeture.

Lorsqu'un ISBN est détecté :

- Détection visuellement confirmée (retour haptique léger si disponible).
- Le livre est **ajouté directement** à la bibliothèque.
- Une carte non bloquante apparaît au-dessus de la barre d'actions : couverture, titre, auteur, avec **« Annuler »** et **« Modifier »**. Elle disparaît d'elle-même après environ 5 secondes ; « Annuler » reste disponible tant qu'elle est visible.
- Scan unique (V1) : la caméra se met en pause pendant l'affichage de la carte. Scan multiple (V1.5) : la caméra reste active et les cartes s'empilent.
- Livre introuvable ou informations partielles : l'utilisateur est prévenu (voir section 10) et la saisie manuelle s'ouvre avec l'ISBN déjà rempli.
- ISBN déjà possédé : la carte propose « Ouvrir la fiche » ou « Ajouter un exemplaire ».

Ne pas multiplier les éléments graphiques pendant le scan. La caméra doit rester le point central.

### 8.5 État vide

Les états vides doivent être simples et élégants.

**Structure :**

- Icône linéaire de taille 40 dp environ.
- Titre clair et explicite.
- Description d'une ou deux lignes maximum.
- Action principale.

Exemple pour une bibliothèque vide :

> **Votre bibliothèque commence ici**  
> Ajoutez vos premiers livres pour commencer à organiser vos lectures.

Bouton principal : « Ajouter un livre ».

Aucune grande illustration, animation décorative ou décoration superflue.

Les mêmes règles s'appliquent aux états vides des prêts, annotations et historiques.

## 9. Règles de cohérence pour réutiliser ce style dans d'autres applications

L'objectif est de créer un système de design réutilisable, et non un thème exclusivement lié à Libria.

L'architecture visuelle repose obligatoirement sur trois couches.

### Couche 1 — Valeurs de base (Design Tokens)

Définir un ensemble centralisé de valeurs :

- Palette sémantique et thèmes.
- Typographie et échelle des textes.
- Espacements.
- Rayons.
- Bordures.
- Ombres.
- Durées d'animation.
- Courbes de transition.

Les écrans ne doivent jamais réinventer ces valeurs.

Pour une future application, il doit être possible de changer la couleur d'accent et l'identité secondaire sans devoir redessiner toute l'interface.

### Couche 2 — Composants

Créer des composants réutilisables et cohérents :

| Composant | Règle |
|---|---|
| Boutons | Hauteur et rayons standardisés |
| Champs de saisie | Bordures et focus cohérents |
| Cartes | Même logique de surfaces |
| Chips | Même hauteur et comportement |
| Dialogues | Même profondeur et animation |
| Bottom sheets | Même rayon et transitions |
| Barre de navigation | Identité flottante commune |
| Icônes | Même bibliothèque et épaisseur |
| États vides | Même composition minimale |
| Barres de progression | Même épaisseur et animation |

Un composant ne doit pas créer ses propres couleurs ou ses propres règles d'animation.

### Couche 3 — Écrans

Les écrans assemblent les composants et les tokens.

Ils peuvent avoir des compositions différentes, mais respectent toujours :

- La même hiérarchie typographique.
- Les mêmes espacements.
- Les mêmes règles d'alignement.
- Les mêmes comportements interactifs.
- Les mêmes principes d'accessibilité.
- Les mêmes animations.

### Ressources libres et licences

| Ressource | Choix | Licence |
|---|---|---|
| Police principale | Source Sans 3 | SIL OFL 1.1 |
| Police secondaire | Source Serif 4 | SIL OFL 1.1 |
| Icônes | Phosphor Icons | MIT |

- Dépôt Phosphor Icons : <https://github.com/phosphor-icons/core>
- Package Flutter Phosphor : <https://pub.dev/packages/phosphor_flutter>
- Licence MIT : <https://github.com/phosphor-icons/core/blob/main/LICENSE>

Phosphor est adapté au choix retenu : la bibliothèque propose les variantes Regular et Fill, ainsi que d'autres épaisseurs. Conserver les variantes nécessaires et inclure les mentions de licence MIT.

**Intégration des icônes (v1.1).** Les paquets Flutter de Phosphor sont communautaires et fragmentés (le paquet d'origine est signalé comme déprécié par des forks). Libria n'en dépend pas : elle embarque **uniquement les icônes utilisées** (Regular et Fill) depuis les fichiers officiels sous licence MIT, derrière une **classe d'icônes maison** (`LibriaIcons`). Les icônes sont des constantes statiques afin que Flutter retire celles qui sont inutilisées. Changer de source d'icônes ne touche que cette classe.

Aucune ressource graphique propriétaire ne doit être introduite sans vérification de licence. Les polices et icônes sont intégrées localement, sans téléchargement à l'exécution.

### Principes de réutilisation

1. Conserver la structure générale et les composants communs d'une application à l'autre.
2. Autoriser une identité colorimétrique différente par application, mais toujours avec ses déclinaisons clair, sombre et AMOLED.
3. Ne pas multiplier les styles de boutons, de cartes ou de navigation.
4. Préférer la simplicité à l'accumulation de fonctionnalités visuelles.
5. Préserver les performances sur les appareils modestes.
6. Respecter systématiquement les paramètres d'accessibilité du système.
7. Toute nouvelle fonctionnalité doit s'intégrer dans les composants existants autant que possible.

### Évolution future de Libria

La bibliothèque 3D est prévue pour une version ultérieure et ne fait pas partie du périmètre V1.

Le système actuel doit néanmoins conserver une séparation entre les données d'un livre et sa représentation visuelle. Cela permettra de réutiliser les couvertures, les états de lecture et les métadonnées pour une future expérience de bibliothèque 3D.

Cette évolution ne doit pas imposer de surcharge graphique à l'interface actuelle.

## 10. Compléments v1.1 (propositions, à valider sur téléphone)

### 10.1 Couverture de remplacement
Beaucoup de livres n'ont pas de couverture. Le remplacement est généré localement, jamais téléchargé : fond choisi parmi quatre surfaces teintées (dérivées de l'accent et des neutres) selon un hachage stable du titre, titre en Source Serif 4 (3 lignes maximum), auteur en Source Sans 3 sous le titre, bordure de 1 dp, rayon de 8 dp, ratio 2:3. Aucun motif ni illustration. Contraste texte/fond ≥ 4,5:1.

### 10.2 États d'erreur et hors ligne
Même composition que les états vides (icône 40 dp, titre, une ou deux lignes, action), avec l'icône d'état et un libellé ; jamais la couleur seule. Cas prévus :
- **Livre introuvable** : « Aucune fiche trouvée pour cet ISBN » ; actions « Saisir à la main » et « Réessayer ».
- **Hors ligne** : message discret, non bloquant ; la recherche en ligne est indisponible mais la bibliothèque reste utilisable ; saisie manuelle proposée.
- **Source indisponible** : même traitement que hors ligne, avec mention de la source.
- **Informations partielles** : bandeau d'information sur la fiche ajoutée (« Certaines informations sont manquantes »), action « Compléter ».
- **Caméra refusée** : explication, action vers les réglages système, saisie manuelle.

### 10.3 Message d'annulation (« Annuler »)
Carte flottante au-dessus de la barre de navigation, marge de 16 dp, rayon 14 dp, surface élevée avec bordure, texte 14/20, bouton « Annuler » en couleur d'accent. Durée : 5 secondes, 8 secondes si lecteur d'écran actif. Apparition : fondu et glissement de 8 dp, 200 ms. Une seule carte à la fois, la nouvelle remplace l'ancienne (sauf scan multiple).

### 10.4 Champs de formulaire
Libellé au-dessus du champ (12/16, graisse 600), champ de 52 dp de haut, rayon 12 dp, bordure `outlineStrong` 1 dp, focus 2 dp en accent. Message d'erreur sous le champ avec icône (12/16). Aucun champ obligatoire hormis le titre ; le bouton principal reste actif dès que le titre est saisi. Formulaire de saisie manuelle : section « Essentiel » (titre, auteur, ISBN) toujours visible, section « Détails » repliée (éditeur, date, pages, langue, format, série, couverture), section « Mon exemplaire » repliée (acquisition, prix, état, emplacement).

### 10.5 États de chargement
Pas d'effet scintillant permanent (coût et fatigue visuelle). Blocs fixes de la couleur de surface secondaire aux dimensions finales, avec un fondu de 150 ms à l'arrivée du contenu. Les couvertures arrivent par fondu de 150 ms.

### 10.6 Réglages
Liste groupée par sections (Apparence, Données, À propos), titres de section en libellé 12/16, lignes de 56 dp minimum. Apparence : thème (Automatique, Clair, Sombre, Noir pur), accent (six préréglages, pastilles de 40 dp), densité de la grille. Données : export, import, corbeille. À propos : créateur, licence GPL-3.0, crédits et licences des polices et icônes, déclaration claire de ce qui est envoyé sur Internet et vers qui.

### 10.7 Prêt
Feuille inférieure : « Prêté à » (nom libre, avec suggestions issues des noms déjà utilisés), date de prêt (aujourd'hui par défaut), date de retour facultative, rappel facultatif (interrupteur). Retour : un appui sur « Marquer comme rendu » dans la fiche, avec annulation. Un livre prêté affiche un indicateur discret sur sa couverture.

### 10.8 Annotations
Feuille ou écran plein selon la longueur : sélecteur de type (Note, Citation, Réflexion, Marque-page), champ de page ou de chapitre facultatif, zone de texte. Les citations utilisent Source Serif 4 18/27 avec un filet vertical d'accent de 3 dp. Insertion avec fondu discret.

---

**Fin de la fiche de direction artistique — Libria V1.1**
