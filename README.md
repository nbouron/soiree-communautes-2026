# Soirée des communautés rennaises 2026

Site web écoresponsable pour la soirée des communautés tech rennaises.

**📅 9 avril 2026** · **📍 Epitech Rennes** · **🎫 Gratuit**

🔗 **Site live** : [bzhcamp-soiree-2026.web.app](https://bzhcamp-soiree-2026.web.app/)
🎟️ **Inscription** : [events.rennes.tech](https://events.rennes.tech/events/b47d3641-f591-40e0-8fa5-ec8473d16bb7)

## L'événement

Les communautés tech de Rennes se retrouvent pour une soirée de talks courts (20min + 5min Q&A), de partage d'expérience et de convivialité. 16 talks, 8 communautés, 6 salles en parallèle. Pizzas et boissons offerts après les présentations.

### Communautés participantes

Agile Rennes · Rennes DevOps · BreizhData Club · RennesJS · Mobile Rennes · GenAI Rennes · Software Crafters · BreizhJUG

Organisé par le [BreizhCamp](https://www.breizhcamp.org/), accueilli par [Epitech Rennes](https://www.epitech.eu/ecole-informatique-rennes/).

## Écoconception web

Ce site applique les principes d'écoconception numérique :

### Choix techniques

| Pratique | Détail | Impact |
|----------|--------|--------|
| **Images WebP** | Compression quality 75, max 1200-1600px | 8.9 MB → 272 KB (-97%) |
| **CSS unique** | Un seul fichier `style.css` partagé | Élimine ~200KB de CSS dupliqué |
| **Polices système** | Inter/system-ui sans CDN Google | 0 requête externe pour les fonts |
| **HTML sémantique** | `main`, `article`, `section`, `nav` | Parsing optimisé |
| **Dark mode** | `prefers-color-scheme: dark` | Économie OLED estimée -60% |
| **Mouvement réduit** | `prefers-reduced-motion: reduce` | Respect des préférences utilisateur |
| **Cache long** | Images/CSS : 1 an, HTML : no-cache | Réduit les requêtes réseau |
| **Print styles** | Impression propre sans nav/footer | Évite l'impression inutile |
| **Accessibilité** | Skip-link, focus-visible, contraste 4.5:1 | L'accessibilité est éco-responsable |
| **Pas de JavaScript** | Site 100% HTML/CSS statique | Zéro coût d'exécution JS |

### Objectifs

- Poids total du site : **< 1 MB**
- Poids homepage : **< 200 KB** (HTML + CSS + images)
- EcoIndex : **grade A ou B** (score ≥ 70)
- Empreinte carbone : **< 0.5g CO2** par page vue
- Lighthouse performance : **≥ 90**
- Lighthouse accessibilité : **≥ 90**

### Références

- [RGESN](https://ecoresponsable.numerique.gouv.fr/publications/referentiel-general-ecoconception/) — Référentiel Général d'Écoconception de Services Numériques
- [W3C Web Sustainability Guidelines](https://www.w3.org/TR/sustainability-web/) — Directives W3C
- [GreenIT.fr](https://www.greenit.fr/) — Collectif écoconception numérique
- [EcoIndex](https://www.ecoindex.fr/) — Mesure l'empreinte environnementale des sites web

## Stack technique

- HTML5 sémantique + CSS (pas de JavaScript)
- Images WebP optimisées
- Polices système (Inter/system-ui)
- Firebase Hosting

## Développement

```bash
# Serveur local
python3 -m http.server 8765

# Déployer
firebase deploy --only hosting
```

## Licence

Site du BreizhCamp — Tous droits réservés.
