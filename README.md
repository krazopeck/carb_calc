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

## Déploiement sur GitHub Pages

### 1. Créer le dépôt

Sur github.com, créer un nouveau dépôt public, par exemple `nutrition-course`.

### 2. Pousser les fichiers

Dans un terminal, depuis le dossier qui contient `index.html`, `manifest.json`, `icon.svg` et ce `README.md` :

```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/TON_PSEUDO/nutrition-course.git
git push -u origin main
```

### 3. Activer GitHub Pages

Dans le dépôt sur github.com :
1. **Settings** → **Pages** (menu de gauche)
2. Sous *Build and deployment* → *Source* : choisir **Deploy from a branch**
3. *Branch* : sélectionner `main` et le dossier `/ (root)`
4. Cliquer sur **Save**

Après 1-2 minutes, l'app sera disponible à l'adresse :
```
https://TON_PSEUDO.github.io/nutrition-course/
```

### 4. Installer sur ton téléphone

**iPhone (Safari)** :
- Ouvrir l'URL dans Safari
- Bouton Partage → *Sur l'écran d'accueil*
- L'icône apparaît comme une vraie app

**Android (Chrome)** :
- Ouvrir l'URL dans Chrome
- Menu ⋮ → *Ajouter à l'écran d'accueil* (ou une pop-up proposera directement)

## Personnaliser

Tout est dans `index.html` (HTML + CSS + JS dans un seul fichier).

- **Aliments préchargés** : modifier le tableau `DEFAULT_FOODS` en haut du `<script>` (autour de la ligne qui commence par `const DEFAULT_FOODS = [...]`)
- **Couleurs** : variables CSS dans `:root` (`--ios-blue`, `--ios-orange`, etc.)
- **Valeurs par défaut** (durée, objectif) : modifier l'objet `state` ou les `value=""` des inputs

> ⚠️ Après changement de code, si tu as déjà ouvert l'app une fois, ton navigateur gardera ton ancien état dans `localStorage`. Pour repartir de zéro : DevTools → Application → Local Storage → supprimer la clé `nutrition-course-v1`.

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
