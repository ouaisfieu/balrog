# 📖 La Réserve - Guide d'utilisation

## Qu'est-ce que La Réserve ?

La Réserve est un **système ARG (Alternate Reality Game)** qui permet de créer des actions de détournement institutionnel. Chaque action génère une page web autonome que vous pouvez publier n'importe où.

> *"Ce qui existe déjà mais n'a jamais été reconnu."*

---

## 🚀 Démarrage rapide

### Option 1 : Utiliser en ligne
1. Ouvrez `index.html` dans votre navigateur
2. Remplissez le formulaire
3. Cliquez sur "Générer ma page"
4. Téléchargez votre fichier HTML

### Option 2 : Héberger localement
```bash
# Clonez ou téléchargez le projet
git clone https://github.com/votre-compte/la-reserve.git

# Ouvrez dans un navigateur
open index.html
# ou
python -m http.server 8000  # puis visitez localhost:8000
```

---

## 📝 Comment créer une action ?

### 1. Remplir le formulaire

L'éditeur propose **4 onglets** :

| Onglet | Contenu |
|--------|---------|
| 📝 Infos de base | Titre, type, statut, description en Markdown |
| 👥 Recrues | Personnes impliquées (réelles, fictives, vous-même) |
| 📅 Timeline | Journal chronologique des événements |
| 👁️ Aperçu | Prévisualisation de la page finale |

### 2. Utiliser le Markdown

La description supporte le **Markdown** complet :

```markdown
# Titre principal
## Sous-titre

**Texte en gras** et *italique*

- Liste à puces
- Autre élément

1. Liste numérotée
2. Deuxième point

> Citation ou blockquote

`code inline`

[Lien](https://example.com)

![Image](url-de-image.jpg)
```

**Raccourcis clavier :**
- `Ctrl+B` : Gras
- `Ctrl+I` : Italique  
- `Ctrl+S` : Sauvegarder le brouillon
- `Tab` : Indenter

### 3. Types de recrues

| Type | Description | Exemple |
|------|-------------|---------|
| 👤 Réelle | Personne existante | Un·e ami·e, collègue |
| 🎭 Fictive | Personnage inventé | Jean Dupont, Agent X |
| 🪞 Moi-même | Vous sous un autre rôle | Votre alter-ego |
| 💼 Fonction | Rôle abstrait | "Le recruteur", "La DRH" |

### 4. Exporter votre action

Cliquez sur **"🚀 Générer ma page"** pour obtenir :

- 💾 **Fichier HTML** — Page autonome à publier
- 📦 **Fichier JSON** — Données pour backup/import
- 📋 **Copier JSON** — Presse-papier
- 🐦 **Partager sur X/Twitter**
- 🐘 **Partager sur Mastodon**

---

## 🎨 Personnalisation

### Thèmes disponibles

| Thème | Description |
|-------|-------------|
| ☀️ Clair | Design lumineux et aéré |
| 🌙 Sombre | Mode nuit élégant |
| 🪩 Disco | Couleurs vives et festives |
| 💜 Néon | Ambiance cyberpunk |
| 👾 Retro | Style pixel art 8-bit |
| 💻 Console | Terminal hacker |

### Typographies

| Style | Polices |
|-------|---------|
| Élégant | Playfair Display + Work Sans |
| Organique | Fraunces + Manrope |
| Editorial | DM Serif Display + Inter |
| Littéraire | Libre Baskerville + Archivo |
| Poétique | Instrument Serif + Plus Jakarta Sans |
| Brut | Bricolage Grotesque + Crimson Pro |

> Le thème et la typographie choisis sont **intégrés dans la page exportée**.

---

## 📁 Structure de projet recommandée

```
mon-projet-la-reserve/
├── README.md                    ← Ce fichier
├── index.html                   ← Interface principale
├── actions/
│   ├── action-lr-abc123.html   ← Pages générées
│   ├── action-lr-abc123.json   ← Données JSON
│   ├── action-lr-def456.html
│   └── action-lr-def456.json
└── assets/
    └── images/                  ← Vos captures d'écran, preuves
```

---

## 📥 Import/Export

### Exporter une action

1. Créez votre action dans le formulaire
2. Cliquez sur "Générer ma page"
3. Téléchargez le HTML et/ou le JSON

### Importer une action existante

1. Cliquez sur "📥 Importer un JSON"
2. Sélectionnez votre fichier `.json`
3. Les données remplissent automatiquement le formulaire
4. Modifiez si nécessaire, puis régénérez

### Format JSON

```json
{
  "id": "LR-ABC123DEF",
  "titre": "Coordinateur·rice de silences",
  "pseudo": "Anonyme",
  "lieu": "Bruxelles",
  "type": "silence",
  "statut": "en-cours",
  "description": "# Mon action\n\nDescription en **Markdown**...",
  "asbl": "ASBL Fictive",
  "recrues": [
    { "nom": "Jean", "type": "fictive", "role": "Complice" }
  ],
  "timeline": [
    { "date": "2025-01-15", "type": "creation", "description": "Début" }
  ],
  "theme": "clair",
  "style": "elegant",
  "createdAt": "2025-01-15T10:30:00.000Z"
}
```

---

## 🌐 Publication

### GitHub Pages (gratuit)

1. Créez un dépôt GitHub
2. Uploadez vos fichiers HTML
3. Allez dans Settings → Pages
4. Sélectionnez la branche `main`
5. Votre action est en ligne à `https://votre-compte.github.io/votre-depot/`

### Netlify / Vercel

1. Connectez votre dépôt GitHub
2. Le déploiement est automatique à chaque commit

### Hébergement manuel

Uploadez simplement les fichiers HTML sur n'importe quel serveur web :
- Apache, Nginx
- Serveur Node.js
- Hébergement mutualisé classique

### IPFS (décentralisé)

```bash
ipfs add -r mon-projet-la-reserve/
```

Votre action devient accessible via une adresse IPFS permanente.

---

## 🔧 Fonctionnalités avancées

### Codes d'intégration (embed)

Dans l'onglet Aperçu → "📦 Code embed" :

**Iframe :**
```html
<iframe src="action-lr-abc123.html" width="100%" height="600" frameborder="0"></iframe>
```

**Open Graph (pour les previews sur réseaux sociaux) :**
```html
<meta property="og:title" content="Titre de votre action">
<meta property="og:description" content="Description...">
<meta property="og:type" content="article">
```

**Markdown :**
```markdown
[Titre de l'action](https://votre-site.com/action-lr-abc123.html)
```

### Sauvegarde automatique

Le brouillon est sauvegardé automatiquement dans le `localStorage` du navigateur. Vous pouvez fermer la page et revenir plus tard.

### Pièces jointes

Glissez-déposez des fichiers dans la zone prévue. 
> Note : Les fichiers sont référencés mais pas embarqués dans le HTML. Hébergez-les séparément.

---

## 🤝 Contribuer au projet

La Réserve est un projet ouvert. Vous pouvez :

- ✅ Créer et partager vos propres actions
- 💡 Proposer des améliorations via Issues/PR
- 📝 Documenter vos expériences de détournement
- 🔀 Forker et adapter le projet à vos besoins

### Licence

Ce projet est sous licence **CC BY-SA 4.0** (Creative Commons Attribution-ShareAlike).

Vous pouvez :
- Partager et adapter librement
- À condition de créditer et partager sous la même licence

---

## ❓ FAQ

### Les pages fonctionnent-elles hors ligne ?

**Oui.** Chaque page HTML est autonome et fonctionne sans serveur. Les polices sont chargées depuis Google Fonts, donc une connexion est nécessaire pour le premier chargement.

### Puis-je modifier une action après génération ?

**Oui.** Importez le fichier JSON correspondant, modifiez, et régénérez.

### Les données sont-elles envoyées quelque part ?

**Non.** Tout fonctionne dans votre navigateur. Aucune donnée n'est transmise à un serveur.

### Puis-je utiliser mon propre domaine ?

**Oui.** Hébergez les fichiers HTML sur votre serveur et utilisez votre domaine.

---

## 📞 Contact

Pour toute question ou suggestion, créez une Issue sur le dépôt GitHub du projet.

---

*La Réserve — Ce qui existe déjà mais n'a jamais été reconnu.*
