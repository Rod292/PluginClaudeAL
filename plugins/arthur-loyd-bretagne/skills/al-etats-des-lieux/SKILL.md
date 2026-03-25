---
name: al-etats-des-lieux
description: "États des lieux immobilier commercial : workflow EDL entrée/sortie via MCP, pièces types, grille évaluation, compteurs, comparaison entrée/sortie."
---

# États des Lieux — Guide Complet Arthur Loyd Bretagne

## Rôle de ce document

Ce document décrit le workflow complet pour réaliser un état des lieux (EDL) d'entrée ou de sortie via les outils MCP ImmoLabs. Consulte-le dès qu'une question porte sur les EDL, les inspections de locaux, les pièces à évaluer, les photos d'inspection ou la comparaison entrée/sortie.

---

## 1. Workflow complet

### Étape 1 — Création de l'EDL
Utilise `create_etat_des_lieux` avec :
- **title** : ex. "EDL Entrée - Bureaux 15 rue de Siam, Brest"
- **address** : adresse complète du bien
- **type** : `entry` (entrée) ou `exit` (sortie)
- **date** : date prévue de l'inspection
- **consultant** : nom du consultant qui réalise l'EDL

### Étape 2 — Ajout des pièces (sur site)
Pour chaque pièce du local, utilise `add_piece` :
- Nom de la pièce (ex: "Bureau direction", "Open-space RDC")
- Type de pièce
- Évaluation de chaque élément (sols, murs, plafonds, etc.)

### Étape 3 — Photos
Utilise `upload_etat_des_lieux_photo` avec le paramètre **section** :
- `piece` : photo d'une pièce spécifique
- `elements` : photo d'un élément particulier (dégât, équipement)
- `compteur_eau` : relevé compteur eau
- `compteur_electricite` : relevé compteur électricité
- `compteur_gaz` : relevé compteur gaz
- `general` : vue d'ensemble, façade, parties communes

### Étape 4 — Vérification de complétude
Utilise `analyze_etat_des_lieux_completeness` pour obtenir :
- **Score de complétude** (%)
- **Liste des éléments manquants**
- **Recommandations** pour compléter l'EDL

### Étape 5 — Consultation et mise à jour
- `get_etat_des_lieux` : consulter un EDL existant
- `update_etat_des_lieux` : modifier/compléter des informations
- `get_etat_des_lieux_form_structure` : obtenir la structure du formulaire

---

## 2. Pièces types par catégorie de bien

### Bureaux
| Pièce | Éléments spécifiques à vérifier |
|-------|-------------------------------|
| Accueil / Réception | Comptoir, signalétique, interphone, contrôle accès |
| Open-space | Prises sol, réseau, éclairage, stores |
| Bureaux individuels | Serrures, stores, climatisation individuelle |
| Salle de réunion | Écran/vidéoprojecteur, câblage, acoustique |
| Cuisine / Coin café | Électroménager, plomberie, ventilation |
| Sanitaires | Robinetterie, évacuation, VMC, accessoires |
| Couloirs / Circulation | Éclairage de sécurité, extincteurs, signalétique |
| Local technique | Tableau électrique, TGBT, arrivées réseau |
| Archives / Stockage | Étagères, éclairage, ventilation |
| Parking | Marquage, éclairage, barrière, places numérotées |

### Commerce
| Pièce | Éléments spécifiques |
|-------|---------------------|
| Vitrine / Devanture | État vitrage, enseigne, store banne, éclairage |
| Espace de vente | Sols, éclairage, prises, sécurité incendie |
| Réserve | Accès, éclairage, ventilation, charge au sol |
| Bureau arrière | Standard bureau |
| Sanitaires | Conformité ERP, accessibilité PMR |
| Local technique | Extraction, climatisation, compteurs |

### Entrepôt / Activité
| Pièce | Éléments spécifiques |
|-------|---------------------|
| Zone de stockage | HSP, charge au sol, marquage, éclairage |
| Quais de chargement | État quais, niveleurs, portes sectionnelles |
| Bureaux associés | Standard bureau |
| Vestiaires | Casiers, douches, conformité |
| Sanitaires | Nombre conforme effectif, accessibilité |
| Local technique | Chaufferie, TGBT, sprinklers |
| Cour extérieure | Enrobé, clôture, portail, aire de manœuvre PL |

---

## 3. Grille d'évaluation par élément

Pour chaque pièce, évaluer systématiquement :

### Sols
- **Types** : carrelage, moquette, béton ciré/brut, parquet, linoléum, résine, dalle technique
- **Points de contrôle** : fissures, taches, usure, décollements, joints

### Murs
- **Types** : peinture, faïence, bardage, cloison amovible, vitré
- **Points de contrôle** : fissures, traces d'humidité, trous, salissures, état peinture

### Plafonds
- **Types** : dalles acoustiques, béton apparent, faux-plafond, plaques de plâtre
- **Points de contrôle** : taches, dalles manquantes/cassées, fissures, infiltrations

### Menuiseries
- **Fenêtres** : état châssis, vitrage, joints, mécanisme ouverture
- **Portes** : état vantaux, serrures, ferme-porte, seuils
- **Stores/Volets** : mécanisme, état lames, motorisation

### Électricité
- **Prises** : nombre, état, fonctionnement
- **Interrupteurs** : état, fonctionnement
- **Éclairage** : type (néon, LED, halogène), fonctionnement, nombre
- **Tableau électrique** : état, étiquetage, disjoncteurs

### Plomberie
- **Robinetterie** : état, fuites, pression
- **Évacuation** : écoulement, état siphons
- **Chauffe-eau/ballon** : marque, capacité, état

### Équipements
- **Climatisation** : marque, type, fonctionnement, filtres
- **Chauffage** : type, fonctionnement, thermostat
- **VMC** : fonctionnement, état bouches

### Échelle d'état
| État | Description | Code couleur |
|------|-------------|-------------|
| **Bon** | Neuf ou quasi-neuf, aucun défaut | Vert |
| **Correct** | Usure normale, conforme à l'usage | Bleu |
| **Usé** | Usure visible, fonctionnel | Orange |
| **Dégradé** | Dommages visibles, réparation nécessaire | Rouge |
| **Hors-service** | Non fonctionnel, remplacement requis | Rouge foncé |

---

## 4. Relevés obligatoires

### Compteurs
À chaque EDL, relever SYSTÉMATIQUEMENT :
- **Eau** : numéro compteur + index (m³)
- **Électricité** : numéro compteur + index (kWh), heures pleines/creuses si applicable
- **Gaz** : numéro compteur + index (m³)

Prendre une photo de chaque compteur avec l'index lisible.

### Clés
- Nombre de clés remises (entrée) ou rendues (sortie)
- Type : clé physique, badge, code, télécommande portail/parking
- Détailler par accès : porte principale, bureaux individuels, local technique, parking

### Détecteurs et sécurité
- Détecteurs de fumée : nombre, fonctionnement
- Extincteurs : nombre, date dernière vérification
- Issues de secours : état, signalétique
- Alarme : type, fonctionnement, code transmis

---

## 5. Photos — Bonnes pratiques

### Règles de prise de vue
1. **Vue d'ensemble** de chaque pièce (depuis l'entrée)
2. **Gros plan** de chaque défaut constaté, avec un objet de référence pour l'échelle (stylo, clé, mètre)
3. **Compteurs** : photo frontale, index lisible
4. **Menuiseries** : fenêtre ouverte et fermée si défaut constaté
5. **Équipements** : plaque signalétique visible (marque, modèle, puissance)

### Organisation des photos
- Nommer ou taguer chaque photo avec la pièce et l'élément concerné
- Utiliser les sections MCP : `piece`, `elements`, `compteur_eau`, `compteur_electricite`, `compteur_gaz`, `general`

---

## 6. Comparaison entrée / sortie

Quand un EDL de sortie est réalisé :

1. Récupérer l'EDL d'entrée via `get_etat_des_lieux` (chercher par adresse et type `entry`)
2. Comparer pièce par pièce :
   - État à l'entrée vs état actuel
   - Dégradations au-delà de l'usure normale (vétusté)
   - Équipements manquants ou endommagés
3. Distinguer :
   - **Usure normale** : pas de retenue → dégradation progressive liée au temps et à l'usage normal
   - **Dégradation locative** : retenue possible → dommage imputable au preneur
4. Vérifier les compteurs : consommation entre entrée et sortie

---

## 7. Spécificités immobilier commercial

### Obligations ERP (Établissement Recevant du Public)
Pour les commerces, vérifier :
- Type ERP (J, L, M, N, O, P, R, S, T, U, V, W, X, Y)
- Catégorie (1 à 5, selon capacité d'accueil)
- Conformité accessibilité PMR
- Issues de secours conformes
- Extincteurs et détection incendie

### Clauses de remise en état
Attention aux clauses du bail commercial :
- **Remise en état** : le preneur doit rendre les locaux dans l'état initial
- **État d'usage** : prise en compte de la vétusté
- **Grille de vétusté** : si annexée au bail, l'appliquer pour chiffrer les retenues

### Amiante
Pour les bâtiments construits avant le 1er juillet 1997 :
- Vérifier présence du DTA (Dossier Technique Amiante)
- Signaler tout matériau suspect (flocage, dalles de sol vinyle-amiante, faux-plafond)
- Ne PAS toucher ou prélever — signaler uniquement

---

## 8. Checklist récapitulative

Avant de finaliser un EDL, vérifier :

- [ ] Toutes les pièces ont été inspectées et ajoutées
- [ ] Chaque pièce a une évaluation (sols, murs, plafonds, menuiseries, électricité, plomberie, équipements)
- [ ] Les compteurs sont relevés avec photo (eau, électricité, gaz)
- [ ] Les clés sont comptées et listées
- [ ] Les défauts sont photographiés en gros plan
- [ ] Le score de complétude (`analyze_etat_des_lieux_completeness`) est > 80%
- [ ] Les deux parties (bailleur et preneur) sont identifiées
- [ ] La date et le type (entrée/sortie) sont corrects
- [ ] Pour un EDL sortie : la comparaison avec l'EDL entrée est documentée
