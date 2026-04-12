# Holberton School — Web Front-End

## Description

Ce projet couvre les fondamentaux du **développement web front-end** : construction de pages HTML sémantiques et stylisation avancée avec CSS. Il est organisé en deux sous-projets progressifs : `html_advanced` et `CSS_advanced`.

---

## Cours : Développement Web Front-End

### L'architecture du web

```
Navigateur (Client)
    │
    ├── HTML   → Structure et contenu
    ├── CSS    → Présentation et mise en page
    └── JS     → Interactivité et comportement
```

### Comment le navigateur interprète une page

1. Parse le HTML → construit le **DOM** (Document Object Model)
2. Parse le CSS → construit le **CSSOM**
3. Combine les deux → **Render Tree**
4. Calcule la disposition (**Layout**)
5. Affiche à l'écran (**Paint**)

---

## Sous-projet 1 : `html_advanced/`

Construction progressive d'une page web complète pour la marque fictive **Techium** (agence digitale).

### Cours HTML5

#### Structure de base

```html
<!DOCTYPE html>           <!-- Déclaration HTML5 -->
<html lang="fr" dir="ltr">
<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Titre de la page</title>
</head>
<body>
    <!-- Contenu visible -->
</body>
</html>
```

#### Balises sémantiques HTML5

| Balise | Rôle |
|--------|------|
| `<header>` | En-tête de page ou de section |
| `<nav>` | Barre de navigation |
| `<main>` | Contenu principal (unique par page) |
| `<section>` | Section thématique |
| `<article>` | Contenu autonome (billet, carte) |
| `<aside>` | Contenu secondaire (sidebar) |
| `<footer>` | Pied de page |
| `<figure>` | Illustration avec légende |
| `<figcaption>` | Légende d'une figure |

#### Balises courantes

```html
<!-- Titres hiérarchiques (1 seul h1 par page) -->
<h1>Titre principal</h1>
<h2>Sous-titre</h2>

<!-- Paragraphe et texte -->
<p>Un paragraphe.</p>
<strong>Important</strong>  <!-- Gras sémantique -->
<em>Emphase</em>            <!-- Italique sémantique -->

<!-- Liens et images -->
<a href="https://exemple.com">Texte du lien</a>
<img src="image.jpg" alt="Description" width="300">

<!-- Listes -->
<ul>                         <!-- Non ordonnée -->
    <li>Élément</li>
</ul>
<ol>                         <!-- Ordonnée -->
    <li>Premier</li>
</ol>

<!-- Tableau -->
<table>
    <thead><tr><th>En-tête</th></tr></thead>
    <tbody><tr><td>Données</td></tr></tbody>
</table>
```

#### Attributs importants

| Attribut | Usage |
|----------|-------|
| `id` | Identifiant unique sur la page |
| `class` | Classe CSS (peut être multiple) |
| `href` | URL d'un lien |
| `src` | Source d'une image ou script |
| `alt` | Texte alternatif (accessibilité) |
| `lang` | Langue du contenu |
| `data-*` | Attributs personnalisés |

#### Bonnes pratiques HTML

- Un seul `<h1>` par page
- Toujours remplir `alt` sur les images
- Utiliser des balises sémantiques plutôt que `<div>` partout
- Valider son HTML : [validator.w3.org](https://validator.w3.org)

---

## Sous-projet 2 : `CSS_advanced/`

Application du style CSS à la structure HTML pour créer une page visuellement attrayante.

### Cours CSS3

#### Comment lier CSS au HTML

```html
<!-- Feuille de style externe (recommandé) -->
<link rel="stylesheet" href="styles/main.css">

<!-- CSS intégré dans la page -->
<style>
    body { margin: 0; }
</style>

<!-- CSS en ligne (à éviter sauf cas particulier) -->
<p style="color: red;">Texte rouge</p>
```

#### Sélecteurs CSS

```css
/* Élément */
p { color: black; }

/* Classe */
.ma-classe { font-size: 16px; }

/* ID */
#mon-id { background: blue; }

/* Descendant */
nav ul li { list-style: none; }

/* Pseudo-classe */
a:hover { color: orange; }
button:disabled { opacity: 0.5; }

/* Pseudo-élément */
p::first-line { font-weight: bold; }
li::before { content: "→ "; }
```

#### Le modèle de boîte (Box Model)

```
┌──────────────────────────┐
│         margin           │
│  ┌────────────────────┐  │
│  │      border        │  │
│  │  ┌──────────────┐  │  │
│  │  │   padding    │  │  │
│  │  │  ┌────────┐  │  │  │
│  │  │  │content │  │  │  │
│  │  │  └────────┘  │  │  │
│  │  └──────────────┘  │  │
│  └────────────────────┘  │
└──────────────────────────┘

box-sizing: border-box; /* padding et border inclus dans width */
```

#### Flexbox — mise en page flexible

```css
.container {
    display: flex;
    justify-content: space-between; /* Axe principal */
    align-items: center;            /* Axe secondaire */
    flex-wrap: wrap;                /* Retour à la ligne */
    gap: 1rem;
}

.item {
    flex: 1;        /* Grandit pour remplir l'espace */
}
```

#### Variables CSS

```css
:root {
    --color-primary: #C271FF;
    --font-size-base: 16px;
    --spacing-md: 1.5rem;
}

.button {
    background-color: var(--color-primary);
    font-size: var(--font-size-base);
}
```

#### Media Queries — Responsive Design

```css
/* Mobile first */
.container { width: 100%; }

/* Tablette */
@media (min-width: 768px) {
    .container { width: 750px; }
}

/* Desktop */
@media (min-width: 1200px) {
    .container { width: 1140px; }
}
```

---

## Structure du projet

```
holbertonschool-web_front_end/
├── html_advanced/
│   ├── 0-index.html          ← Structure HTML minimale
│   ├── 1-index.html          ← Ajout du header
│   ├── ...
│   ├── index.html            ← Page Techium complète
│   ├── about.html
│   ├── contact.html
│   ├── article.html
│   └── styleguide.html       ← Guide de style des composants
│
└── CSS_advanced/
    ├── index.html            ← HTML complet avec classes CSS
    └── styles/               ← Feuilles de style CSS
```

---

## Objectifs pédagogiques

- Structurer une page web avec HTML5 sémantique
- Styler avec CSS3 (Flexbox, variables, responsive)
- Comprendre l'accessibilité web
- Construire un site web complet de façon progressive

---

## Auteur

Projet réalisé dans le cadre du cursus **Holberton School France**.
