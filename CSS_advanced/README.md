# CSS - Advanced

## Concepts clés

### Qu'est-ce que CSS ?

**CSS** (Cascading Style Sheets) est le langage qui contrôle l'apparence visuelle des pages HTML : couleurs, polices, marges, mise en page.

```html
<!-- Lier un fichier CSS à la page -->
<link rel="stylesheet" href="styles/1-style.css">
```

---

### Sélecteurs CSS

```css
/* Balise HTML */
body { color: #161616; }

/* Classe (réutilisable) */
.card-category { color: #D73953; }

/* ID (unique) */
#header { background: black; }

/* Pseudo-classe */
a:hover { text-decoration: underline; }

/* Pseudo-élément */
p::first-line { font-weight: bold; }

/* Combinateurs */
header nav { ... }      /* nav descendant de header */
section > p { ... }     /* p enfant direct de section */
h2 + p { ... }          /* p immédiatement après h2 */
```

---

### Variables CSS (Custom Properties) — 10-style.css

```css
:root {
    --color-primary: #d73953;
    --color-black: #090909;
    --color-white: #ffffff;
    --font-family-base: "Open Sans", "Helvetica Neue", Helvetica, Arial, sans-serif;
    --font-size-medium: 1.6rem;
    --font-weight-bold: 700;
    --line-height-base: 1.5;
}

body {
    color: var(--color-black);
    font-family: var(--font-family-base);
    font-size: var(--font-size-medium);
}
```

- `:root` : pseudo-classe qui cible l'élément racine (`<html>`). Idéal pour définir des variables globales.
- `--nom-variable: valeur` : déclare une variable CSS.
- `var(--nom-variable)` : utilise la variable.
- Les variables en cascade : si une variable est redéfinie dans un enfant, elle écrase la valeur héritée.

---

### Typographie

```css
body {
    font-family: "Open Sans", Arial, sans-serif;  /* police avec fallbacks */
    font-size: 1.6rem;     /* 1rem = 16px (par défaut) */
    font-weight: 400;      /* 400 = normal, 700 = bold */
    line-height: 1.5;      /* hauteur de ligne = 1.5 × la taille de police */
}

/* Trick courant : base 10 pour faciliter les calculs rem */
html {
    font-size: 62.5%;   /* 62.5% de 16px = 10px → 1rem = 10px */
}
/* Donc 1.6rem = 16px, 2.4rem = 24px, etc. */
```

**Unités de taille :**

| Unité | Définition |
|-------|------------|
| `px` | Pixel fixe |
| `rem` | Relatif à la police racine (`html`) |
| `em` | Relatif à la police du parent |
| `%` | Relatif au parent |

---

### Couleurs

```css
color: #d73953;          /* hexadécimal */
color: rgb(215, 57, 83); /* RGB */
color: rgba(0, 0, 0, 0.5); /* RGB avec transparence */
background-color: var(--color-light-grey);
```

---

### Box Model

```
┌─────────────────────────┐
│         margin          │
│  ┌───────────────────┐  │
│  │      border       │  │
│  │  ┌─────────────┐  │  │
│  │  │   padding   │  │  │
│  │  │  ┌───────┐  │  │  │
│  │  │  │content│  │  │  │
│  │  │  └───────┘  │  │  │
│  │  └─────────────┘  │  │
│  └───────────────────┘  │
└─────────────────────────┘
```

```css
.box {
    width: 300px;
    padding: 16px;       /* espace intérieur */
    border: 2px solid #000;
    margin: 24px;        /* espace extérieur */

    /* box-sizing: border-box inclut padding+border dans width */
    box-sizing: border-box;
}
```

---

### Normalize.css — 20-style.css

**normalize.css** est une feuille de style qui harmonise les styles par défaut des navigateurs (Chrome, Firefox, Safari ont des valeurs par défaut différentes).

```css
/* Exemple de normalize */
body { margin: 0; }  /* supprime la marge par défaut du body */
h1 { font-size: 2em; margin: 0.67em 0; }

/* Ajout courant après normalize */
*, *::before, *::after {
    box-sizing: border-box;  /* comportement cohérent pour toutes les boîtes */
}
```

---

### Affichage — `display`

```css
.element {
    display: block;        /* bloc (prend toute la largeur) */
    display: inline;       /* en ligne (ne prend que sa largeur) */
    display: inline-block; /* en ligne mais avec dimensions contrôlables */
    display: none;         /* masqué (ne prend aucun espace) */
    display: flex;         /* flexbox (disposition flexible) */
}
```

---

### Visually hidden

```css
.visually-hidden {
    display: none;
}
```

Ce pattern masque du contenu visuellement tout en le gardant dans le HTML (utile pour les lecteurs d'écran ou les éléments conditionnels).

---

### Pseudo-classes et pseudo-éléments

```css
a:hover { color: var(--color-primary); }     /* au survol */
a:active { opacity: 0.8; }                   /* au clic */
input:focus { outline: 2px solid blue; }     /* quand actif */

p::before { content: "→ "; }                /* avant l'élément */
p::after { content: " ←"; }                 /* après l'élément */
```

---

## Résumé des fichiers

| Fichier | Concept principal |
|---------|-------------------|
| `1-style.css` | `scroll-behavior: smooth` |
| `2-style.css` | Couleurs de base sur `body`, `a`, `.card-category` |
| `3-style.css` | `.visually-hidden` |
| `10-style.css` | Variables CSS (`--color-*`, `--font-*`), `:root` |
| `11-style.css` | `font-family`, `font-size: 62.5%`, `line-height` |
| `12-style.css` | Typographie des titres `h1`–`h4` |
| `13-style.css` | Liens : couleur, `text-decoration` |
| `14-style.css` | `box-sizing: border-box` |
| `15-style.css` | Conteneur `.container`, `width`, `margin: auto` |
| `16-style.css` | `padding` des sections |
| `17-style.css` | Couleurs de fond par section |
| `20-style.css` | Intégration de normalize.css |
| `21-style.css` | Reset margin/padding globaux |
| `22-style.css` | Styles du header |
| `25-style.css` | Cartes et articles |
| `27-style.css` | Footer |
