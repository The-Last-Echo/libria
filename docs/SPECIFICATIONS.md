# SPÉCIFICATIONS — Libria (nom de travail)

> Version 1.3
> **Statuts** : ✅ Validé · ❓ À définir · ⏸️ Reporté.
> **💡 Proposé** = recommandation de l'assistant, non validée tant que l'auteur ne l'a pas confirmée.
> **🔎 Vérifié** = constaté dans une source consultée (date : novembre 2026). **Hypothèse** = non vérifié.
> **(délégué)** = l'auteur a demandé à l'assistant de choisir ; choix révisable à tout moment.

---

## 1. Vision et objectifs

- ✅ Application mobile de gestion de bibliothèque personnelle physique.
- ✅ Indépendante, open source, gratuite, grand public (petits comme gros lecteurs).
- ✅ Moderne, particulièrement soignée visuellement, complète, fiable, évolutive.
- ✅ Très bonnes performances, y compris sur de grandes bibliothèques.
- ✅ Conception sérieuse avant tout code applicatif.
- ✅ Qualité de présentation de référence : dépôts GymMane et Streak (sans copie).
- ✅ **Différenciation** face aux applications existantes (§4bis) : meilleure interface, modèle Œuvre/Édition/Exemplaire, prêts et annotations, style commun, puis bibliothèque 3D (plus tard).

## 2. Principes fondamentaux

- ✅ Offline-first ; aucun compte ; aucun serveur central obligatoire.
- ✅ Respect de la vie privée, des licences et des droits d'auteur.
- ✅ L'utilisateur garde l'accès à ses données même si un service externe disparaît.
- ✅ Architecture modulaire, simple, adaptée à une petite équipe assistée par IA.
- ✅ **Internet intégré et assumé** (§10). Pas de réglage « désactivable », pas de variante d'APK sans Internet pour l'instant.
- ✅ Rien d'obligatoire à l'ajout d'un livre sauf le **titre** ; tout le reste est facultatif.

## 3. Public cible

- ✅ Grand public, sans profil unique.
- ✅ Langues de l'interface : **français et anglais** au lancement, autres langues plus tard (traductions communautaires).
- 💡 L'ajout doit être rapide, sans vocabulaire technique ; fonctions avancées accessibles mais jamais imposées.

## 4. Organisation générale

- ✅ Orientation **catalogue d'abord** : bibliothèque et livre en cours à l'accueil, bouton « + » toujours accessible.
- ✅ Modules : Bibliothèque, Ajout, Fiche livre, Organisation, Lecture, Annotations, Prêts, Statistiques, Réglages/Données.

## 4bis. Paysage existant et différenciation 🔎

Applications libres comparables repérées :
- **Openshelf** (F-Droid, licence GPL-3.0) : gestion de bibliothèque personnelle ; sources Open Library et Inventaire ; étagères intelligentes ; scanner libre avec reconnaissance ISBN par OCR ; statistiques (séries, objectifs de pages) ; statuts À lire / En cours / Lu / Abandonné / En pause ; recherche plein texte. Signalée « NonFreeNet » sur IzzyOnDroid car elle contacte aussi Google Books.
- **Openreads** (F-Droid, Flutter) : suivi de lecture ; ajout par Open Library, scan ou saisie ; statistiques ; import CSV Goodreads ; tags.

**Lecture détaillée d'Openshelf** (dépôt public, version 1.5.1 vue en novembre 2026) 🔎 :
- Développée en Flutter. Scanner à deux modes exclusifs : code-barres, ou lecture OCR de l'ISBN imprimé (Tesseract, libre) traitée en arrière-plan pour garder l'interface fluide. La bibliothèque de codes-barres utilisée n'a pas pu être identifiée.
- Recherche par titre, auteur, éditeur et ISBN, avec résultats qui arrivent au fil des sources, filtrage puis classement.
- Sources : Open Library, Inventaire, **Google Books**, et **Anna's Archive** (source optionnelle ajoutée en 1.3.1).
- Historique de possession (type, personne, date), date de fin obligatoire pour « Lu », tri par date de fin, dossier de base de données personnalisable, sauvegarde automatique Android.
- Permissions sur la fiche F-Droid : caméra, réseau, et **accès à tous les fichiers** (MANAGE_EXTERNAL_STORAGE).
- Mises à jour fréquentes : le projet est actif.

Leçons pour Libria : (a) l'OCR d'ISBN est utile pour les livres sans code-barres lisible, à garder en idée (⏸️) ; (b) la recherche multi-champs avec résultats progressifs est un bon modèle ; (c) traiter les images (couvertures) hors du fil principal ; (d) conserver l'état de chaque onglet ; (e) gérer proprement le bouton retour.
Différences voulues : Libria n'utilise **ni Google Books ni Anna's Archive** (bibliothèque parallèle dont la légalité est contestée, incompatible avec le principe de respect des droits d'auteur), et n'a pas besoin d'un accès à tous les fichiers : sélecteur de fichiers système uniquement (✅).

Conséquence : une grande partie de la V1 existe déjà ailleurs. ✅ Axes de différenciation retenus : design et fluidité, modèle Œuvre / Édition / Exemplaire, prêts et annotations, style commun aux applications de l'auteur ; ⏸️ bibliothèque 3D plus tard.
- 💡 « Meilleure interface » doit devenir **mesurable** : par exemple ajout d'un livre par ISBN en moins de 5 secondes, défilement fluide avec 5 000 livres, démarrage rapide, animations sans saccades sur un téléphone d'entrée de gamme. Critères chiffrés à fixer.
- 🔎 Prêts : Openshelf propose un historique de possession avec personne et date, ce qui recouvre probablement une partie de la fonction prêt ; annotations et éditions multiples : non constatées sur les fiches consultées.

## 5. Navigation et expérience utilisateur

- ✅ Premier lancement uniquement : tutoriel de 3 écrans maximum avec « Passer », terminé par « Ajoute ton premier livre » ; page « À propos » (créateur, licence, crédits) consultable ensuite. État vide de la bibliothèque soigné.
- ✅ Barre de navigation inférieure de 3 à 4 onglets, avec bouton « + » pour l'ajout.
- ✅ **V1 = Accueil · Bibliothèque · Réglages** ; **V1.5 = + Activité** (statistiques, objectifs, historique). La liste de souhaits est une section de la Bibliothèque. (Remplace la proposition précédente Bibliothèque · Lecture · Réglages.)
- ✅ Accueil : livre(s) en cours, puis dernières acquisitions, puis étagères.
- ✅ Bibliothèque : grille de couvertures ou liste, tri, filtres, recherche instantanée locale.
- ✅ Fiche livre : couverture, infos principales, statut, progression ; autres éditions et exemplaires accessibles sur demande.
- ✅ Annulation systématique après les actions rapides (ajout, suppression).

### Parcours à concevoir en détail
1. Premier lancement. 2. Ajout par ISBN. 3. Livre introuvable. 4. Scan en rafale (V1.5). 5. Retrouver un livre. 6. Lire (début, progression, fin, note). 7. Relire. 8. Prêter / emprunter. 9. Changement de téléphone (export/import).

## 6. Fonctionnalités détaillées

### 6.1 Gestion bibliographique
- ✅ Trois entités : Œuvre, Édition, Exemplaire, gardées en interne ; l'utilisateur voit « un livre ». Le scan crée les trois niveaux d'un coup.
- Informations : titres, sous-titres, auteurs, traducteurs, illustrateurs, éditeurs, dates, langues, ISBN et autres identifiants, pages, formats et dimensions, genres et sujets, séries et tomes, couvertures.
- ✅ Exemplaire : acquisition, prix, état, emplacement, propriétaire, statut.
- ✅ **Liste de souhaits** (livres que l'on veut acquérir). 💡 Modélisation : œuvre ou édition marquée « souhaitée », sans exemplaire.

### 6.2 Organisation
- ✅ V1 : étagères, tags, catégories automatiques par état de lecture.
- ✅ Étagères intelligentes (filtres enregistrés) : ensuite.
- ⏸️ « Étagères virtuelles » = rendu visuel 3D de la bibliothèque (§17). Les étagères d'organisation restent en V1.

### 6.3 Ajout de livres
- ✅ Méthode principale : scan ISBN. Autres : recherche titre/auteur, ajout manuel, import CSV, scan multiple, couvertures (catalogues, galerie, photo).
- ✅ Scan : **ajout direct avec bouton « Annuler »** ; correction possible ensuite.
- ✅ **Métadonnées récupérées au moment de l'ajout** (pas après) : le livre apparaît déjà renseigné. 💡 Délai maximal court ; en cas d'échec, proposition immédiate d'ajout avec les informations minimales.
- ✅ Livre introuvable ou informations partielles : **l'utilisateur est prévenu**, formulaire manuel pré-rempli avec l'ISBN. Une nouvelle tentative n'a lieu que sur action de l'utilisateur.
- ✅ Seul le titre est obligatoire ; objectif d'ajout rapide quand l'ISBN est connu.

### 6.4 Doublons
- ✅ **A — même ISBN** : normalisation ISBN-10/13 ; choix : ouvrir la fiche, ajouter un exemplaire, annuler.
- ✅ **B — même œuvre, autre édition** : suggestion non bloquante.
- ✅ **C — import CSV** : écran de revue (garder les deux, ignorer, fusionner).
- ⏸️ Fusion manuelle avancée : à concevoir avec beaucoup de précautions.

### 6.5 Suivi de lecture
- ✅ V1 : statut, progression, dates de début et de fin, relectures. Ensuite : sessions, chronomètre, objectifs, statistiques détaillées, rappels.
- ✅ Statuts : **À lire · En cours · Terminé · Abandonné · En pause**.
- ✅ Note (étoiles) et avis texte, privés.
- ✅ Une relecture crée une nouvelle entrée d'historique sans écraser les précédentes.

### 6.6 Annotations ✅
Notes libres, citations, réflexions, marque-pages, notes liées à une page ou un chapitre.

### 6.7 Prêts
- ✅ Prêtés et empruntés, historique, dates de retour. Noms saisis librement, pas d'accès aux contacts. Rappel de retour **facultatif**.
- ✅ (délégué) Prêter un exemplaire le passe automatiquement en « Prêté » ; le retour le remet « Disponible ». Un exemplaire emprunté a `ownership = borrowed` et son propriétaire courant est enregistré dans `owner_name` ; il est exclu des statistiques de possession. ❓ **En attente de confirmation (ticket #6)** : décision prise en session = il reste actif dans la Bibliothèque après la clôture du prêt entrant ; l'alternative recommandée est qu'il en sorte (nouvelle disponibilité « rendu ») en gardant son historique.

### 6.8 Données, export, sauvegarde
- ✅ V1 : export et import complets (données et images), export CSV.
- ✅ Ensuite : sauvegarde automatique vers un dossier choisi ; imports depuis d'autres services (services à choisir plus tard).

### 6.9 Rétention
- ✅ Leviers : ajout rapide, livre en cours à l'accueil avec progression en un geste, animations soignées, rappels de prêt, bilans périodiques, valeur accumulée.
- ✅ À éviter : notifications insistantes, culpabilisation, séries forcées.
- ✅ **Gamification légère** : objectifs de lecture (V1.5). La gamification avancée reste en idées futures.
- ⏸️ Idée liée : dans la bibliothèque 3D, un livre n'apparaît que lorsqu'il a été lu. 💡 Point d'attention : « livres possédés » et « livres lus » sont deux ensembles différents ; il faudra éviter la confusion avec le catalogue. Le modèle prévu (entrée de lecture avec date de fin) permettra déjà cette fonction plus tard, sans changement.

## 7. Règles métier

- ✅ ISBN stocké normalisé (ISBN-13), forme d'origine conservée si utile.
- ✅ Dates de publication partielles autorisées (année seule).
- ✅ Provenance conservée (source et date) ; une modification de l'utilisateur prévaut toujours sur la source.
- ✅ Suppression : corbeille avec délai.
- ✅ (délégué) **Statut de lecture rattaché à l'œuvre**, avec l'édition lue indiquée en option. Raison : changer d'édition ne doit pas dupliquer l'état « Terminé ».
- ❓ Durée de conservation de la corbeille.

## 8. Modèle de données

> ✅ = validé par l'auteur (version 0.9 du modèle).

*Le vocabulaire canonique du domaine (termes français et noms dans le code) est dans `GLOSSARY.md`, qui fait foi en cas de divergence ; les décisions d'architecture sont dans `docs/adr/`.*

### 8.1 Principes
- ✅ Identifiants uniques et dates de modification sur toutes les tables ; migrations versionnées et testées ; recherche locale rapide ; couvertures en fichiers avec miniatures.
- ✅ **Identifiants** : UUID version 7 (triés par date, bons pour l'index) sous forme de texte. À vérifier : prise en charge par la bibliothèque `uuid`.
- ✅ **Horodatages** : `created_at` et `updated_at` en millisecondes UTC (entiers). **Dates de lecture** : dates calendaires `AAAA-MM-JJ` (sans fuseau). **Dates de publication** : texte `AAAA`, `AAAA-MM` ou `AAAA-MM-JJ` (année seule autorisée).
- ✅ **Corbeille** : suppression logique par `deleted_at`. ✅ Purge définitive après 30 jours.
- ✅ **Montants** : entier en plus petite unité (centimes) + code de devise.
- ✅ **Provenance** : colonne JSON `provenance` sur Œuvre et Édition : pour chaque champ, `{source, fetched_at, user_edited}`. Un enrichissement ne remplit que les champs vides ou non modifiés par l'utilisateur.
- ✅ **Pas de données dupliquées au départ** (pas de colonnes de cache comme « auteur affiché » ou « statut courant ») : on mesure d'abord avec le script de 5 000 livres, on ajoute un cache seulement si c'est lent.
- ✅ **Clés étrangères activées**, contraintes `CHECK` sur les énumérations, index partiels pour tenir compte de la corbeille.

### 8.2 Tables

**works** (Œuvre) : `id`, `title`, `title_sort` (normalisé : minuscules, sans accents ni article initial), `subtitle`, `original_title`, `original_language`, `first_publication` (partielle), `description`, `series_id`, `series_position` (texte : « 1 », « 1.5 », « Hors-série »), `primary_edition_id` (édition dont la couverture est affichée), `provenance`, `created_at`, `updated_at`, `deleted_at`.

**editions** : `id`, `work_id`, `title`, `subtitle`, `isbn13` (normalisé), `publisher_id`, `publication_date` (partielle), `language`, `page_count`, `format` (poche, broché, relié, autre), `height_mm`, `width_mm`, `thickness_mm`, `cover_image_id`, `description`, `provenance`, horodatages. Index unique partiel sur `isbn13` (hors corbeille et hors valeur vide).

**identifiers** : `id`, `work_id` ou `edition_id` (exactement un des deux), `scheme` (isbn10, ean, oclc, openlibrary_work, openlibrary_edition, inventaire_uri, wikidata, autre), `value`. Unique sur (`scheme`, `value`). Sert à rattacher une nouvelle édition à une œuvre déjà connue.

**copies** (Exemplaire) : `id`, `edition_id`, `ownership` (`owned` ou `borrowed`), `owner_name` (vide = moi ; rempli pour un livre emprunté), `availability` (`available`, `lent`, `lost`, `given`, `sold`), `acquisition_date` (partielle), `acquisition_source` (texte libre : achat, cadeau, échange…), `price_minor`, `price_currency`, `condition` (neuf, très bon, bon, correct, abîmé), `location` (texte libre avec suggestions), `notes`, horodatages.

**people** : `id`, `name`, `name_sort`, identifiants externes facultatifs. **contributions** : `id`, `person_id`, `work_id` ou `edition_id` (exactement un), `role` (author, translator, illustrator, editor, preface), `position`. Les auteurs sont rattachés à l'œuvre ; traducteurs et illustrateurs à l'édition.

**publishers** : `id`, `name`. **series** : `id`, `name`, `name_sort`.

**subjects** (genres venant des sources) : `work_id`, `label`. **tags** (étiquettes personnelles) : `id`, `name`, `color`. **work_tags** : `work_id`, `tag_id`.

**shelves** (Étagère) : `id`, `name`, `icon`, `color`, `sort_order`, `kind` (`manual` en V1 ; `smart` en V1.5), `filter_json` (étagères intelligentes). **shelf_items** : `shelf_id`, `work_id`, `position`, `added_at`. ✅ Un seul concept « étagère » en V1 (le mot « collection » est abandonné ; les cycles sont couverts par `series`).

**reading_entries** (Entrée de lecture) : `id`, `work_id`, `edition_id` (édition lue, facultatif), `status` (to_read, reading, finished, abandoned, paused), `started_on`, `finished_on`, `progress_unit` (pages ou pourcentage), `progress_value`, `rating` (0 à 10 = demi-étoiles ; vide = non noté), `review`, horodatages.

**annotations** : `id`, `work_id`, `edition_id` (facultatif), `reading_entry_id` (facultatif), `kind` (note, quote, reflection, bookmark), `content`, `page` (entier), `page_label` (texte, ex. « xii »), `chapter`, horodatages.

**wishlist_items** : `id`, `work_id`, `edition_id` (facultatif), `priority`, `note`, `added_at`.

**loan_parties** (partie à un prêt ; remplace `borrowers`, voir `GLOSSARY.md`) : `id`, `name` (personnes à qui je prête ou qui me prêtent ; noms libres, pas de contacts). **loans** : `id`, `copy_id`, `direction` (`lent` ou `borrowed`), `party_id`, `lent_on`, `due_on` (facultatif), `returned_on` (vide = en cours), `reminder_at` (facultatif), `note`, horodatages. Index unique partiel : au plus **un prêt en cours par exemplaire**.

**images** : `id`, `kind` (cover, photo), `relative_path`, `width`, `height`, `sha256`, `source` (catalogue, galerie, caméra), `attribution` (texte), `created_at`. Les miniatures sont des fichiers de cache dérivés, absents de la base.

**reading_sessions** (V1.5) : `id`, `reading_entry_id`, `started_at`, `duration_s`, `page_from`, `page_to`. Créée par une migration en V1.5.

**search_index** : table de recherche plein texte (titres, sous-titres, auteurs, série, éditeur, ISBN, étiquettes). ✅ Tokenisation insensible aux accents. À vérifier dans le SQLite embarqué avec Drift.

### 8.3 Invariants et règles
1. **Livre visible dans la Bibliothèque** = œuvre ayant au moins un exemplaire **actif** : hors corbeille et de disponibilité `available`, `lent` ou `lost` (`given` et `sold` n'y comptent plus, leur enregistrement est conservé). Une œuvre sans exemplaire actif n'y figure pas : elle apparaît dans l'historique de lecture, la liste de souhaits ou la bibliothèque 3D future.
2. **Statut courant d'une œuvre** = statut de sa dernière entrée de lecture (par `started_on`, puis création). ✅ Une nouvelle entrée « À lire » après une lecture terminée devient donc le statut courant, et les filtres de statut de la Bibliothèque utilisent ce statut courant, pas l'historique des entrées (ticket #7). ❓ **Précision à confirmer** : une entrée sans `started_on` (cas d'une entrée « À lire ») compte comme la plus récente, puis départage par création ; sans cela l'ancienne entrée datée l'emporterait. Aucune entrée = pas de statut. Une relecture = nouvelle entrée, les précédentes restent.
3. **Prêter** un exemplaire : crée un prêt en cours, passe `availability` à `lent`. **Rendre** : renseigne `returned_on`, repasse à `available`. Un exemplaire emprunté a `ownership = borrowed`, son propriétaire dans `owner_name`, et n'entre pas dans les statistiques de possession. ❓ Effet du retour d'un emprunt entrant sur l'activité de l'exemplaire : en attente de confirmation (voir §6.7).
4. **Ajout par ISBN** : (a) normaliser l'ISBN ; (b) si une édition avec cet ISBN existe → doublon niveau A ; (c) sinon, chercher une œuvre par identifiant externe (Open Library, Inventaire) → rattacher la nouvelle édition à cette œuvre ; (d) sinon, créer œuvre, édition et exemplaire ; (e) suggestion de niveau B (même titre normalisé et même premier auteur) non bloquante.
5. **Suppression** : supprimer un exemplaire le met en corbeille ; si c'était le dernier, l'œuvre quitte la Bibliothèque mais garde ses entrées de lecture, notes et édition. Supprimer une œuvre met en corbeille en cascade ses éditions, exemplaires, entrées de lecture, annotations et prêts, restaurables ensemble.
6. **Liste de souhaits** : quand un exemplaire est ajouté pour une œuvre souhaitée, proposer de la retirer de la liste.
7. ✅ **Étagères manuelles** (ticket #6) : les liens entre une œuvre et ses étagères sont conservés quand son dernier exemplaire quitte la Bibliothèque ; l'œuvre reste masquée tant qu'elle n'a aucun exemplaire actif.
8. **Enrichissement** : jamais d'écrasement d'un champ marqué `user_edited`.
9. **Ajout minimal** : seul le titre est obligatoire ; auteur, ISBN et le reste sont facultatifs.

### 8.4 Index principaux (à confirmer par mesure)
`works(title_sort)`, `editions(work_id)`, `editions(isbn13)` partiel unique, `copies(edition_id)`, `copies(availability)`, `reading_entries(work_id, started_on)`, `reading_entries(status)`, `contributions(person_id)`, `annotations(work_id)`, `loans(copy_id)` partiel unique sur prêts en cours, `identifiers(scheme, value)` unique.

### 8.5 Export et import
- ✅ **Archive** (fichier ZIP) : un fichier JSON avec numéro de version du format (indépendant de la version de la base) et un dossier d'images. L'import accepte les anciennes versions du format.
- ✅ **CSV** : une ligne par exemplaire, colonnes lisibles, pour tableur.
- ✅ Avertissement à l'export : l'archive contient les noms des personnes concernées par les prêts.
- ✅ Les réglages de l'application ne font pas partie de l'archive de bibliothèque (à confirmer).

### 8.6 Tests de données
Normalisation ISBN (dont ISBN-10 vers ISBN-13), détection de doublons A/B/C, rattachement à une œuvre, migrations entre toutes les versions du schéma, aller-retour export/import, corbeille et restauration en cascade, un seul prêt en cours par exemplaire, générateur de 5 000 livres factices pour les mesures.

## 9. Architecture technique

- 🔎 **Drift** : bibliothèque active (version 2.35 publiée en septembre 2026), décrite comme stable ; fonctions de migration et de vérification de schéma, exécution en arrière-plan, extension de recherche plein texte FTS5.
- ✅ **Flutter, Dart, SQLite, Drift** confirmés par l'auteur après vérification.
- ✅ Android en priorité ; ⏸️ iOS mis de côté pour l'instant.
- ✅ Quatre couches : interface, logique métier, données locales, connecteurs de sources.
- ✅ Conventions de code et règles de collaboration portées par `AGENTS.md`, `GLOSSARY.md` et `docs/adr/` (plus de fichier `CONVENTIONS.md` séparé).
### Gestion d'état 🔎
- Les comparatifs récents (articles de blog, niveau de preuve moyen) convergent : **Riverpod** est le choix par défaut pour une nouvelle application ; Bloc pour des équipes qui veulent une structure stricte ; Provider pour de très petites applications ou l'existant.
- Riverpod : version 3.4.1 (juillet 2026), version 3.0 stable depuis septembre 2025. ⚠ L'auteur a indiqué que la 3.0 est une version de transition et qu'une 4.0 pourrait arriver relativement tôt : des changements incompatibles sont possibles.
- ✅ Choix validé : **Riverpod, sans génération de code pour l'état**, et logique métier dans des classes Dart simples (dépôts, services) indépendantes de Riverpod : changer d'outil d'état resterait alors peu coûteux.

### Navigation 🔎
- **go_router** : paquet de l'équipe Flutter, version 18.x, déclaré « complet » (corrections de bugs et stabilité, pas de nouvelles fonctions prévues) ; gère une barre de navigation persistante via ShellRoute.
- ✅ Choix validé : go_router avec barre de navigation inférieure **personnalisée** et état de chaque onglet conservé.

### Fondations de l'interface 🔎
- **Flutter 3.47 (12 août 2026)** : Material et Cupertino sont désormais des paquets autonomes (`material_ui` et `cupertino_ui`, versions 1.0), d'adoption facultative ; les copies du SDK sont gelées depuis Flutter 3.44. Une source tierce indique qu'elles seront dépréciées à partir de novembre 2026 (non confirmé par la documentation officielle).
- **Material 3 Expressive** : une implémentation officielle est annoncée comme en cours, non disponible.
- **Polices** : le paquet `google_fonts` télécharge les polices à l'exécution sauf si les fichiers sont fournis dans l'application. 💡 Fournir les polices dans l'application (licence OFL à inscrire dans les licences), afin qu'aucune requête vers Google ne soit faite : cohérent avec la promesse de vie privée.

### Scanner de codes-barres
- 🔎 `mobile_scanner` : s'appuie sur ML Kit (composant Google non libre) → 💡 à éviter pour F-Droid.
- 🔎 `flutter_zxing` (4.0, en version candidate) : moteur zxing-cpp intégré, sans ML Kit ni services Google, annoncé compatible avec les builds F-Droid, mode de scan en série ; nécessite une version récente de Flutter.
- 🔎 `lightweight_barcode_scanner` (0.4.0) : autre option sans ML ni services Google, plus récente.
- 🔎 Précisions sur `lightweight_barcode_scanner` 0.4.1 (README consulté) : licence Apache-2.0 ; seule permission requise : la caméra ; lit l'EAN-13 (format des ISBN) ; limite des formats lus ; fenêtre de scan ; modes de scan unique, continu ou « distinct » (utile pour scanner une série) ; zoom automatique pensé pour les codes-barres linéaires ; lecture possible d'une image de la galerie ; Android 7.0 minimum. Limites : version 0.x, une seule personne éditrice, très peu d'utilisateurs, et le README précise que le comportement de la caméra n'est pas validé sur appareils réels.
- ❓ **Choix du scanner non tranché** : `lightweight_barcode_scanner` et `flutter_zxing` sont tous deux jeunes. ✅ Les isoler derrière une interface interne unique (changer de bibliothèque ne touche alors que quelques fichiers), puis décider après un **test sur plusieurs téléphones réels** (ISBN en EAN-13, faible lumière, livres brillants ou courbés).
- 💡 Prévoir la validation de la somme de contrôle de l'ISBN (préfixe 978/979) pour rejeter les lectures erronées, et une alternative quand un livre n'a pas de code-barres (recherche manuelle).

## 10. Sources externes

- ✅ Internet intégré et assumé : requêtes uniquement sur action de l'utilisateur ; seul l'ISBN ou la recherche est envoyé ; aucun identifiant ni analyse ; résultats conservés localement ; explication claire à l'utilisateur.
- ✅ Google Books et Anna's Archive non retenus.
- 🔎 **Open Library** (ticket #2, pages officielles `/developers/api` et `/developers/licensing`, consultées en novembre 2026) : API prévues pour des recherches humaines en temps réel, **pas comme base de données pour des services tiers** ; priorité aux projets ouverts ; **1 requête/seconde** par défaut, **3 requêtes/seconde** si l'application s'identifie par un `User-Agent` avec nom et e-mail de contact ; mettre les réponses en cache ; préférer `search.json` à de nombreuses requêtes unitaires ; pas de téléchargement en masse (utiliser les exports mensuels) ; abus = limitation ou blocage ; formulaire d'enregistrement d'application proposé. Couvertures : API dédiée, 100 recherches par identifiant et par adresse toutes les 5 minutes. Licence : aucun nouveau droit revendiqué sur la base, mais des droits peuvent exister sur certaines contributions ; **rien d'établi pour les couvertures**.
- ❓ Le `User-Agent` exige une adresse de contact visible publiquement (application open source) : prévoir une adresse dédiée au projet, pas une adresse personnelle.
- 🔎 **Inventaire** (ticket #3 ; rapport de l'agent, **non vérifié de façon indépendante** : la documentation est une page générée par script) : données bibliographiques décrites comme CC0 (à distinguer des données tierces), serveur sous AGPL-3.0 ; résolution publique par ISBN (`/api/entities/by-uris?uris=isbn:...`) avec lien édition → œuvre ; `User-Agent` avec contact demandé ; limites par route et HTTP 429 en cas de dépassement, sans quota global publié ; couvertures exposées sans licence structurée (certaines viennent d'Open Library ou de Wikimedia, retrait possible sur demande).
- ❓ **Couvertures** : stockage local, attribution et contenu de l'archive d'export à décider (ticket #10) ; couverture réelle des deux sources sur de vrais livres, dont français, à mesurer (ticket #11).
- 💡 Risque : dépendance à deux services associatifs. Mesures : un module par source, cache local, saisie manuelle toujours possible, usage modéré.
- ❓ Licences des couvertures à vérifier avant de les stocker durablement.
- ⏸️ Base communautaire facultative de fiches vérifiées (§17).

## 11. Confidentialité et aspects légaux

- ✅ Aucun accès à « tous les fichiers » : sélecteur de fichiers du système pour l'import et l'export ; pour la sauvegarde automatique (V1.5), dossier choisi par l'utilisateur via le système (hypothèse à vérifier à l'implémentation).
- ✅ Licence **GPL-3.0**. ❓ Vérifier la compatibilité des licences des dépendances.
- ❓ Texte honnête sur ce qui sort du téléphone, vers qui (README, « À propos », tutoriel).
- ❓ Permissions : caméra, notifications ; stockage des images ; licences des couvertures.

## 12. Design et identité visuelle

- ✅ Priorité majeure : moderne, élégant, immersif, fluide, personnalisable, animations travaillées.
- ✅ Nom : **Libria**, disponibilité vérifiée par l'auteur.
- ✅ Créer un **système de design** réutilisable dans toutes les applications de l'auteur (« ultra clean, propre, pratique »).
- 💡 Le construire d'abord dans Libria, dans un dossier isolé, puis l'extraire en paquet séparé quand une deuxième application en a besoin (éviter la généralisation prématurée).
- ✅ Le style choisi servira de base à toutes les prochaines applications de l'auteur : barre de navigation inférieure soignée, petites animations, rendu propre.
- ✅ **Architecture du système de design en trois couches** (validée) : (1) *tokens* (couleurs, typographie, espacements, rayons, ombres, durées et courbes d'animation) ; (2) *composants* maison (barre de navigation, boutons, cartes, feuilles, champs, états vides) ; (3) écrans. Les composants s'appuient sur les briques de base de Flutter et, au besoin, sur `material_ui` (accessibilité, champs de saisie), **sans jamais l'exposer directement aux écrans** : si Material change, seuls les composants sont touchés. Cela répond au risque créé par la séparation Material/Cupertino et par l'arrivée de Material 3 Expressive.
- 💡 Animations : transitions et micro-interactions (appui, ajout d'une couverture, changement d'onglet) avec les animations intégrées de Flutter ; mouvement à ressort pour le côté vivant ; respect du réglage système « réduire les animations » ; budget de performance mesuré en mode profil sur un téléphone d'entrée de gamme.
- ✅ **Fiche de direction artistique « Indigo Graphite »**, désormais en **version 1.1** (fichier `libria-direction-artistique.md`), document de référence du système de design, séparé des spécifications car réutilisable par d'autres applications. Les valeurs ajoutées en v1.1 (préréglages d'accent, bordures de champ, compléments de la section 10) sont des propositions à valider à l'usage sur téléphone.
- 🔎 Contenu : thèmes clair, sombre et noir pur ; accent indigo (`#6556B8` clair, `#A99AFF` sombre, `#B6AAFF` noir pur) personnalisable ; polices Source Sans 3 (interface) et Source Serif 4 (titres de livres, citations), licence OFL, fournies dans l'application ; icônes Phosphor (MIT) ; rayons modérés, séparation par les surfaces plutôt que par les ombres ; mouvement sobre, sans ressort ni rebond ; barre de navigation flottante de 72 dp ; réglage Android de réduction des animations respecté.
- 🔎 **Contrastes calculés** (WCAG) sur les trois thèmes : tous les couples texte/fond de la palette atteignent au moins 4,5:1 (le plus faible : texte atténué sur surface secondaire en thème clair, 4,71:1). Les bordures, elles, sont à 1,2–1,6:1 : correct pour de la décoration, **insuffisant (3:1 requis) pour délimiter un champ de saisie** quand la bordure est le seul repère.
- ✅ **Ajustements validés (v1.1 de la fiche)** :
  1. *Navigation* : voir §5 (3 onglets en V1, Activité en V1.5) ; avec 4 onglets plus le bouton « + » dans 72 dp, le libellé « Bibliothèque » risque d'être serré sur écran étroit ou avec un texte agrandi ; à tester.
  2. *Scan* : la fiche prévoit un écran de confirmation après détection ; la décision validée est un **ajout direct avec « Annuler »** et correction possible. L'aperçu devient une carte non bloquante « Ajouté — Annuler / Modifier ». En scan multiple (V1.5), la caméra reste active.
  3. *Filtres de la bibliothèque* : la fiche liste Tous, À lire, En cours, Lus, Prêtés ; il manque Abandonné, En pause et la liste de souhaits. Chips défilants avec les principaux visibles et le reste regroupé. Harmoniser « Lus » / « Terminé ».
  4. *Bouton « + »* : l'appui ouvre une feuille à trois actions (scanner, rechercher, saisie manuelle), soit un appui de plus avant le scan ; garder pour la clarté, mesurer face à l'objectif des 5 secondes.
  5. *Icônes* : le paquet officiel `phosphor_flutter` est signalé comme déprécié par des forks communautaires, et plusieurs forks non officiels coexistent. 💡 Plutôt que dépendre d'un paquet instable, embarquer **uniquement les icônes utiles** (variantes Regular et Fill) derrière notre propre classe d'icônes (couche composants) ; utiliser des constantes statiques pour que Flutter retire les icônes inutilisées.
  6. *Couleur d'accent personnalisable en V1* : six préréglages, chacun en trois variantes (clair, sombre, noir pur) dont les contrastes ont été calculés ; tout nouveau préréglage est vérifié de la même façon. Bordures de champ renforcées par un jeton dédié (≥ 3:1).
  7. *Polices* : Source Sans 3 couvre les langues latines, grecques et cyrilliques mais pas toutes les écritures ; prévoir des polices de repli si d'autres langues arrivent ; mesurer le poids des fichiers (limiter les graisses).
  8. *Couleur dynamique d'Android* : non prévue par la fiche ; exclue de la V1.
- ✅ **Manques comblés par la section 10 de la fiche v1.1** (valeurs à confirmer sur téléphone) : couverture de remplacement quand un livre n'en a pas (cas fréquent), états d'erreur et hors ligne (livre introuvable), message « Annuler » après une action, champs de formulaire et saisie manuelle, écran Réglages, parcours de prêt, éditeur d'annotations, états de chargement.
- ❓ Palette, typographie, thèmes (clair, sombre, noir pur), couleur dynamique d'Android, personnalisation : à définir à partir des maquettes.

## 13. Tests et qualité

- ✅ Tests automatiques : normalisation ISBN, doublons, migrations, import/export.
- ✅ CI à chaque modification : tests, analyse, compilation.
- ✅ Script de génération de fausses données (ex. 5 000 livres) pour les tests de performance.
- ❓ Accessibilité.

## 14. Distribution et feuille de route

### Méthode et avancement du développement
- ✅ Le développement est conduit avec les **skills de Matt Pocock** (agent dans VS Code, suivi par GitHub Issues sur `The-Last-Echo/libria`) : clarification et glossaire (`/grill-with-docs`), carte des décisions restantes (`/wayfinder`), puis par tranche verticale `/to-spec`, `/to-tickets`, `/implement` avec TDD et revue de code. L'auteur garde la main sur toutes les décisions.
- ✅ Répartition des documents : `docs/SPECIFICATIONS.md` = référence produit ; `GLOSSARY.md` = vocabulaire du domaine (termes français et noms dans le code) ; `docs/adr/` = historique des décisions d'architecture ; tickets GitHub = spécifications et travail par fonctionnalité ; `AGENTS.md` = règles de collaboration avec les agents.
- ✅ Le squelette de code proposé par Claude (« phase 0 ») n'est **pas adopté** : le code de base sera produit par le processus ci-dessus. Les éléments vérifiés à cette occasion (palette et contrastes de la fiche de style, ISBN, schéma de base) restent des références dans ce document et dans la fiche.
- ✅ **Identifiant d'application Android : `com.thelastecho.libria`** (vérifié inexistant par l'auteur). Se crée avec `flutter create --org com.thelastecho --project-name libria`. Non modifiable après publication.
- 🔎 Constats d'outillage (novembre 2026, Flutter 3.50.1, Dart 3.14) à respecter dans le premier ticket de code :
  - l'import `package:flutter/material.dart` est signalé obsolète : utiliser `package:material_ui/material_ui.dart` (et `cupertino_ui` pour les localisations Cupertino) ;
  - l'option `--delete-conflicting-outputs` de `build_runner` n'existe plus ;
  - avec Drift 2.35, les paquets `sqlite3_flutter_libs` et `sqlcipher_flutter_libs` sont des versions vides « fin de vie » tirées par `drift_flutter` : sans effet, à surveiller ;
  - `flutter analyze` renvoie un code d'erreur dès qu'une simple « info » apparaît : à prendre en compte dans la CI ;
  - le motif de contrainte `check(colonne.isIn([...]))` de Drift déclenche l'avertissement `recursive_getters`, cosmétique et documenté.
- ❓ Mettre la CI GitHub (analyse, tests, compilation de contrôle) et la release automatique d'APK signés en place : tickets à créer ; voir `docs/SIGNING.md` dans l'archive d'origine pour la marche à suivre de la clé de signature (à reprendre dans un ticket).

### Périmètre
- ✅ **V1** : ajout (ISBN, recherche, manuel), fiche livre, bibliothèque (tri, filtres, recherche), statuts, étagères et tags, progression et relectures de base, notes et avis, annotations, prêts, liste de souhaits, export/import, thèmes, tutoriel et « À propos ».
- 💡 **V1.5** : scan multiple, import CSV externes, étagères intelligentes, sessions et chronomètre, objectifs, statistiques, rappels, gamification légère, sauvegarde automatique.
- **V2 et plus** : §17.

## 15. Décisions

Voir les statuts ✅ dans chaque section. Principales : offline-first, Internet assumé, catalogue d'abord, trois entités, scan à ajout direct, métadonnées à l'ajout, doublons A/B/C, statuts de lecture, export/import en V1, GPL-3.0, nom Libria, GitHub + CI, périmètre V1, FR + EN, Android prioritaire, iOS mis de côté.

## 16. Questions ouvertes

1. Critères mesurables de « meilleure interface ».
2. Choix du scanner après test réel.
3. Disponibilité du nom Libria.
4. Valider le modèle de données détaillé (§8).
5. OCR d'ISBN : utile plus tard ?
6. Vérification à l'implémentation : sauvegarde automatique vers un dossier choisi, sans accès à tous les fichiers.
8. Palette, typographie, thèmes, personnalisation.
9. Licences des couvertures, conditions d'usage des API.
10. Durée de la corbeille : 30 jours proposés.
11. Cycle de vie d'un exemplaire **emprunté** (ticket #6) : session = il reste actif après le retour ; à confirmer (alternative : nouvelle disponibilité « rendu », qui le sort de la Bibliothèque). Le propriétaire est porté par `owner_name` (le même nom figure aussi dans le prêt entrant : doublon possible).
12. ✅ Statut courant et relectures : résolu (ticket #7), sous réserve de la règle des entrées sans date de début (voir §8.3, règle 2).
13. Vocabulaire : « note » désigne à la fois l'évaluation (étoiles) et un type d'annotation ; choisir deux termes distincts.
14. Signification du type d'image `photo` (photo de quoi ?) ou suppression.
15. ✅ Résolu (ticket #6) : les liens d'étagères sont conservés, l'œuvre reste masquée (§8.3, règle 7).

## 17. Idées futures (⏸️ à conserver)

- Ville virtuelle évoluant avec les lectures ; **bibliothèque en 3D** (étagères virtuelles), où les livres lus viennent s'ajouter
- Gamification avancée
- Widgets Android
- Fiches auteurs enrichies
- Catalogue communautaire ; **base communautaire facultative** : envoi opt-in, vers un serveur dédié, de fiches de livres vérifiées (jamais de données personnelles). Points à étudier : hébergement, coût, modération, vérification, licences, compatibilité avec le principe sans serveur
- Fonctionnalités sociales
- Synchronisation entre appareils
- Gestion de fichiers EPUB et PDF personnels
- Variante d'APK sans Internet
- Fusion manuelle avancée de doublons
- iOS
- Lecture OCR de l'ISBN imprimé (pour les livres sans code-barres lisible), inspirée d'Openshelf ; à étudier avec une bibliothèque libre
- Imports depuis d'autres services (Goodreads et autres)

> Aucune idée n'est supprimée ni intégrée d'office à la V1.

## Journal des modifications

- v0.1 — Création. v0.2 — Catalogue d'abord, GitHub + CI. v0.3 — Internet validé ; propositions.
- v1.3 — Fusion des modifications des sessions des tickets #6 et #7 ; faits vérifiés des recherches Open Library et Inventaire (tickets #2 et #3) ; deux points marqués à confirmer (retour d'un emprunt, entrées sans date de début).
- v1.2 — Synchronisation avec `GLOSSARY.md` et les ADR 0001 à 0005 : `borrowers` devient `loan_parties`, définition de la Bibliothèque précisée selon la disponibilité des exemplaires ; points ouverts 11 à 15 ajoutés.
- v1.1 — Développement confié aux skills de Matt Pocock ; squelette « phase 0 » non adopté ; identifiant Android `com.thelastecho.libria` ; constats d'outillage Flutter 3.50.
- v1.0 — Modèle de données validé ; nom Libria vérifié ; phase 0 du développement lancée et livrée (non compilée).
- v0.9 — Onglets et scan validés ; fiche de direction artistique v1.1 produite (préréglages d'accent, bordures de champ, compléments) ; modèle de données détaillé proposé (§8).
- v0.8 — Fiche de direction artistique reçue et analysée ; contrastes calculés ; ajustements recommandés (navigation, scan, filtres, icônes, accent) ; manques identifiés.
- v0.7 — Validés : Riverpod, go_router + barre personnalisée, architecture de design en trois couches, exclusion de Google Books et Anna's Archive, pas d'accès à tous les fichiers. Direction artistique confiée à un dialogue externe.
- v0.6 — Openshelf lu en détail ; recherche état d'application (Riverpod), navigation (go_router), fondations d'interface (séparation Material/Cupertino de Flutter 3.47, polices) ; architecture du système de design proposée ; scanner isolé derrière une interface validé.
- v0.5 — Réponses : différenciation validée, 3 onglets V1, objectifs de lecture V1.5, 3D reportée, stack confirmée, scanner en attente de test (lecture du README de lightweight_barcode_scanner), OpenAPK examiné.
- v0.4 — Intégration des réponses de l'auteur ; vérifications (Open Library, Inventaire, scanners, Drift) ; paysage concurrent ; décisions déléguées ; nom Libria, GPL-3.0, FR + EN.
