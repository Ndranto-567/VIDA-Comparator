# ComparListes — Réclamations & Droits

Application web de comparaison de listes Excel pour analyser les réclamations de droits.

## 🚀 Utilisation directe (sans installation)

**Double-cliquez sur `index.html`** — l'application s'ouvre dans votre navigateur. Aucune installation requise.

## ☁️ Mise en ligne sur GitHub Pages (partage avec le groupe)

### Étape 1 — Créer un compte GitHub
Aller sur [github.com](https://github.com) → Sign up (gratuit)

### Étape 2 — Créer un nouveau dépôt
1. Cliquer sur **New repository**
2. Nom : `comparlistes`
3. Visibilité : **Public**
4. Cliquer **Create repository**

### Étape 3 — Uploader le fichier
1. Dans le dépôt créé, cliquer **uploading an existing file**
2. Glisser-déposer `index.html`
3. Cliquer **Commit changes**

### Étape 4 — Activer GitHub Pages
1. Aller dans **Settings** → **Pages**
2. Source : **Deploy from a branch**
3. Branch : **main** / **(root)**
4. Cliquer **Save**

### Étape 5 — Partager le lien
Après 1-2 minutes, l'application sera accessible à :
```
https://VOTRE_USERNAME.github.io/comparlistes/
```
Partagez ce lien avec les membres du groupe !

---

## 📊 Les 8 listes produites

| Liste | Définition | Signification |
|-------|-----------|---------------|
| **A** | Données complètes fichier A | Source — Réclamants |
| **B** | Données complètes fichier B | Source — Liste financière |
| **C = A ∩ B** | Correspondance exacte (≥95%) | Cas confirmés |
| **D = A \ B** | Réclamants absents de B | Réclamations suspectes |
| **E = B \ A** | Dans B sans réclamation | Droits non réclamés |
| **F ≈ D ↔ E** | Correspondances floues | Probable même personne |
| **G ⊂ A** | Non trouvés côté A | Indéterminés A |
| **H ⊂ B** | Non trouvés côté B | Indéterminés B |

---

## 🔧 Critères de comparaison
- **Nom complet** — algorithme Jaro-Winkler (gère les fautes d'orthographe)
- **Numéro CIN** — comparaison normalisée
- **Téléphone** — 9 derniers chiffres (ignore les préfixes)

Une personne est "trouvée" si **au moins 1 critère** atteint le seuil.
