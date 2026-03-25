---
name: al-offres
description: "Création et gestion des offres immobilières : types de biens, transactions, lots, conditions financières, mandats, diagnostics, photos via MCP ImmoLabs."
---

# Offres Immobilières — Guide Complet Arthur Loyd Bretagne

## Rôle de ce document

Ce document décrit le workflow complet de création et gestion des offres immobilières via les outils MCP ImmoLabs : types de biens, transactions, champs critiques, conditions financières, mandats, services et diagnostics. Consulte-le dès qu'une question porte sur la création, modification ou gestion d'une offre, d'un lot, de photos ou de conditions commerciales.

---

## 1. Workflow de création d'une offre

### Étape 1 — Vérifier l'existence
```
search_offers → chercher par adresse pour éviter les doublons
```

### Étape 2 — Créer le propriétaire (si inexistant)
```
search_contacts → vérifier si le contact existe
search_accounts → vérifier si la société existe
create_account → créer la société si nécessaire
create_contact → créer le contact si nécessaire
```

### Étape 3 — Créer l'offre
```
create_offer → avec adresse, ville, code postal + au moins 1 lot
```
Champs obligatoires :
- **address** : adresse du bien
- **city** : ville
- **postalCode** : code postal
- **propertyType** : type de bien
- **transactionTypes** : types de transaction (tableau)

### Étape 4 — Ajouter des lots (si multi-lots)
```
add_lot_to_offer → si l'adresse héberge plusieurs locaux
```
Chaque lot représente un local distinct dans un même immeuble/adresse.

### Étape 5 — Ajouter les photos
```
upload_offer_photo → photos du bien (façade, intérieur, plans)
```

### Étape 6 — Activer l'offre
```
update_offer → passer le statut en "active"
```

---

## 2. Types de biens

| Code | Label | Cas d'usage |
|------|-------|-------------|
| `bureau` | Bureau | Locaux tertiaires, open-space, bureaux individuels |
| `commerce` | Commerce | Boutiques, restaurants, locaux commerciaux pied d'immeuble |
| `entrepot` | Entrepôt | Stockage, logistique, plateformes |
| `local-activite` | Local d'activité | Mixte bureau/atelier, artisanat, production légère |
| `local-industriel` | Local industriel | Production, usine, industrie lourde |
| `terrain` | Terrain | Terrains nus, à bâtir, zones d'activité |
| `parking` | Parking | Places de stationnement, parkings |
| `hotel` | Hôtel | Établissements hôteliers |
| `restaurant` | Restaurant | Restaurants, brasseries |
| `immeuble` | Immeuble | Immeubles entiers |
| `appartement` | Appartement | Logements (rare en immobilier d'entreprise) |
| `maison` | Maison | Maisons (rare en immobilier d'entreprise) |
| `ecole` | École | Établissements d'enseignement |

---

## 3. Types de transactions

| Code | Label | Description |
|------|-------|-------------|
| `a-louer` | À louer | Location classique |
| `a-vendre` | À vendre | Vente |
| `sous-location` | Sous-location | Sous-location d'un bail existant |
| `investissement` | Investissement | Bien occupé vendu à un investisseur |
| `cession-de-fonds` | Cession de fonds | Vente d'un fonds de commerce |
| `a-louer-droit-entree` | Droit au bail | Cession du droit au bail |
| `cession-de-bail` | Cession de bail | Transfert du bail en cours |
| `vefa` | VEFA | Vente en état futur d'achèvement |
| `befa` | BEFA | Bail en état futur d'achèvement |
| `vente-possible` | Vente possible | Vente envisageable (pas le mode principal) |
| `location-possible` | Location possible | Location envisageable (pas le mode principal) |

**Note** : une offre peut avoir PLUSIEURS types de transaction simultanés (ex: `a-louer` + `a-vendre`).

---

## 4. Champs critiques par type de bien

### Bureaux
| Champ | Importance | Description |
|-------|-----------|-------------|
| Surface (m²) | Obligatoire | Surface utile du lot |
| Étage | Important | Niveau dans l'immeuble |
| Nombre de parkings | Important | Places incluses ou optionnelles |
| DPE | Obligatoire | Diagnostic de performance énergétique |
| Configuration | Important | Open-space, cloisonné, mixte |
| Accessibilité PMR | Important | Conformité personnes à mobilité réduite |
| État général | Important | neuf, bon_etat, a_rafraichir, a_renover, gros_travaux |

### Commerce
| Champ | Importance | Description |
|-------|-----------|-------------|
| Linéaire vitrine (ml) | Critique | Mètres linéaires de façade vitrée |
| Type ERP | Important | Classification sécurité incendie |
| Catégorie ERP | Important | 1 à 5 selon capacité d'accueil |
| Extraction | Critique | Présence d'extraction pour restauration |
| Enseigne autorisée | Important | Possibilité de poser une enseigne |
| Visibilité | Important | Artère principale, flux piéton |

### Entrepôt / Activité
| Champ | Importance | Description |
|-------|-----------|-------------|
| HSP (m) | Critique | Hauteur sous plafond / sous ferme |
| Charge au sol (kg/m²) | Critique | Capacité portance |
| Quais de chargement | Important | Nombre et type (niveleur, hayon) |
| Portes sectionnelles | Important | Nombre et dimensions |
| Accès poids lourds | Critique | Aire de manœuvre PL/semi |
| Sprinklers | Important | Système anti-incendie |

### Terrain
| Champ | Importance | Description |
|-------|-----------|-------------|
| Surface parcelle (m²) | Obligatoire | Surface totale du terrain |
| PLU / Zonage | Critique | Zone urbanisme (UE, AU, etc.) |
| Viabilisation | Critique | Eau, électricité, assainissement, télécom |
| COS / CES | Important | Coefficients d'occupation/emprise |

---

## 5. Conditions financières

### Location
| Champ | Description | Unité |
|-------|-------------|-------|
| Loyer facial | Loyer annoncé | €/m²/an HT HC |
| Loyer économique | Loyer réel (après franchise) | €/m²/an |
| Charges | Provisions ou forfait | €/m²/an ou €/an |
| Type de charges | Provision avec régularisation ou forfait | — |
| Payeur charges | Bailleur ou preneur | — |
| Taxe foncière | Montant annuel | €/an |
| Dépôt de garantie | Mois de loyer ou montant fixe | Mois ou € |
| Indice de révision | ILAT, ICC, ou ILC | — |
| Type de bail | 3/6/9, professionnel, dérogatoire, mixte | — |
| Durée ferme | Période incompressible | Années |
| Franchise | Période de gratuité | Mois |

### Vente
| Champ | Description | Unité |
|-------|-------------|-------|
| Prix de vente | Prix net vendeur | € |
| Honoraires | Commission Arthur Loyd | % du prix ou montant fixe |
| Payeur honoraires | Vendeur ou acquéreur | — |
| Frais de notaire | Estimation | % ou € |
| Régime fiscal | TVA sur le prix, droits d'enregistrement | — |

### Investissement
| Champ | Description | Unité |
|-------|-------------|-------|
| Prix de vente | Prix de cession | € |
| Rendement | Taux de capitalisation | % |
| Loyers perçus | Revenus locatifs annuels | €/an |
| WALB | Durée moyenne pondérée des baux | Années |
| Occupation | Taux d'occupation physique/financier | % |

---

## 6. Mandats

### Types de mandat
| Type | Code | Exclusivité | Description |
|------|------|-------------|-------------|
| Simple | `simple` | Non | Le propriétaire peut confier à plusieurs agents |
| Préférentiel | `preferentiel` | Partielle | Agent privilégié, propriétaire peut vendre seul |
| Exclusif | `exclusif` | Oui | Seul Arthur Loyd peut commercialiser |
| Co-préférentiel | `co-preferentiel` | Partielle | Plusieurs agents préférentiels |
| Co-exclusif | `co-exclusif` | Oui | Exclusivité partagée entre agents désignés |

### Champs du mandat
- **Date d'effet** : début du mandat
- **Date de renouvellement** : tacite reconduction
- **Préavis** : délai pour résiliation (généralement 3 mois)
- **Conditions de résiliation** : clause spécifique
- **Honoraires** : % ou montant, payeur (vendeur/acquéreur/bailleur/preneur)

---

## 7. Services et prestations (17 booléens)

Chaque lot peut indiquer la présence ou non de ces services. Système à 3 états :
- **0** = non spécifié
- **1** = disponible
- **2** = mis en avant (featured)

| Service | Code | Pertinence principale |
|---------|------|----------------------|
| Accessibilité PMR | `pmr` | Tous types |
| Parking | `parking` | Tous types |
| ERP | `erp` | Commerce |
| RDC | `rdc` | Commerce, activité |
| Visibilité | `visibility` | Commerce |
| Enseigne | `signage` | Commerce |
| Transports en commun | `publicTransport` | Bureaux, commerce |
| Fibre optique | `fiber` | Bureaux |
| Climatisation | `airConditioning` | Bureaux |
| Ascenseur | `elevator` | Bureaux, immeuble |
| Gardien | `security` | Bureaux, immeuble |
| Vidéosurveillance | `cctv` | Entrepôt, activité |
| Espace vert | `garden` | Tous types |
| Borne électrique | `evCharging` | Bureaux, commerce |
| Local vélo | `bikeStorage` | Bureaux |
| Douche | `shower` | Bureaux, activité |
| Coworking | `coworking` | Bureaux |

---

## 8. Diagnostics

### Diagnostics énergétiques
| Diagnostic | Champs | Valeurs |
|-----------|--------|---------|
| DPE | Valeur (kWh/m²/an), Lettre (A-G), Date, Statut | Obligatoire pour toute annonce |
| GES | Valeur (kgCO2/m²/an), Lettre (A-G), Date, Statut | Accompagne le DPE |

### Diagnostics réglementaires
| Diagnostic | Obligatoire si | Statut possible |
|-----------|----------------|-----------------|
| Amiante | Permis de construire avant 01/07/1997 | completed, pending, notRequired |
| Plomb | Bâtiment avant 01/01/1949 | completed, pending, notRequired |
| Termites | Zone à risque (arrêté préfectoral) | completed, pending, notRequired |
| Gaz | Installation gaz > 15 ans | completed, pending, notRequired |
| Électricité | Installation électrique > 15 ans | completed, pending, notRequired |
| Loi Carrez | Copropriété | completed, pending, notRequired |
| Assainissement | Assainissement non collectif | completed, pending, notRequired |

### Certifications environnementales
| Certification | Description |
|--------------|-------------|
| BREEAM | Certification britannique, niveaux Pass à Outstanding |
| HQE | Haute Qualité Environnementale (France) |
| WELL | Bien-être des occupants |
| BiodiverCity | Biodiversité urbaine |

---

## 9. État général du bien

| Code | Label | Description |
|------|-------|-------------|
| `neuf` | Neuf | Construction neuve ou rénovation complète |
| `bon_etat` | Bon état | Entretenu, prêt à occuper |
| `a_rafraichir` | À rafraîchir | Travaux légers (peinture, sols) |
| `a_renover` | À rénover | Travaux moyens (cloisonnement, électricité) |
| `gros_travaux` | Gros travaux | Réhabilitation lourde |

---

## 10. Photos

### Upload via MCP
```
upload_offer_photo → avec offerId et le fichier image
```

### Catégories de médias
| Catégorie | Code | Contenu |
|-----------|------|---------|
| Photo principale | `main` | Façade ou vue représentative |
| Plans | `plans` | Plans d'architecte, plans de masse |
| Documents | `documents` | Diagnostics, annexes |
| Extérieur | `exterior` | Façades, parking, environnement |
| Intérieur | `interior` | Bureaux, commerce, pièces |
| Plan de situation | `site_plan` | Carte de localisation |
| Divers | `misc` | Autres visuels |

### Bonnes pratiques photos Arthur Loyd
- Photo principale : vue dégagée de la façade, bien éclairée
- Minimum 5 photos pour une offre complète
- Plans : inclure plan de masse + plans par niveau si disponibles
- Pas de photos floues, sombres ou en contre-jour
- Respecter la charte graphique pour les visuels marketing (voir `al-charte-graphique.md`)

---

## 11. Groupement de lots

### Concept
Plusieurs lots à la même adresse peuvent être groupés :
- **together_only** : les lots doivent être loués/vendus ensemble
- **together_or_separate** : les lots peuvent être pris ensemble ou séparément

### Quand grouper
- Immeuble avec plusieurs plateaux de bureaux
- Centre commercial avec plusieurs cellules
- Zone d'activité avec plusieurs bâtiments

### MCP
```
add_lot_to_offer → ajouter un lot à une offre existante
remove_lot_from_offer → retirer un lot
update_lot → modifier les caractéristiques d'un lot
```

---

## 12. Statuts d'une offre

| Statut | Description |
|--------|-------------|
| `draft` | Brouillon, en cours de saisie |
| `active` | En commercialisation |
| `under_offer` | Offre reçue, en négociation |
| `let_agreed` | Accord de location trouvé |
| `sold` | Vendu |
| `withdrawn` | Retiré du marché |
| `archived` | Archivé |

### Archiver une offre
```
archive_offer → retire l'offre de la commercialisation active
```

---

## 13. Origines d'une offre

| Code | Label | Description |
|------|-------|-------------|
| `appel-entrant` | Appel entrant | Propriétaire contacte Arthur Loyd |
| `prospection` | Prospection | Démarchage actif par le consultant |
| `recommandation` | Recommandation | Bouche à oreille, réseau |
| `site-web` | Site web | Via le site Arthur Loyd |
| `reseau` | Réseau | Via le réseau national Arthur Loyd |
| `autre` | Autre | Autre canal d'entrée |

---

## 14. Historique des locataires

Chaque lot peut enregistrer l'historique des occupants :

### Locataire actuel
- **Nom** du preneur (personne physique ou morale)
- **Contact** : téléphone, email
- **Date d'entrée** dans les locaux
- **Type de bail** en cours
- **Loyer actuel**
- **Échéance du bail**

### Locataires précédents
- Historique des occupants successifs
- Dates d'entrée et de sortie
- Motif de départ (fin de bail, résiliation anticipée, déménagement)

Cette information est utile pour :
- Estimer la stabilité locative d'un bien (investissement)
- Comprendre la rotation des preneurs
- Identifier des besoins récurrents sur une adresse

---

## 15. Données PLU (Plan Local d'Urbanisme)

Le système peut stocker les données d'urbanisme liées à une offre :

### Zones
- **Code zone** : UE, AU, N, A, etc.
- **Libellé** : zone urbaine économique, zone à urbaniser, etc.
- **Règlement** : hauteur max, emprise au sol, recul

### Prescriptions
- Servitudes d'utilité publique
- Zones de protection (monuments historiques, AVAP)
- Risques naturels/technologiques (PPRI, Seveso)

### Cadastre
- Références cadastrales (section, numéro de parcelle)
- Surface cadastrale
- Contenance

### Secteurs commerciaux
- ZACOM (Zone d'Aménagement Commercial)
- Périmètre de protection du commerce de centre-ville
- ORT (Opération de Revitalisation de Territoire)

---

## 16. Conseils pratiques — Création d'offre

### Checklist avant activation
- [ ] Adresse complète et correcte
- [ ] Type de bien cohérent
- [ ] Au moins 1 lot avec surface renseignée
- [ ] Conditions financières remplies (loyer ou prix)
- [ ] DPE renseigné (obligatoire pour toute annonce)
- [ ] Au moins 3 photos (dont 1 photo principale façade)
- [ ] Mandat signé et renseigné
- [ ] Contact propriétaire associé

### Erreurs fréquentes à éviter
1. **Oublier le DPE** : obligatoire depuis 2011 pour toute annonce immobilière
2. **Loyer sans précision HT/TTC** : toujours préciser le régime fiscal
3. **Surface sans précision** : surface utile, SHON, surface Carrez ?
4. **Pas de photo principale** : le bien ne s'affiche pas correctement sur les portails
5. **Mandat expiré** : vérifier la date de validité avant de publier
6. **Doublon d'adresse** : toujours vérifier avec `search_offers` avant de créer
