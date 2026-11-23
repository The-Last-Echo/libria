# Libria

Vocabulaire du domaine de Libria, bibliothèque personnelle de livres physiques. Les noms anglais indiqués entre parenthèses sont les termes canoniques à employer dans le code ; « livre » reste un terme générique d’interface, pas une entité métier.

## Catalogue

**Livre** (terme d’interface, sans entité `Book`) : Terme générique visible par la personne qui utilise l’application ; selon le contexte, il désigne une œuvre, une édition ou un exemplaire. Dans le code et les règles métier, employer le concept précis.
_Avoid_: `Book` comme entité canonique

**Œuvre (`Work`)** : Création intellectuelle indépendante de ses éditions et de ses exemplaires. L’historique de lecture est rattaché à l’œuvre.

**Édition (`Edition`)** : Publication particulière d’une œuvre, décrite notamment par son ISBN, sa maison d’édition, sa date, sa langue et son format.

**Exemplaire (`Copy`)** : Copie physique d’une édition, avec ses propres informations d’acquisition, de possession, d’état et d’emplacement. Un exemplaire emprunté reste actif après la clôture du prêt entrant et conserve le nom de son propriétaire.

**Bibliothèque (`Library`)** : Ensemble des œuvres qui possèdent au moins un exemplaire actif. Un exemplaire prêté, emprunté ou perdu reste actif ; un exemplaire donné ou vendu ne compte plus dans la Bibliothèque, même si son enregistrement est conservé.

**Identifiant bibliographique (`Identifier`)** : Valeur qui permet de reconnaître ou de relier une œuvre ou une édition, comme un ISBN ou un identifiant de catalogue.

**Maison d’édition (`Publisher`)** : Organisation qui publie une édition ; ce n’est pas le rôle de contribution `editor`.

**Série (`Series`)** : Ensemble d’œuvres liées par un ordre ou un univers éditorial.
_Avoid_: collection (pour désigner une série de livres)

**Personne contributrice (`Person`)** : Personne associée à la création ou à la publication d’une œuvre ou d’une édition.

**Contribution (`Contribution`)** : Lien entre une personne et une œuvre ou une édition, qualifié par un rôle.

**Rôle de contribution (`ContributionRole`)** : Nature de la participation d’une personne, par exemple auteur (`author`), traducteur (`translator`), illustrateur (`illustrator`), éditeur scientifique ou éditorial (`editor`) ou préfacier (`preface`). `editor` désigne une personne contributrice, tandis que `Publisher` désigne la maison d’édition.

**Sujet bibliographique (`Subject`)** : Genre ou thème descriptif associé à une œuvre par une source de métadonnées.
_Avoid_: étiquette personnelle

**Étiquette (`Tag`)** : Terme libre ajouté par la personne qui utilise Libria pour organiser ses œuvres.
_Avoid_: sujet bibliographique

## Organisation et souhaits

**Étagère (`Shelf`)** : Regroupement nommé d’œuvres dans la Bibliothèque ; en V1, les étagères sont créées et organisées manuellement. Les liens d’une œuvre avec ses étagères peuvent être conservés après son retrait de la Bibliothèque ; l’œuvre reste masquée tant qu’elle n’a aucun exemplaire actif.
_Avoid_: collection

**Étagère intelligente (`SmartShelf`)** : Étagère dont le contenu est défini par des critères de recherche enregistrés, prévue après la V1.

**Liste de souhaits (`Wishlist`)** : Ensemble des œuvres ou éditions que l’on souhaite acquérir, sans exemplaire associé.

**Élément de liste de souhaits (`WishlistItem`)** : Entrée de la liste de souhaits portant sur une œuvre ou, facultativement, une édition précise.

## Ajout et import

**Doublon (`Duplicate`)** : Résultat d’une vérification à trois niveaux : A, même ISBN normalisé ; B, même œuvre avec une autre édition, proposé comme suggestion non bloquante ; C, doublon potentiel repéré lors d’un import CSV. Pour A, la personne peut ouvrir la fiche existante, ajouter un exemplaire ou annuler ; pour C, elle peut conserver les deux entrées, ignorer ou fusionner après revue.

## Lecture

**Entrée de lecture (`ReadingEntry`)** : Enregistrement d’une tentative de lecture d’une œuvre. Une relecture crée une nouvelle entrée ; l’édition lue peut être précisée.

**Statut de lecture (`ReadingStatus`)** : État d’une entrée de lecture : à lire (`to_read`), en cours (`reading`), terminé (`finished`), abandonné (`abandoned`) ou en pause (`paused`). Le statut courant d’une œuvre est celui de sa dernière entrée.

**Progression de lecture (`ReadingProgress`)** : Position atteinte dans une entrée de lecture, exprimée en pages ou en pourcentage.

**Évaluation (`Rating`)** : Appréciation facultative d’une lecture, exprimée en étoiles et distincte d’une note libre d’annotation.

**Avis (`Review`)** : Appréciation personnelle et privée d’une lecture, comprenant facultativement une évaluation, un texte, ou les deux.
_Avoid_: annotation

**Séance de lecture (`ReadingSession`)** : Période de lecture enregistrée pour une entrée, prévue après la V1.

## Annotations

**Annotation (`Annotation`)** : Note libre, citation, réflexion ou marque-page portant sur une œuvre ; elle peut aussi être précisée par une édition ou une entrée de lecture selon le contexte.

## Exemplaires et prêts

**Possession (`Ownership`)** : Relation d’un exemplaire avec son propriétaire : possédé par la personne qui utilise Libria (`owned`) ou emprunté à quelqu’un d’autre (`borrowed`). Pour un exemplaire emprunté, le propriétaire courant est porté par cet exemplaire dans son nom de propriétaire.

**Disponibilité d’un exemplaire (`CopyAvailability`)** : État de gestion d’un exemplaire : disponible (`available`), prêté (`lent`), perdu (`lost`), donné (`given`) ou vendu (`sold`). `lent` et `lost` restent dans la Bibliothèque ; `given` et `sold` n’y comptent plus.

**Prêt (`Loan`)** : Emprunt temporaire d’un exemplaire, dans le sens sortant (prêté par la personne qui utilise Libria) ou entrant (emprunté par elle), avec son historique et ses dates éventuelles.

**Sens du prêt (`LoanDirection`)** : Direction d’un prêt du point de vue de la personne qui utilise Libria : prêté (`lent`) ou emprunté (`borrowed`).

**Partie à un prêt (`LoanParty`)** : Personne identifiée par un nom libre comme l’une des deux parties d’un prêt, qu’elle prête l’exemplaire ou le reçoive.
_Avoid_: `Borrower`, emprunteur seul

## Données et suppression

**Corbeille (`Trash`)** : Espace temporaire où sont placés les éléments supprimés afin qu’ils puissent être restaurés avant leur purge définitive.

**Archive de bibliothèque (`LibraryArchive`)** : Export complet et portable des données de la bibliothèque et de ses images, dans un format versionné indépendamment de la base locale ; les réglages de l’application n’en font pas partie.

## Métadonnées et images

**Source de métadonnées (`MetadataSource`)** : Catalogue externe consulté à la demande pour rechercher ou compléter des informations bibliographiques.

**Provenance (`Provenance`)** : Origine des informations bibliographiques et distinction entre les données récupérées d’une source et celles modifiées par la personne qui utilise Libria.

**Couverture (`CoverImage`)** : Image qui représente une édition ; elle peut venir d’un catalogue, de la galerie ou d’une photo.
