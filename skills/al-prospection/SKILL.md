---
name: al-prospection
description: "Prospection et commercialisation immobilière : plan de commercialisation, actions MCP, veille concurrentielle Bretagne, qualification prospects, rapports propriétaires, matching."
---

# Prospection & Commercialisation — Guide Arthur Loyd Bretagne

## Rôle de ce document

Ce document décrit les processus de commercialisation, de suivi des actions, de veille concurrentielle et de qualification des prospects pour Arthur Loyd Bretagne. Consulte-le dès qu'une question porte sur un plan de commercialisation, le suivi d'actions sur une offre, les concurrents, la qualification de prospects ou les rapports propriétaires.

---

## 1. Plan de commercialisation type

### Semaine 1 — Lancement

| Action | Type MCP | Priorité |
|--------|----------|----------|
| Pose panneau sur site | `signage_installation` | Haute |
| Publication site Arthur Loyd + portails | `website_portal_publication` | Haute |
| Reportage photo professionnel | `photos_videos` | Haute |
| Relance base interne (matching demandes) | `email_send` | Haute |
| Mise en page fiche commerciale | — | Moyenne |

### Semaines 2 à 4 — Diffusion

| Action | Type MCP | Fréquence |
|--------|----------|-----------|
| Newsletter ciblée par secteur | `newsletter_send` | 1 fois |
| Emails personnalisés aux prospects qualifiés | `email_send` | Continu |
| Publication LinkedIn (post locaux dispo) | `social_media_post` | 1-2 fois |
| Relances téléphoniques | `phone_call` | Bi-hebdo |
| Partage réseau Arthur Loyd national | `email_send` | 1 fois |

### En continu — Commercialisation active

| Action | Type MCP | Déclencheur |
|--------|----------|-------------|
| Visites de bien | `property_visit` | Demande prospect |
| Relances post-visite | `phone_call` / `email_send` | J+2 après visite |
| Réception d'offres | `price_offer_received` | Offre reçue |
| Négociation | `negotiation` | Offre à discuter |
| Contre-visite | `property_visit` | Intérêt confirmé |

### Mensuel — Reporting

| Action | Type MCP | Fréquence |
|--------|----------|-----------|
| Rapport propriétaire | `owner_report` | Mensuel (exclusif) / Trimestriel (simple) |
| Point marché / ajustement prix | `meeting_agency` | Si nécessaire |

---

## 2. Actions MCP — Référence complète

### Enregistrer une action
Utilise `log_offer_action` avec :
- **offerId** : identifiant de l'offre concernée
- **type** : type d'action (voir tableau ci-dessous)
- **description** : détail de l'action
- **date** : date de réalisation
- **outcome** : résultat (si connu)

### Compléter une action
Utilise `complete_offer_action` avec :
- **actionId** : identifiant de l'action
- **outcome** : `positive`, `negative`, ou `neutral`
- **notes** : commentaires de résultat

### Types d'actions par catégorie

#### Prospection (8 types)
| Type | Description | Icône |
|------|-------------|-------|
| `website_portal_publication` | Publication sur site web ou portails immobiliers | Globe |
| `newsletter_send` | Envoi de newsletter ciblée | Mail |
| `signage_installation` | Pose/dépose de panneau sur site | Sign |
| `social_media_post` | Publication sur réseaux sociaux (LinkedIn) | Share |
| `marketing_material` | Création de support marketing (fiche, plaquette) | FileText |
| `market_analysis` | Analyse de marché / étude comparative | BarChart |
| `cold_call` | Appel de prospection à froid | PhoneOutgoing |
| `canvassing` | Prospection terrain / porte-à-porte | MapPin |

#### Interaction client (8 types)
| Type | Description |
|------|-------------|
| `phone_call` | Appel téléphonique (entrant/sortant) |
| `email_send` | Envoi d'email personnalisé |
| `meeting_agency` | Réunion en agence |
| `property_visit` | Visite de bien sur site |
| `video_call` | Visioconférence |
| `negotiation` | Phase de négociation (prix, conditions) |
| `follow_up` | Relance / suivi post-contact |
| `price_offer_received` | Réception d'une offre de prix |

#### Technique (7 types)
| Type | Description |
|------|-------------|
| `photos_videos` | Reportage photo/vidéo du bien |
| `diagnostics` | Réalisation de diagnostics techniques |
| `floor_plan` | Réalisation/mise à jour de plans |
| `virtual_tour` | Création de visite virtuelle |
| `inventory_report` | État des lieux |
| `technical_inspection` | Inspection technique |
| `appraisal` | Estimation / avis de valeur |

#### Administratif (6 types)
| Type | Description |
|------|-------------|
| `owner_report` | Rapport d'activité au propriétaire |
| `mandate_signature` | Signature du mandat |
| `contract_drafting` | Rédaction de contrat / bail |
| `agreement_signature` | Signature d'accord / compromis |
| `legal_review` | Vérification juridique |
| `document_preparation` | Préparation de documents |

### Statuts d'action
- `PLANNED` : action programmée
- `IN_PROGRESS` : en cours
- `COMPLETED` : terminée
- `CANCELLED` : annulée

### Résultats (outcome)
- `positive` : résultat favorable (visite concluante, offre reçue, mandat signé)
- `negative` : résultat défavorable (refus, désistement, bien inadapté)
- `neutral` : sans conclusion (message laissé, document envoyé, en attente retour)

---

## 3. Veille concurrentielle

### Portails immobilier commercial
| Portail | Couverture | Intérêt |
|---------|------------|---------|
| BureauxLocaux.com | National | Référence bureaux/commerces, prix m² |
| Geolocaux.com | National | Annonces multi-types, alertes |
| SeLoger Pro | National | Large audience, données marché |
| LeBonCoin Pro | National | Volume d'annonces, tendances |

### Concurrents nationaux présents en Bretagne
| Cabinet | Forces | Zone Bretagne |
|---------|--------|--------------|
| CBRE | Études marché, grands comptes | Rennes, investissement |
| JLL | Conseil stratégique, workplace | Rennes |
| Cushman & Wakefield | Logistique, bureau prime | Rennes |
| BNP Paribas RE | Réseau agences, transaction | Rennes, Nantes |
| Nexity Entreprise | Promotion + conseil | Bretagne |

### Concurrents régionaux
| Cabinet | Forces | Zone |
|---------|--------|------|
| Giboire Entreprise | Leader historique Rennes, multi-produit | Rennes, Ille-et-Vilaine |
| Kermarrec Entreprise | Réseau local solide | Rennes, Bretagne Est |
| Advenis | Gestion + transaction | Bretagne |
| Samsic Immobilier | Adossé au groupe Samsic | Rennes |

### Points de veille
- **Prix au m²** par secteur géographique et type de bien
- **Taux de vacance** par zone (centre-ville, périphérie, ZA)
- **Nouvelles offres** mises en marché par les concurrents
- **Transactions** réalisées (montants, preneurs, surfaces)
- **Tendances** : coworking, flex office, logistique urbaine, retail park

---

## 4. Qualification des prospects

### Scoring — 4 critères
| Critère | Question clé | Points |
|---------|-------------|--------|
| Budget confirmé | Le prospect a-t-il validé son budget ? | /25 |
| Besoin identifié | Surface, type, localisation définis ? | /25 |
| Délai précis | Échéance connue (bail en cours, déménagement prévu) ? | /25 |
| Décideur identifié | Le contact est-il décisionnaire ? | /25 |

### Classification température
| Température | Délai estimé | Comportement type |
|-------------|-------------|-------------------|
| **Chaud** | < 1 mois | Visite planifiée, budget validé, urgence |
| **Tiède** | 1 à 3 mois | Recherche active, critères en cours d'affinage |
| **Froid** | > 3 mois | Veille, pas de projet immédiat |

### Actions par température

**Prospect chaud** (< 1 mois) :
- Organiser visite sous 48h → `property_visit`
- Présenter 2-3 biens correspondants
- Suivi téléphonique post-visite J+1 → `phone_call`
- Préparer offre / négociation → `negotiation`

**Prospect tiède** (1-3 mois) :
- Relance bi-hebdomadaire → `phone_call` / `email_send`
- Envoi de nouvelles offres correspondantes → `email_send`
- Invitation à visiter des biens similaires
- Suivi évolution des critères

**Prospect froid** (> 3 mois) :
- Inscription newsletter mensuelle → `newsletter_send`
- Envoi d'études marché / tendances → `email_send`
- Relance trimestrielle pour mise à jour projet → `phone_call`
- Entretien de la relation : vœux, invitation événements

---

## 5. Rapports propriétaires

### Fréquence
| Type de mandat | Fréquence rapport |
|----------------|-------------------|
| Exclusif / Co-exclusif | **Mensuel** |
| Préférentiel / Co-préférentiel | **Bimensuel** |
| Simple | **Trimestriel** |

### Contenu du rapport
1. **Synthèse des actions réalisées** : nombre d'appels, emails, visites, publications
2. **Contacts générés** : nombre de demandes reçues, profil des prospects
3. **Visites effectuées** : dates, retours des visiteurs
4. **Retours marché** : perception prix, concurrence, état du marché local
5. **Recommandations** : ajustement prix, travaux suggérés, changement de stratégie
6. **Prochaines actions** : planning des 30 prochains jours

### Créer un rapport via MCP
1. `list_offer_actions` avec l'offerId → récupérer toutes les actions de la période
2. Synthétiser les données par catégorie
3. `log_offer_action` type `owner_report` → enregistrer l'envoi du rapport

---

## 6. Matching offres/demandes

### Rechercher des correspondances
- `find_matches_for_offer` : trouver les demandes qui correspondent à une offre
- `find_matches_for_demand` : trouver les offres qui correspondent à une demande

### Critères de matching
Le système compare automatiquement :
- Type de bien (bureau, commerce, entrepôt, etc.)
- Surface (min/max de la demande vs surface de l'offre)
- Localisation (ville, secteur géographique)
- Budget (loyer ou prix vs fourchette de la demande)
- Transaction (location, vente, etc.)

### Exploitation des résultats
1. Examiner les matchs par score (les plus élevés d'abord)
2. Contacter les prospects correspondants → `email_send` ou `phone_call`
3. Proposer des visites pour les matchs > 70%
4. Documenter chaque contact dans les actions de l'offre

---

## 7. Marché immobilier commercial — Bretagne Ouest

### Zones géographiques clés

#### Brest Métropole
| Secteur | Types dominants | Tendances |
|---------|----------------|-----------|
| Centre-ville / Siam | Commerces, bureaux | Vacance commerciale en amélioration, bureaux rare |
| Quartier de l'Europe | Bureaux | Forte demande, taux de vacance bas |
| Guipavas / Gouesnou | Activité, logistique | Zones dynamiques, accès rocade |
| Kergaradec | Activité, entrepôt | Zone historique, renouvellement en cours |
| Port de commerce | Bureaux, mixte | Développement tertiaire récent |

#### Quimper
| Secteur | Types dominants |
|---------|----------------|
| Centre-ville | Commerces |
| Zone de Créac'h Gwen | Activité, commerce périphérique |
| Ergué-Gabéric | Logistique, activité |

#### Lorient / Vannes
| Secteur | Types dominants |
|---------|----------------|
| Lorient centre | Bureaux, commerces |
| Caudan / Lanester | Activité, logistique |
| Vannes centre | Bureaux, commerces |
| Séné / Theix | Activité, logistique |

### Indices de révision des loyers
| Indice | Usage | Publication |
|--------|-------|-------------|
| **ILAT** | Bureaux et activités | Trimestriel (INSEE) |
| **ILC** | Commerces | Trimestriel (INSEE) |
| **ICC** | Construction (ancien, moins utilisé) | Trimestriel (INSEE) |

Les baux commerciaux (3/6/9) sont révisés à chaque anniversaire triennal selon l'indice choisi. L'indexation annuelle est la norme.

---

## 8. Bonnes pratiques de suivi

### Cadence de relance recommandée
| Contexte | Délai | Canal |
|----------|-------|-------|
| Post-visite (prospect intéressé) | J+1 | Téléphone |
| Post-visite (prospect hésitant) | J+2 à J+3 | Email + téléphone |
| Après envoi d'offre de prix | J+3 à J+5 | Téléphone |
| Prospect inactif depuis 2 semaines | J+14 | Email de relance |
| Prospect inactif depuis 1 mois | J+30 | Téléphone |

### KPIs à suivre par offre
| KPI | Cible | Source MCP |
|-----|-------|-----------|
| Nombre de contacts générés | > 5/mois (bureau), > 10/mois (commerce) | `list_offer_actions` filtre `phone_call` + `email_send` |
| Nombre de visites | > 2/mois | `list_offer_actions` filtre `property_visit` |
| Délai moyen de commercialisation | < 6 mois (bureau), < 9 mois (commerce) | `get_offer_stats` |
| Taux de conversion visite/offre | > 20% | Calcul sur actions |

### Signaux d'alerte
- **0 visite après 1 mois** : revoir le prix, la communication ou le ciblage
- **Visites sans offre après 3 mois** : bien perçu comme trop cher ou inadapté
- **Forte rotation de contacts sans suite** : problème de qualification en amont
- **Propriétaire qui ne répond plus** : risque de perte de mandat, agir vite
