# Soirée des communautés rennaises 2026 — Site web

## Projet
Site statique écoresponsable pour la soirée des communautés tech rennaises, organisée par le BreizhCamp et accueillie par Epitech Rennes le 9 avril 2026.

## Stack technique
- HTML5 sémantique + CSS (un seul fichier `style.css`)
- Pas de JavaScript framework
- Images WebP optimisées
- Police système (Inter/system-ui, pas de Google Fonts CDN)
- Déploiement : Firebase Hosting (`bzhcamp-soiree-2026`)

## Structure
```
├── index.html          # Page d'accueil
├── programme.html      # Grille du programme
├── communautes.html    # 8 communautés
├── speakers.html       # 16 speakers
├── breizhcamp.html     # L'organisateur
├── epitech.html        # Le lieu
├── style.css           # CSS partagé (unique)
├── talks/              # 16 pages individuelles speaker/talk
│   ├── herve-voisin.html
│   └── ...
├── img/                # Images WebP optimisées
│   ├── hero-banner.webp
│   ├── epitech-campus.webp
│   └── communautes-gathering.webp
├── firebase.json       # Config Firebase Hosting
├── .firebaserc         # Projet Firebase
├── README.md           # Documentation
└── CLAUDE.md           # Ce fichier
```

## Conventions
- CSS : un seul fichier `style.css`, pas de styles inline
- Images : format WebP, max 100KB, avec width/height/loading="lazy"
- Fonts : system font stack, pas de CDN externe
- Liens externes : `target="_blank" rel="noopener"`
- HTML : sémantique (main, article, section, nav, footer)
- Accessibilité : skip-link, focus-visible, contraste 4.5:1
- Écoconception : dark mode, reduced-motion, print styles

## Design system (BreizhCamp)
- `--violet: #8e3089` (accent principal)
- `--lime: #e0e04e` (CTA tertiaire)
- `--orange: #b45309` (accent secondaire)
- Échelle neutral : `--neutral-50` (#f8fafc) → `--neutral-900` (#0f172a)
- Hero gradient : `linear-gradient(135deg, #8e3089, #b45309)`
- Border-radius : 8px
- Font : Inter, system-ui, -apple-system, sans-serif

## Communautés (8 + couleurs)
- Agile Rennes (#3b82f6)
- Rennes DevOps (#f97316)
- BreizhData Club (#22c55e)
- RennesJS (#eab308)
- Mobile Rennes (#a855f7)
- GenAI Rennes (#ef4444)
- Software Crafters (#14b8a6)
- BreizhJUG (#b45309)

## Déploiement
```bash
firebase deploy --only hosting
```
URL : https://bzhcamp-soiree-2026.web.app/
