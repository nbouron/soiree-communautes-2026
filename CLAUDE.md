# Soirée des communautés rennaises 2026 — Site web

## Projet
Site statique écoresponsable pour la soirée des communautés tech rennaises, organisée par le BreizhCamp et accueillie par Epitech Rennes le 9 avril 2026.

## Stack technique
- HTML5 sémantique + CSS (un seul fichier `style.css`)
- Google Analytics GA4 (`G-0KXV4BWTBD`) — snippet async dans `<head>` de chaque page
- Images WebP optimisées
- Police système (Inter/system-ui, pas de Google Fonts CDN)
- Déploiement : Firebase Hosting (`bzhcamp-soiree-2026`)
- CI/CD : GitHub Actions (`.github/workflows/`) — deploy automatique sur push `main`

## Structure
```
├── index.html          # Page d'accueil
├── programme.html      # Grille du programme (18 talks, 10 communautés)
├── communautes.html    # 10 communautés
├── speakers.html       # 18 speakers
├── breizhcamp.html     # L'organisateur
├── epitech.html        # Le lieu
├── style.css           # CSS partagé (unique)
├── talks/              # 18 pages individuelles speaker/talk
│   ├── herve-voisin.html
│   └── ...
├── img/                # Images WebP optimisées
│   ├── hero-banner.webp
│   ├── epitech-campus.webp
│   └── communautes-gathering.webp
├── .github/workflows/  # CI/CD Firebase deploy
├── firebase.json       # Config Firebase Hosting + headers cache
├── .firebaserc         # Projet Firebase (bzhcamp-soiree-2026)
├── README.md           # Documentation
└── CLAUDE.md           # Ce fichier
```

## Conventions
- CSS : un seul fichier `style.css`, pas de styles inline sauf couleurs de communautés
- Images : format WebP, max 100KB, avec width/height/loading="lazy"
- Fonts : system font stack, pas de CDN externe
- Liens externes : `target="_blank" rel="noopener"`
- HTML : sémantique (main, article, section, nav, footer)
- Accessibilité : skip-link, focus-visible, contraste 4.5:1
- Écoconception : dark mode, reduced-motion, print styles
- Analytics : snippet GA4 ajouté via `</head>` — ne pas le supprimer

## Design system (BreizhCamp)
- `--violet: #8e3089` (accent principal)
- `--lime: #e0e04e` (CTA tertiaire)
- `--orange: #b45309` (accent secondaire)
- Échelle neutral : `--neutral-50` (#f8fafc) → `--neutral-900` (#0f172a)
- Hero gradient : `linear-gradient(135deg, #8e3089, #b45309)`
- Border-radius : 8px
- Font : Inter, system-ui, -apple-system, sans-serif

## Communautés (10 + couleurs CSS)
- Agile Rennes — `--agile: #3b82f6`
- Rennes DevOps — `--devops: #f97316`
- BreizhData Club — `--breizh: #22c55e`
- RennesJS — `--js: #eab308`
- Mobile Rennes — `--mobile: #a855f7`
- GenAI Rennes — `--genai: #ef4444`
- Software Crafters — `--crafters: #14b8a6`
- BreizhJUG — `--breizhjug: #b45309`
- AWS Rennes — `--aws: #FF9900`
- GDG Rennes — `--gdg: #E91E63`

Chaque communauté a une classe CSS `.talk-cell.{id}` dans `style.css` avec bg + border-left.

## Ajouter un talk / speaker
1. Créer `talks/{prenom-nom}.html` en copiant un fichier existant
2. Ajouter la card dans `speakers.html`
3. Ajouter la cellule dans `programme.html` (remplacer un `.talk-cell.empty`)
4. Ajouter le chip dans `index.html` (section speakers preview)
5. Mettre à jour les compteurs partout (talks, speakers, communautés)

## Monitoring & infrastructure
| Service | Détail |
|---------|--------|
| **Uptime check** | Cloud Monitoring, 60s, `bzhcamp-soiree-2026.web.app` HTTPS |
| **Alertes down** | Email → `nicolas.bouron@gmail.com`, déclenchement après 60s |
| **Analytics** | GA4 `G-0KXV4BWTBD` — Firebase Console + analytics.google.com |
| **Logs d'accès** | Cloud Logging → `resource.type="firebase_domain"` |

## Déploiement
```bash
# Le CI/CD déploie automatiquement sur push main
# Déploiement manuel si besoin :
firebase deploy --only hosting
```
URL live : https://bzhcamp-soiree-2026.web.app/
