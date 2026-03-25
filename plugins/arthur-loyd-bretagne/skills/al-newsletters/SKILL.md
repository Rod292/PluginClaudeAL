---
name: al-newsletters
description: "Création de newsletters immobilières : charte graphique MJML, blocs réutilisables, structure type, couleurs et polices obligatoires. À utiliser pour create_newsletter_from_offer, set_newsletter_content, ou toute génération de MJML newsletter."
---

# Newsletters MJML — Guide Arthur Loyd Bretagne

## Rôle de ce document

Ce document contient les règles visuelles obligatoires pour la création de newsletters via les outils MCP ImmoLabs. Ces règles sont basées sur l'analyse des newsletters réellement envoyées (pas la charte corporate générale). Consulte-le SYSTÉMATIQUEMENT avant de créer ou modifier du contenu MJML newsletter.

> **Important** : La charte corporate Arthur Loyd (Sen, Century Gothic, pas de noir #000000) s'applique aux supports print et branding. Les newsletters email utilisent une charte adaptée décrite ci-dessous, optimisée pour le rendu email.

---

## 1. Constantes de style

### Couleurs

| Rôle | Hex | Détail |
|------|-----|--------|
| **Header** | `#373a41` | Fond du header — gris foncé, PAS rouge |
| **Titres** | `#cc2e31` | Rouge foncé pour tous les titres et sous-titres |
| **Texte body** | `#000000` | Noir pour le contenu des descriptions |
| **Texte secondaire** | `#334155` | Adresses, métadonnées |
| **Lien email** | `#5BC8F4` | Liens cliquables (email du conseiller) |
| **Footer** | `#444153` | Fond du footer |
| **Unsubscribe** | `#52525b` | Bouton désabonnement |
| **Body background** | `#f4f4f4` | Fond global de l'email |
| **Contenu** | `#ffffff` | Fond des sections de contenu |
| **Divider** | `#F2F2F2` | Séparateurs |

### Couleurs par type de bien (accent lots uniquement)

| Type | Hex |
|------|-----|
| Bureaux | `#5BC8F4` |
| Commerces | `#F1A663` |
| Logistique | `#11B2BB` |
| Activité | `#5BD6AA` |
| Terrain | `#8BC34A` |

### Typographie

**Police : Inter** — toujours.

```
Inter, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif
```

| Niveau | Taille | Poids | Couleur |
|--------|--------|-------|---------|
| Titre principal | 22px | 700 | `#cc2e31` |
| Sous-titre | 18px | 600 | `#cc2e31` |
| Body text | 15px | 400 | `#000000` |
| Texte secondaire | 13-14px | 400-600 | `#334155` |
| Footer | 11-12px | 400-500 | `#a1a1aa` |

### Règles de texte

- **Alignement body** : `align="justify"` — toujours
- **Line-height body** : `1.6`
- **Images** : toujours `border-radius="8px"` (sauf logos)

---

## 2. Structure type d'une newsletter

### Newsletter single offer

```
1. Header (#373a41) : logo 30% + nom org 70% + sous-titre + adresse
2. Titre offre (#cc2e31, 22px)
3. Image principale (border-radius 8px)
4. Description (noir, justify, 15px)
5. Sous-titre "Caractéristiques" + infos clés en liste texte
6. [Optionnel] Grille photos 2 colonnes
7. [Optionnel] Section lots si multi-lots
8. CTA texte simple : "Ce bien vous intéresse ?" (#cc2e31, centré)
9. Carte contact conseiller (35%/65%)
10. Footer (#444153) : logo footer + copyright + unsubscribe
```

### Newsletter multi-offres

```
1. Header (identique)
2. Introduction (texte justify)
3. Pour chaque offre :
   - Titre (#cc2e31, 20px)
   - Métadonnées (ville — surface — prix)
   - Image (border-radius 8px)
   - Description courte (200 chars, justify)
   - Séparateur (sauf dernière)
4. CTA texte simple
5. Carte contact conseiller
6. Footer (identique)
```

---

## 3. Blocs MJML réutilisables

### mj-head (obligatoire dans tout MJML)

```xml
<mj-head>
  <mj-font name="Inter" href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap" />
  <mj-attributes>
    <mj-all font-family="Inter, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif" />
    <mj-text font-size="15px" color="#000000" line-height="1.6" />
  </mj-attributes>
</mj-head>
```

### Header

```xml
<mj-section background-color="#373a41" padding="32px 24px">
  <mj-column width="30%">
    <mj-image src="{{orgLogo}}" alt="{{orgName}}" width="80px" align="left" />
  </mj-column>
  <mj-column width="70%" vertical-align="middle">
    <mj-text font-size="28px" font-weight="700" color="#ffffff" line-height="1.2" align="left">
      {{orgName}}
    </mj-text>
    <mj-text font-size="13px" font-weight="600" color="#ffffff" text-transform="uppercase" letter-spacing="1.5px" align="left" padding-top="4px">
      Conseil en immobilier d'entreprise
    </mj-text>
    <mj-text font-size="12px" color="rgba(255,255,255,0.7)" align="left" padding-top="4px">
      {{orgAddress}}
    </mj-text>
  </mj-column>
</mj-section>
```

### Titre principal

```xml
<mj-text font-size="22px" font-weight="700" color="#cc2e31" line-height="1.3">
  Titre ici
</mj-text>
```

### Sous-titre

```xml
<mj-text font-size="18px" font-weight="600" color="#cc2e31" padding-bottom="8px">
  Sous-titre ici
</mj-text>
```

### Texte body

```xml
<mj-text font-size="15px" color="#000000" line-height="1.6" align="justify">
  Contenu texte ici
</mj-text>
```

### Image

```xml
<mj-image src="URL" alt="description" fluid-on-mobile="true" border-radius="8px" />
```

### CTA texte

```xml
<mj-section background-color="#ffffff" padding="24px 24px 32px">
  <mj-column>
    <mj-text font-size="18px" font-weight="600" color="#cc2e31" align="center">
      Ce bien vous intéresse ?
    </mj-text>
    <mj-text font-size="15px" color="#000000" align="center" padding-top="8px">
      Contactez-nous pour organiser une visite ou obtenir plus d'informations.
    </mj-text>
  </mj-column>
</mj-section>
```

### Carte contact conseiller

```xml
<mj-section background-color="#ffffff" padding="0 32px 40px">
  <mj-column width="35%" vertical-align="top">
    <mj-image src="{{userPhoto}}" alt="{{userName}}" border-radius="8px" width="140px" />
  </mj-column>
  <mj-column width="65%" vertical-align="top" padding-left="20px">
    <mj-text font-size="22px" font-weight="700" color="#0f172a" line-height="1.2">
      {{userName}}
    </mj-text>
    <mj-text font-size="13px" font-weight="600" color="#64748b" text-transform="uppercase" letter-spacing="1px" padding-top="4px">
      Conseiller Immobilier d'Entreprise
    </mj-text>
    <mj-divider border-width="1px" border-color="#F2F2F2" padding="16px 0 12px" />
    <mj-text font-size="14px" color="#475569" line-height="1.8">
      📞 <strong>{{userPhone}}</strong><br/>
      ✉️ <a href="mailto:{{userEmail}}" style="color: #5BC8F4; text-decoration: none;">{{userEmail}}</a>
    </mj-text>
  </mj-column>
</mj-section>
```

### Footer

```xml
<mj-section background-color="#444153" padding="40px 32px 20px">
  <mj-column>
    <mj-image src="{{orgFooterLogo}}" alt="{{orgName}}" width="450px" align="center" padding-bottom="28px" />
    <mj-divider border-width="1px" border-color="#52525b" padding="0 60px 20px" />
    <mj-text font-size="12px" color="#a1a1aa" align="center" padding-bottom="8px">
      © 2026 {{orgName}}. Tous droits réservés.
    </mj-text>
    <mj-text font-size="11px" color="#71717a" align="center" padding-top="12px" padding-bottom="4px">
      Vous recevez cet email car vous êtes dans notre base de prospects.
    </mj-text>
    <mj-button href="{{unsubscribeUrl}}" background-color="#52525b" color="#ffffff" border-radius="6px" font-size="12px" font-weight="500" inner-padding="10px 24px" align="center">
      Se désabonner
    </mj-button>
  </mj-column>
</mj-section>
```

### Séparateur

```xml
<mj-divider border-width="1px" border-color="#F2F2F2" padding="0" />
```

---

## 4. Placeholders disponibles

| Placeholder | Description |
|-------------|-------------|
| `{{orgName}}` | Nom de l'organisation |
| `{{orgEmail}}` | Email de l'organisation |
| `{{orgLogo}}` | URL du logo header |
| `{{orgFooterLogo}}` | URL du logo footer (blanc) |
| `{{orgWebsite}}` | Site web |
| `{{orgLinkedin}}` | URL LinkedIn |
| `{{orgInstagram}}` | URL Instagram |
| `{{orgAddress}}` | Adresse de l'organisation |
| `{{userName}}` | Nom du conseiller |
| `{{userEmail}}` | Email du conseiller |
| `{{userPhone}}` | Téléphone du conseiller |
| `{{userPhoto}}` | URL photo du conseiller |
| `{{unsubscribeUrl}}` | URL de désabonnement (remplacé à l'envoi) |

---

## 5. Interdits absolus

| Interdit | Correct |
|----------|---------|
| Header rouge (`#CC2E31` ou `#E40521`) | Header gris `#373a41` |
| Police Sen ou Century Gothic | Police Inter |
| `css-class="title-font"` | Pas de css-class |
| Titres gris `#444153` | Titres rouge `#cc2e31` |
| Texte body gris | Texte body noir `#000000` |
| Texte body aligné à gauche | Texte body justify |
| Badges colorés par type de bien | Pas de badges |
| Section métriques 50/50 | Infos en liste texte |
| CTA sombre avec bouton rouge | CTA texte simple centré |
| `mj-social` dans le footer | Pas d'icônes sociales |
| Images sans border-radius | `border-radius="8px"` |

---

## 6. Workflow MCP

### `create_newsletter_from_offer`
Les templates sont hardcodés et déjà alignés. Les variables sont résolues automatiquement à la création. Rien de spécial à faire.

### `set_newsletter_content` (MJML custom)
**Obligatoire** : assembler le MJML en utilisant les blocs ci-dessus. Ne pas inventer de nouveaux styles.

**Variables template** : Tu PEUX et DOIS utiliser les placeholders `{{orgName}}`, `{{userName}}`, `{{userPhoto}}`, etc. dans ton MJML custom. Ils seront automatiquement résolus avec les vraies valeurs de l'organisation et du conseiller au moment de l'envoi (test ou production). Seul `{{unsubscribeUrl}}` est résolu per-destinataire.

### Images externes
Les images hébergées sur des domaines externes (Wikimedia, Unsplash, etc.) peuvent ne pas s'afficher dans l'éditeur GrapeJS à cause des restrictions CORS.

**Solution** : utiliser le proxy image ImmoLabs pour les URLs externes :
```
/api/newsletters/proxy-image?url={url encodée}
```

Exemple dans le MJML :
```xml
<mj-image src="https://app.immo-labs.com/api/newsletters/proxy-image?url=https%3A%2F%2Fupload.wikimedia.org%2Fwikipedia%2Fcommons%2F4%2F4a%2FBrest_tram_Rue_de_Siam.JPG" border-radius="8px" />
```

**Préférer** les images uploadées via l'éditeur (stockées Firebase) qui n'ont pas ce problème.

### Personnalisation
L'utilisateur peut ensuite modifier la newsletter dans l'éditeur GrapeJS. Le MJML généré sert de base conforme à la charte.
