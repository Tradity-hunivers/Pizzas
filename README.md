# Pinocchio Pizza — Site vitrine

Site vitrine one-page de la pizzeria **Pinocchio Pizza** (Dieupentale, 82170), conçu par Help AI Agency.

Fichier unique `index.html` autonome, CSS + JS inline, zéro dépendance runtime hormis Google Fonts et Google Maps.

---

## 📁 Structure

```
.
├── index.html                       # Site complet (HTML + CSS + JS)
├── robots.txt                       # SEO — indexation
├── sitemap.xml                      # SEO — plan du site
├── _redirects                       # Redirections Cloudflare Pages
├── README.md                        # Ce fichier
└── images/
    ├── pizza-signature-margherita.png  # Pizza hero (fournie)
    └── IMAGES-A-FOURNIR.md             # Brief photos à livrer
```

---

## 🚀 Déploiement

### Option A — Cloudflare Pages (recommandé)

1. Pousser ce dossier sur un dépôt GitHub (ou glisser-déposer via l'UI).
2. Dashboard Cloudflare → **Pages** → **Create a project**.
3. Pas de commande de build — site statique. Laisser le champ vide.
4. Dossier de sortie : `/` (racine).
5. Ajouter le domaine personnalisé `pinocchio-pizzas.fr` dans **Custom domains**.
6. Le fichier `_redirects` est pris en compte automatiquement.

### Option B — Netlify

Glisser-déposer le dossier entier sur [app.netlify.com/drop](https://app.netlify.com/drop). C'est tout.

### Option C — Test local

```bash
# Aucun build nécessaire. Ouvrir directement :
open index.html
# ou servir avec Python
python3 -m http.server 8000
```

---

## ✏️ Modifier le contenu

Tout le contenu client est **centralisé en haut de `index.html`**. Les points à éditer :

| Info | Où modifier dans `index.html` |
|---|---|
| Horaires | Section `<section id="visiter">` + JSON-LD `openingHoursSpecification` |
| Téléphone | Rechercher `05 63 31 64 51` (partout) |
| Adresse | Rechercher `13 b Rue du Général Larroque` |
| Menu (pizzas) | Section `<section id="carte">` — blocs `.menu-item` |
| Prix | Même section, attributs `data-price` |
| Histoire | Section `<section id="histoire">` |
| Photos | Remplacer fichiers dans `/images/` — garder les mêmes noms |

---

## 📊 Analytics — Activation GA4

Dans `index.html`, rechercher le commentaire `<!-- GA4: REMPLACER G-XXXXXXXXXX -->` et remplacer `G-XXXXXXXXXX` par l'ID Google Analytics 4 du client. Le script est déjà en place, il suffit d'ajouter l'ID.

Événements déjà trackés :
- `click_telephone` — clic sur le numéro
- `click_reservation` — clic sur CTA réservation
- `click_menu` — ouverture d'un onglet de carte
- `click_itineraire` — clic sur l'adresse / Maps

---

## 🖼️ Remplacer les images

Les images des sections autres que la hero sont servies depuis **Unsplash** (libre de droits). Pour passer en production avec de vraies photos :

1. Shooter les photos selon le brief dans [images/IMAGES-A-FOURNIR.md](images/IMAGES-A-FOURNIR.md).
2. Compresser (squoosh.app) — cible 150-200 KB par image.
3. Déposer dans `/images/` avec le nom exact de la liste.
4. Dans `index.html`, remplacer les URLs `https://images.unsplash.com/…` par les chemins locaux `./images/nom-fichier.jpg`.

---

## 🔎 SEO — Position 1 locale

- Meta title / description optimisés pour « pizza Dieupentale » et « pizzeria Tarn-et-Garonne »
- JSON-LD `Restaurant` complet (schema.org)
- `sitemap.xml` + `robots.txt` prêts
- À compléter après mise en ligne :
  - Google Business Profile (fiche Google Maps)
  - Inscription sur PagesJaunes, TheFork, Just Eat
  - Backlinks locaux (Office du Tourisme de Montauban)

---

## 📝 Crédits

Design & développement : **Help AI Agency** — [helpaiagency.com](mailto:contactpro@helpaiagency.com)
Photos signature : fournies par le client. Photos placeholders : Unsplash License.
