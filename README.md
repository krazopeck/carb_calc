# Nutrition Course

Petite web-app (style iOS) pour calculer le ravitaillement en glucides de tes sorties longues. Tu entres la durée et ton objectif g/h, tu ajoutes ce que tu as dans le sac, et l'app te dit si c'est suffisant.

## Fonctionnalités

- **Paramètres de sortie** : durée (h) + objectif (g/h) → calcul du besoin total
- **Bibliothèque d'aliments** : 8 aliments préchargés (gel, banane, barre, etc.) + ajout d'aliments personnalisés
- **Stepper ± par aliment** pour la quantité dans le sac
- **Barre de progression** collée en bas avec statut en temps réel : *"Il manque X g"* ou *"Objectif atteint ✓"*
- **Persistance** via `localStorage` — tes aliments et paramètres sont gardés entre les visites
- **Dark mode automatique** (suit le système)
- **Installable sur iPhone/Android** via "Ajouter à l'écran d'accueil" → l'app s'ouvre en plein écran comme une vraie app

## Structure

```
nutrition-course/
├── index.html       # l'app entière (HTML + CSS + JS)
├── manifest.json    # métadonnées PWA (nom, icônes, couleurs)
├── icon.svg         # icône vectorielle pour l'écran d'accueil
└── README.md        # ce fichier
```

## Notes techniques

- Pur HTML/CSS/JS vanilla, aucun build, aucune dépendance
- Les valeurs de glucides des aliments préchargés sont indicatives — à ajuster selon les produits que tu utilises réellement
- Recommandations nutritionnelles générales : 30–60 g/h de glucides sur sorties longues d'endurance, jusqu'à 90 g/h en compétition avec un mix glucose/fructose
