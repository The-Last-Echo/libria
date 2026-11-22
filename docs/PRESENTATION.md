# Présentation du projet — Libria (nom de travail), bibliothèque personnelle

> Statut du document : version 0.1 — issue du prompt initial. Aucune décision n'a été ajoutée par rapport à ce qui a été formulé. Le détail et les statuts (Validé / À définir / Reporté) sont dans `SPECIFICATIONS.md`.

## 1. Vision

Créer une application mobile de gestion de **bibliothèque personnelle physique** : indépendante, open source, gratuite, grand public, moderne, particulièrement soignée visuellement, fiable et évolutive.

Le projet vise un **vrai produit**, pas une accumulation de fonctionnalités. La conception précède le développement.

## 2. Principes fondamentaux

- Fonctionnement **offline-first** : la bibliothèque reste accessible sans Internet.
- **Aucun compte obligatoire**, aucune dépendance obligatoire à un serveur central.
- **Respect de la vie privée.**
- **Respect des licences et des droits d'auteur.**
- L'utilisateur garde l'accès à ses données même si un service externe disparaît.
- **Architecture modulaire et évolutive**, adaptée à une petite équipe travaillant avec l'aide d'IA.
- **Interface de grande qualité** (priorité majeure).

Internet est **intégré et assumé** : il sert uniquement aux recherches de métadonnées, déclenchées par l'utilisateur, avec un minimum de données envoyées (ISBN ou recherche), et rien en arrière-plan sans lien avec une action. Pas de réglage « désactivable » (non vérifiable).

## 3. Grandes fonctionnalités envisagées

- **Modèle bibliographique à trois niveaux** : Œuvre → Édition → Exemplaire.
- **Organisation** : collections, étagères virtuelles, catégories automatiques par état de lecture, tags, étagères intelligentes.
- **Ajout de livres** : scan ISBN, recherche titre/auteur, ajout manuel, import CSV, scan multiple, détection de doublons. Couvertures : catalogues, galerie, photo.
- **Sources** : Open Library, Inventaire (Google Books écarté). Licences et CGU à vérifier.
- **Suivi de lecture** : progression, historique, relectures, sessions, chronomètre facultatif, objectifs, statistiques, rappels facultatifs.
- **Annotations** : notes, citations, réflexions, marque-pages, notes liées à une page ou un chapitre.
- **Prêts** : prêtés/empruntés, historique, personnes, dates de retour.

## 4. Design et expérience

Moderne, élégant, immersif, fluide, personnalisable, animations travaillées, excellente ergonomie. Références visuelles (sans copie) : GymMane et Streak.

## 5. Orientations techniques

Flutter, Dart, SQLite, Drift (recommandés, en attente de confirmation finale). Android en priorité ; iOS mis de côté. Licence GPL-3.0. Interface en français et anglais. Scanner de codes-barres sans composant Google (à valider).

## Distribution

Dépôt GitHub, releases APK automatiques via GitHub Actions. Niveau de présentation visé : celui de GymMane et Streak.

## 6. Méthode de travail

- Conception d'abord, **pas de code applicatif** avant demande explicite.
- Discussion progressive, une question principale à la fois.
- Critique constructive de chaque proposition importante.
- Décisions classées : **Validé / À définir / Reporté** ; rien n'est validé sans accord explicite.
- Plusieurs IA consultées ; leurs propositions sont analysées, jamais acceptées automatiquement.

## Périmètre

V1 : ajout (scan ISBN, recherche, manuel), fiche livre, bibliothèque, statuts de lecture, étagères et tags, notes et annotations, prêts, liste de souhaits, export/import, thèmes. V1.5 : scan multiple, statistiques, objectifs, étagères intelligentes, sessions, rappels. Le détail est dans `SPECIFICATIONS.md`.

## 7. Feuille de route générale

À construire ensemble. Ordre de travail annoncé :

1. Expérience utilisateur et organisation générale de l'application.
2. Fonctionnalités, cas limites, règles métier.
3. Modèle de données et architecture.
4. Sources externes, confidentialité, aspects légaux.
5. Identité visuelle.
6. Périmètre de la V1, puis développement.

## 8. Idées futures (préservées, hors V1 par défaut)

- Ville virtuelle évoluant avec les lectures
- Bibliothèque en 3D
- Gamification avancée
- Widgets Android
- Fiches auteurs enrichies
- Catalogue communautaire
- Fonctionnalités sociales
- Synchronisation entre appareils
- Gestion de fichiers EPUB et PDF personnels
