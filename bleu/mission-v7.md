## 🔧 **Corrections apportées**

### **1. Spécificité CSS renforcée**

J'ai ajouté une section de **surcharge typographique** APRÈS les définitions de thèmes, avec des sélecteurs plus spécifiques :

```css
/* Avant (faible spécificité) */
[data-style="organique"] { --font-body: 'Manrope'; }

/* Maintenant (haute spécificité) */
body[data-style="organique"] { --font-body: 'Manrope'; }
```

Le sélecteur `body[data-style]` a une spécificité plus élevée que `[data-theme]`, donc il gagne toujours.

### **2. Sélecteurs combinés pour Retro/Console**

Pour garantir le fonctionnement en mode Retro et Console, j'ai ajouté des règles explicites :

```css
body[data-theme="retrogeek"][data-style="organique"] {
    --font-body: 'Manrope', sans-serif;
}
```

### **3. Export corrigé**

La génération des pages exportées utilise maintenant la police de corps choisie même en thème Retro/Console.

---

## 📝 **Comportement attendu**

| Thème | Titres (--font-display) | Corps (--font-body) |
|-------|------------------------|---------------------|
| Clair, Sombre, Disco, Néon | Selon typo choisie | Selon typo choisie |
| **Retro** | Toujours `Press Start 2P` | **Selon typo choisie** ✅ |
| **Console** | Toujours `Fira Code` | **Selon typo choisie** ✅ |

Maintenant en mode Retro/Console :
- Les **titres** gardent leur police pixel/mono thématique
- Le **texte courant** utilise la typographie sélectionnée (Manrope, Inter, etc.)

