<div align="center">

```
██╗     ███████╗███████╗    ██╗  ██╗███████╗██████╗  ██████╗ ███████╗
██║     ██╔════╝██╔════╝    ██║  ██║██╔════╝██╔══██╗██╔═══██╗██╔════╝
██║     █████╗  ███████╗    ███████║█████╗  ██████╔╝██║   ██║███████╗
██║     ██╔══╝  ╚════██║    ██╔══██║██╔══╝  ██╔══██╗██║   ██║╚════██║
███████╗███████╗███████║    ██║  ██║███████╗██║  ██║╚██████╔╝███████║
╚══════╝╚══════╝╚══════╝    ╚═╝  ╚═╝╚══════╝╚═╝  ╚═╝ ╚═════╝ ╚══════╝
                                                         DE L'OMBRE
```

**Site vitrine — Chaîne YouTube dédiée aux personnages secondaires du cinéma**

[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)](https://developer.mozilla.org/fr/docs/Web/HTML)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS_v3-38B2AC?style=flat-square&logo=tailwind-css&logoColor=white)](https://tailwindcss.com)
[![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-F7DF1E?style=flat-square&logo=javascript&logoColor=black)](https://developer.mozilla.org/fr/docs/Web/JavaScript)
[![YouTube](https://img.shields.io/badge/YouTube-@LesHérosDelOmbre-FF0000?style=flat-square&logo=youtube&logoColor=white)](https://www.youtube.com/@LesH%C3%A9rosDelOmbre)
[![Licence](https://img.shields.io/badge/Licence-Tous_droits_réservés-8B2010?style=flat-square)](./mentions-legales.html)

</div>

---

## ✦ Sommaire

- [Aperçu](#-aperçu)
- [Structure des fichiers](#-structure-des-fichiers)
- [Stack technique](#-stack-technique)
- [Design system](#-design-system)
- [Pages et contenu](#-pages-et-contenu)
- [JavaScript & Interactivité](#-javascript--interactivité)
- [Responsive](#-responsive)
- [Sécurité](#-sécurité)
- [Accessibilité](#-accessibilité)
- [Personnaliser le contenu](#-personnaliser-le-contenu)
- [Déploiement](#-déploiement)
- [Checklist avant mise en ligne](#-checklist-avant-mise-en-ligne)
- [Historique des versions](#-historique-des-versions)

---

## 🎬 Aperçu

> *Ces personnages secondaires sans qui les grandes œuvres ne seraient rien.*

| Propriété | Valeur |
|---|---|
| 🎥 Chaîne | Les Héros de l'Ombre |
| 🔗 YouTube | [@LesHérosDelOmbre](https://www.youtube.com/@LesH%C3%A9rosDelOmbre) |
| 📧 Email | lesoublies8@gmail.com |
| 🎞️ Format vidéo | YouTube Shorts (~4 min) |
| 🌍 Langue | Français |
| 🖥️ Compatibilité | Chrome · Firefox · Safari · Edge — mobile & desktop |
| ⚡ Déploiement | 100 % statique — zéro backend, zéro build |

---

## 📁 Structure des fichiers

```
dossier youtube/
│
├── 📄 index.html              →  Page d'accueil (hero, chaîne, stats, vidéos…)
├── 📄 contact.html            →  Formulaire de contact
├── 📄 mentions-legales.html   →  Mentions légales (TOC sticky, 8 sections)
│
├── ⚡ app.js                  →  Tout le JS de la page d'accueil (defer)
├── 🖼️ logo.svg               →  Logo vectoriel 512×512 (cercle rouge + silhouette)
│
└── 📘 README.md               →  Ce fichier
```

> **Architecture CSS :** Chaque page embarque **Tailwind CSS v3 via CDN** + un bloc `<style>` minimal (~25 lignes) pour les seuls états JS-toggled et pseudo-éléments complexes. Zéro fichier `.css` séparé, zéro npm, zéro build step.

---

## ⚙️ Stack technique

| Technologie | Version | Rôle |
|---|---|---|
| **HTML5** | sémantique | Structure et accessibilité |
| **Tailwind CSS** | v3 (CDN) | Mise en page, design, responsive |
| **JavaScript** | ES6+ vanilla | Interactivité, animations, parallaxe |
| **Google Fonts** | — | Bebas Neue · Cormorant Garamond · Inter · Playfair Display |
| **SignPainter** | macOS system font | Police d'affichage principale (titres, logo) |
| **IntersectionObserver** | API native | Scroll reveal & animation des compteurs |
| **Web Share API** | API native | Bouton partager (fallback clipboard) |
| **Git** | — | Versionnement |

### Pourquoi Tailwind CDN ?

- ✅ **Zéro configuration** — pas de Node.js, pas de PostCSS, pas de build
- ✅ **JIT à la volée** — le CDN scanne les classes dans le HTML et génère uniquement le CSS nécessaire
- ✅ **Cohérence** — même config `tailwind.config` partagée sur les 3 pages
- ✅ **Maintenabilité** — les styles vivent avec les éléments, pas dans un fichier séparé

---

## 🎨 Design system

### Palette moodboard

Définie dans `tailwind.config` (clés préfixées `c-`) sur chaque page.

| Token Tailwind | Hex | Aperçu | Usage |
|---|---|---|---|
| `c-red` | `#8B2010` | 🟥 | Rouge brique — boutons, badges, accents |
| `c-rdk` | `#661508` | 🔴 | Rouge sombre — hover boutons |
| `c-gold` | `#D89634` | 🟡 | Or chaud — titres, bordures TOC, arrows |
| `c-glt` | `#e8a93f` | 💛 | Or clair — hover liens or |
| `c-blk` | `#241B14` | ⬛ | Brun-noir — texte principal |
| `c-drk` | `#1a1208` | ⬛ | Très sombre — hero, header pages |
| `c-dk2` | `#211610` | ⬛ | Sombre 2 — footer, Notre Concept |
| `c-gry` | `#8a7a6a` | 🔘 | Gris brun — texte secondaire |
| `c-glt2` | `#b5a898` | 🔘 | Gris clair — labels, métadonnées |
| `c-crm` | `#f5efe6` | 🟤 | Crème — fond citation, encadrés |
| `c-wht` | `#fdf8f2` | ⬜ | Blanc ivoire — fond général |
| `c-bdr` | `#3a2e24` | 🟫 | Brun bordure — séparateurs |

### Typographie

| Police | Classe Tailwind | Usage |
|---|---|---|
| **SignPainter** | `font-sign` | Titres principaux, logos, h1 des pages |
| **Bebas Neue** | `font-bebas` | Boutons, stats, numéros, nav TOC |
| **Cormorant Garamond** | `font-cormorant` | Citations, sous-titres éditoriaux, italiques |
| **Inter** | `font-sans` (default) | Corps de texte, labels, métadonnées |
| **Playfair Display** | `font-playfair` | Guillemet décoratif géant (citation index) |

### Tailles fluides

Toutes les tailles de texte et paddings utilisent `clamp()` pour un responsive sans cassure :

```html
<!-- Exemples de tailles fluides -->
text-[clamp(3.8rem,7vw,7rem)]    → Hero h1
text-[clamp(2.8rem,6vw,5rem)]    → Page headers
text-[clamp(1.4rem,3vw,2rem)]    → Citations
px-[clamp(1.5rem,5vw,4rem)]      → Padding sections
```

### Animations (CSS minimal block)

| Classe | Keyframes | Délai | Usage |
|---|---|---|---|
| `.anim-tag` | `fadeIn` | 0.5 s | Badge "Chaîne YouTube" hero |
| `.anim-h1` | `fadeUp` | 0.7 s | Titre principal hero |
| `.anim-sub` | `fadeUp` | 0.9 s | Sous-titre hero |
| `.anim-cta` | `fadeUp` | 1.1 s | Bouton CTA hero |
| `.anim-hint` | `fadeIn` | 1.6 s | Indicateur de scroll |
| `.hint-bounce` | `bounceHint` | 2.0 s | Flèche rebondissante |

**Scroll reveal** → classes `.reveal` + `.d1` à `.d4` (délais 0.12 s / 0.24 s / 0.36 s / 0.48 s)

---

## 📄 Pages et contenu

### `index.html` — Page d'accueil

<details>
<summary><strong>Voir le détail des 8 sections →</strong></summary>

#### 1. 🎬 Hero
- Image pleine hauteur avec effet **parallaxe** au scroll
- Nav overlay (burger + logo centré + icônes réseaux)
- Titre animé (`fadeUp`), sous-titre, CTA "Voir les vidéos"
- Indicateur de scroll rebondissant

```
Hauteur hero    : 540px  (→ 420px sur mobile ≤680px)
Image           : 150% de hauteur du hero = 810px
P_INIT          : -243px  (= -(540 × 0.45))
P_SPEED         : 0.45
Actif jusqu'à   : scrollY < 700px
Optimisation    : requestAnimationFrame + flag anti-doublon
```

#### 2. 🎭 La Chaîne (`#about`)
- En-tête : titre SignPainter, tags genre (Cinéma / Séries / Analyse), étoiles ★
- Boutons : "Partager" (Web Share API) + "Chaîne officielle" (lien YouTube)
- Bande méta : Format · Durée moy. · Abonnés · Depuis
- Grille 3 colonnes : **Affiche poster** | **Description + Read more** | **Miniature dernière vidéo**

#### 3. 📊 Statistiques
- 4 compteurs animés : Abonnés · Épisodes · Vues totales · Durée par épisode
- Easing cubique : `1 - (1-p)³` sur 1 500 ms
- Déclenchement par `IntersectionObserver` (se joue une seule fois)

#### 4. 💬 Citation
- Fond crème `c-crm`
- Guillemet géant `"` en Playfair Display, opacité 4 %
- Texte en Cormorant Garamond italique

#### 5. 🎯 Notre Concept (`#concept`)
- Fond sombre `c-dk2`
- 3 cartes : Le personnage ignoré · L'analyse narrative · La passion cinéphile
- Hover : élévation `-6px` + barre dégradée or→rouge animée en haut (CSS `::before` + `scaleX`)

#### 6. 🎞️ Les Vidéos (`#videos`)
- 3 cartes YouTube Shorts en **format portrait 9:16**
- Numéro épisode en filigrane + bouton play rouge au hover
- Barre rouge animée bas de carte au hover (`::after` + `scaleX`)
- Grille centrée `max-w-[820px]`

#### 7. 📢 CTA Abonnement
- Bande rouge pleine largeur
- Bouton blanc → YouTube

#### 8. 🔻 Footer
- 2 colonnes : Branding (logo + description + réseaux + email) | Navigation (flèches or au hover)
- Barre copyright sombre

</details>

---

### `contact.html` — Page de contact

<details>
<summary><strong>Voir le détail →</strong></summary>

| Section | Contenu |
|---|---|
| Nav sticky | Logo SignPainter + liens + burger mobile |
| Page header | Fond `c-drk`, titre "Nous Contacter" en SignPainter |
| Infos rapides | 3 blocs séparés : Email · YouTube · Délai de réponse |
| Formulaire | Prénom · Nom · Email · Téléphone (opt.) · Sujet · Message · RGPD |
| Citation | Style identique à index.html (simplifié) |
| Footer | Identique à index.html |

**Fonctionnement du formulaire :**

Utilise `mailto:` — le client mail s'ouvre avec les champs pré-remplis (destinataire, sujet formaté, corps). Aucun serveur, aucune API.

**Validations côté client :**
- Prénom + Nom requis
- Email valide (`@` détecté)
- Sujet obligatoire (select)
- Message ≥ 10 caractères
- Checkbox RGPD requise

En cas de succès → formulaire masqué + message de confirmation animé.

</details>

---

### `mentions-legales.html` — Mentions légales

<details>
<summary><strong>Voir le détail →</strong></summary>

- En-tête sombre avec flèche retour + titre SignPainter
- Mini bandeau rouge (date de mise à jour)
- **Grille 2 colonnes** : TOC sticky (sommaire 01→08) | Corps légal
- 8 sections : Éditeur · Hébergement · Propriété intellectuelle · Données personnelles · Cookies · Responsabilité · Droit applicable · Contact
- Citation bas de page
- Footer identique

**TOC :** Numéros hardcodés `01`–`08` en Bebas Neue or, liens avec scroll fluide.

</details>

---

## ⚡ JavaScript & Interactivité

Tout le JS de la page d'accueil est dans `app.js` (chargé avec `defer`).  
Le JS de `contact.html` et `mentions-legales.html` est inline dans les pages.

### Architecture `app.js`

```
app.js
├── showToast(msg)        → Toast notification temporaire (bas de page)
│
├── ── MENU BURGER ──
│   ├── openMenu()        → body.classList.add('menu-open') + focus
│   ├── closeMenu()       → body.classList.remove('menu-open')
│   └── Écouteurs         → burgerBtn · menuClose · overlay · liens · Escape
│
├── ── RECHERCHE ──
│   ├── openSearch()      → searchOverlay.classList.add('active')
│   ├── closeSearch()     → searchOverlay.classList.remove('active')
│   └── form submit       → youtube.com/results?search_query=…+Les héros de l ombre
│
├── ── PARTAGER ──
│   └── shareBtn click    → Web Share API (mobile) ou Clipboard API (desktop)
│
├── ── LIRE PLUS/MOINS ──
│   └── readMoreBtn       → toggle .expanded sur #infoText (max-height animation)
│
├── ── SCROLL ──
│   ├── Parallaxe         → heroImg.style.transform = translateY(P_INIT + scrollY × P_SPEED)
│   └── Retour en haut    → toggle .visible sur #backToTop (seuil : 260px)
│
├── ── SCROLL REVEAL ──
│   ├── IntersectionObserver (threshold: 0.1) → .reveal → .reveal.visible
│   └── Filet de sécurité → setTimeout 2 500 ms (en cas de scroll rapide)
│
└── ── COMPTEURS ──
    ├── animateCount(el)  → easing cubique sur 1 500 ms
    └── IntersectionObserver → déclenche une seule fois sur .stat-item
```

### Parallaxe — Maths

```
Hero height   : 540 px
Image height  : 150% = 810 px
P_INIT        : -(540 × 0.45) = -243 px

scrollY = 0   → translateY(-243px)  ✓ image couvre le hero avec marge
scrollY = 540 → translateY(+0px)    ✓ image au bord bas du hero
Vitesse 0.45  = +29% d'effet vs ancienne valeur (0.35)
```

---

## 📱 Responsive

### Breakpoints Tailwind (max-width)

| Breakpoint | Largeur | Changements principaux |
|---|---|---|
| Desktop | > 1024px | Layout 3 colonnes (poster + info + trailer) |
| Tablette+ | ≤ 1024px | Colonne trailer masquée, profile 2 colonnes |
| Tablette | ≤ 860px | Burger actif, grilles → 2 col, stats → 2×2, footer 1 col |
| Mobile | ≤ 680px | Hero → 420px, profile 1 col, poster masqué, nav simplifiée |
| Petit mobile | ≤ 580px | Formulaire 1 col, legal-card 1 col |
| Très petit | ≤ 400px | Vidéos 2 col réduit, typo réduite |

### Stratégie

- **Mobile first** via Tailwind (`max-[X]:`  pour dé-grader), `clamp()` pour la fluidité entre les breakpoints
- Sections pleine largeur (fonds colorés) → pas de `max-width` sur le wrapper
- Sections à fond blanc → `max-w-[1360px] mx-auto`
- Police fluide : `text-[clamp(3.8rem,7vw,7rem)]` → aucune rupture visuelle

---

## 🔒 Sécurité

Chaque page implémente 3 en-têtes de sécurité via `<meta http-equiv>` :

### Content Security Policy (CSP)

```
default-src 'none'
style-src   'unsafe-inline' fonts.googleapis.com cdn.tailwindcss.com
font-src    fonts.gstatic.com
img-src     'self' images.unsplash.com data: blob:
script-src  'self' 'unsafe-inline' cdn.tailwindcss.com
connect-src 'self' cdn.tailwindcss.com
frame-src   'none'
object-src  'none'
base-uri    'self'
form-action 'self' mailto:
```

> `'unsafe-inline'` est nécessaire pour Tailwind CDN (génération CSS à la volée).  
> Sur un vrai déploiement avec build Tailwind, remplacer par des hashes ou nonces.

### Autres en-têtes

| En-tête | Valeur | Protection |
|---|---|---|
| `Referrer-Policy` | `strict-origin-when-cross-origin` | Fuite d'URL |
| `Permissions-Policy` | `camera=() microphone=() geolocation=()` | APIs sensibles |

### Liens externes

Tous les `target="_blank"` incluent `rel="noopener noreferrer"` (clickjacking + fuite de référent).

---

## ♿ Accessibilité

| Fonctionnalité | Implémentation |
|---|---|
| **Skip link** | "Aller au contenu principal" → focus → fixé en haut |
| **ARIA labels** | `aria-label` sur tous les boutons, liens icônes, modales |
| **aria-expanded** | Burger button mis à jour à l'ouverture/fermeture |
| **aria-modal** | Sur les dialogues (menu mobile, overlay recherche) |
| **aria-live** | Sur le toast (`role="status"`) |
| **Focus visible** | `outline: 2px solid #8B2010` sur `:focus-visible` |
| **Reduced motion** | `@media (prefers-reduced-motion)` → désactive tout |
| **Formulaire** | Labels liés, `autocomplete`, champs typés |
| **Images** | `alt` descriptif · `aria-hidden="true"` sur les déco |
| **Liens externes** | `aria-label` avec "(nouvel onglet)" |
| **Sémantique HTML** | `<header>`, `<nav>`, `<main>`, `<section>`, `<footer>`, `<aside>` |

---

## ✏️ Personnaliser le contenu

### 🔗 Changer l'URL YouTube

Rechercher/remplacer dans les 3 fichiers HTML :
```
https://www.youtube.com/@LesH%C3%A9rosDelOmbre
```

### 📊 Modifier les statistiques

Dans `index.html`, section stats — changer `data-target` :

```html
<span data-target="1000">0</span>          <!-- Abonnés -->
<span data-target="4" data-suffix="+">0</span>  <!-- Épisodes -->
<span data-target="30000">0</span>         <!-- Vues totales -->
<span data-target="4" data-suffix="">0</span>   <!-- Minutes/épisode -->
```

### 🎞️ Ajouter une carte vidéo

Dans `index.html`, section `#videos`, dupliquer ce bloc :

```html
<a class="related-card reveal d1 block relative transition-transform duration-[400ms] hover:-translate-y-[6px]"
   href="https://www.youtube.com/@LesHérosDelOmbre/shorts"
   target="_blank" rel="noopener noreferrer"
   aria-label="Regarder « TITRE » sur YouTube Shorts">
    <div class="related-card-thumb [aspect-ratio:9/16] bg-[#1a1a1a] overflow-hidden">
        <img src="URL_MINIATURE" alt="TITRE — Short"
             class="w-full h-full object-cover transition duration-[550ms]">
        <div class="absolute inset-0 z-[2] bg-gradient-to-t from-black/[.92] ...">
            <span class="font-bebas text-[1.6rem] text-white/[.1] ... self-end">04</span>
            <div>
                <h3 class="font-bebas text-[1.05rem] ...">TITRE</h3>
                <span class="shorts-badge ...">Short · 2026</span>
            </div>
        </div>
        <div class="play-overlay absolute inset-0 z-[3] flex items-center justify-center pointer-events-none">
            <div class="play-circle-sm w-[50px] h-[50px] rounded-full bg-c-red ...">
                <svg viewBox="0 0 24 24" class="w-5 h-5 fill-white ml-[3px]"><path d="M8 5v14l11-7z"/></svg>
            </div>
        </div>
    </div>
</a>
```

Changer les classes `.d1` → `.d2` → `.d3` → `.d4` pour les délais d'animation.

### 🎨 Changer les couleurs

Dans le bloc `tailwind.config` de chaque fichier HTML :

```js
tailwind.config = {
  theme: {
    extend: {
      colors: {
        'c-red':  '#8B2010',   // ← Rouge principal
        'c-gold': '#D89634',   // ← Or accent
        'c-drk':  '#1a1208',   // ← Fond hero/headers
        // ...
      }
    }
  }
}
```

### 🔍 Modifier la recherche YouTube

Dans `app.js`, ligne ~67 :

```javascript
window.open(
    `https://www.youtube.com/results?search_query=${encodeURIComponent(q + ' Les héros de l ombre')}`,
    '_blank'
);
```

Changer la chaîne `' Les héros de l ombre'` par le nom de votre chaîne.

### 📧 Changer l'email de contact

Remplacer toutes les occurrences de `lesoublies8@gmail.com` dans `contact.html` et `mentions-legales.html`.

---

## 🚀 Déploiement

Le site est **100 % statique** : aucun backend, aucun build, aucune commande à lancer.

### Hébergement recommandé

| Hébergeur | Méthode | Domaine personnalisé |
|---|---|---|
| **GitHub Pages** | Push sur `main` → Settings → Pages | ✅ Gratuit |
| **Netlify** | Glisser-déposer le dossier sur netlify.com/drop | ✅ Gratuit |
| **Vercel** | `vercel deploy` depuis le dossier | ✅ Gratuit |
| **Cloudflare Pages** | Connecter le repo GitHub | ✅ Gratuit |

### Optimisation production (optionnel)

Pour passer de Tailwind CDN à un build optimisé :

```bash
# 1. Installer Tailwind CLI
npm install -D tailwindcss

# 2. Générer uniquement les classes utilisées
npx tailwindcss -i ./input.css -o ./output.css --minify

# 3. Remplacer le CDN par le fichier généré
# <link rel="stylesheet" href="output.css">
```

> Bénéfice : CSS final ~10 Ko au lieu du CDN complet (~3 Mo). Aussi, supprimer `'unsafe-inline'` de la CSP et le remplacer par un hash.

---

## ✅ Checklist avant mise en ligne

**Contenu**
- [ ] Remplacer les images Unsplash par les vraies miniatures YouTube
- [ ] Mettre à jour l'URL YouTube dans les 3 fichiers HTML
- [ ] Mettre à jour les chiffres des statistiques (abonnés, vues, épisodes)
- [ ] Vérifier l'adresse email dans `contact.html` et `mentions-legales.html`
- [ ] Compléter `mentions-legales.html` avec les vraies infos hébergeur

**Technique**
- [ ] Ajouter un `favicon.ico` / `favicon.svg` à la racine
- [ ] Vérifier les liens réseaux sociaux (Instagram, Twitter/X)
- [ ] Tester le formulaire de contact (ouverture du client mail)
- [ ] Tester le scroll parallaxe sur desktop et mobile
- [ ] Vérifier le menu mobile (burger → slide → fermeture Escape)

**Qualité**
- [ ] Tester sur iOS Safari + Chrome Android
- [ ] Tester avec la préférence "Réduire les animations" activée
- [ ] Vérifier la navigation clavier (Tab + Entrée + Escape)
- [ ] Passer les 3 pages dans [PageSpeed Insights](https://pagespeed.web.dev/)

---

## 📋 Historique des versions

| Version | Date | Description |
|---|---|---|
| `v1.0` | — | Structure initiale, mock macOS window |
| `v1.1` | — | Ajout icône Instagram dans la navigation |
| `v2.0` | — | Refonte complète : pleine page, suppression contour macOS |
| `v2.1` | — | Externalisation JS → `app.js`, correction section "Notre Concept" |
| `v2.2` | — | Suppression newsletter, refonte design professionnelle |
| `v2.3` | — | Page contact adaptée au nouveau design |
| `v2.4` | — | Vidéos : format Shorts 9:16, titre intégré dans la miniature |
| `v2.5` | — | Suppression bordures épaisses, full-width |
| `v2.6` | — | Intégration logo SVG, palette moodboard, police SignPainter |
| `v2.7` | — | Sécurité CSP · parallaxe renforcé (P_SPEED 0.45) · boutons retour uniformisés |
| **`v3.0`** | **Mai 2026** | **Migration complète vers Tailwind CSS v3 CDN — zéro fichier CSS séparé** |

---

<div align="center">

**✦ Les Héros de l'Ombre ✦**

*Ces personnages secondaires sans qui les grandes œuvres ne seraient rien.*

[![YouTube](https://img.shields.io/badge/S'abonner-FF0000?style=for-the-badge&logo=youtube&logoColor=white)](https://www.youtube.com/@LesH%C3%A9rosDelOmbre)

</div>
