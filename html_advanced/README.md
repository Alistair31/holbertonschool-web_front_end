# HTML - Advanced

## Concepts clés

### Structure d'une page HTML

```html
<!DOCTYPE html>
<html lang="EN" dir="ltr">
    <head>
        <meta charset="utf-8">
        <title>Ma page</title>
    </head>
    <body>
        <!-- contenu visible -->
    </body>
</html>
```

- `<!DOCTYPE html>` : déclare le document comme HTML5.
- `<html lang="EN" dir="ltr">` : langue et direction du texte.
- `<head>` : métadonnées (invisibles à l'utilisateur).
- `<body>` : contenu visible.

---

### Balises `<head>` essentielles

```html
<head>
    <meta charset="utf-8">
    <!-- encodage des caractères (accents, etc.) -->

    <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
    <!-- responsive design sur mobile -->

    <meta name="description" content="Description du site">
    <!-- résumé pour les moteurs de recherche -->

    <title>Titre affiché dans l'onglet</title>

    <link rel="icon" type="image/x-icon" href="./favicon.ico">
    <!-- icône de l'onglet -->
</head>
```

---

### Balises sémantiques de structure

Les balises sémantiques donnent du **sens** au contenu (pour les navigateurs, moteurs de recherche, lecteurs d'écran).

```html
<body>
    <header>   <!-- en-tête de page ou de section -->
        <nav>…</nav>   <!-- barre de navigation -->
    </header>

    <main>   <!-- contenu principal (unique par page) -->
        <section>   <!-- groupe thématique de contenu -->
            <article>   <!-- contenu autonome (blog post, carte) -->
                <aside>   <!-- contenu secondaire / barre latérale -->
            </article>
        </section>
    </main>

    <footer>   <!-- pied de page -->
</body>
```

---

### Titres et paragraphes

```html
<h1>Titre principal (un seul par page)</h1>
<h2>Titre de section</h2>
<h3>Sous-titre</h3>
<h4>Sous-sous-titre</h4>

<p>Un paragraphe de texte.</p>

<span>Texte en ligne (sans saut de ligne)</span>
```

- Les titres `<h1>` à `<h6>` définissent une hiérarchie.
- `<p>` est un bloc (saut de ligne avant et après).
- `<span>` est en ligne (dans un paragraphe).

---

### Listes

```html
<!-- Liste non ordonnée (puces) -->
<ul>
    <li>Élément 1</li>
    <li>Élément 2</li>
</ul>

<!-- Liste ordonnée (numérotée) -->
<ol>
    <li>Premier</li>
    <li>Deuxième</li>
</ol>
```

---

### Liens — `<a>`

```html
<!-- Lien interne -->
<a href="./about.html">À propos</a>

<!-- Lien externe -->
<a href="https://example.com" target="_blank" rel="noopener">Visiter</a>

<!-- Lien vers une ancre -->
<a href="#section-contact">Contact</a>

<!-- Lien vers une section avec id -->
<section id="section-contact">…</section>
```

- `href` : destination du lien.
- `target="_blank"` : ouvrir dans un nouvel onglet.
- `rel="noopener"` : sécurité pour les liens externes.

---

### Images — `<img>`

```html
<img src="images/logo.png" alt="Logo Techium" width="200" height="100">
```

- `src` : chemin vers l'image.
- `alt` : texte alternatif (accessibilité, SEO).
- `width` / `height` : dimensions (évitent le décalage de mise en page).

---

### Navigation

```html
<nav>
    <ul>
        <li><a href="./">Home</a></li>
        <li><a href="services">Services</a></li>
        <li><a href="about">About</a></li>
        <li><a href="contact">Contact</a></li>
    </ul>
</nav>
```

---

### Conteneurs génériques — `<div>` et `<span>`

```html
<!-- div : conteneur bloc (nouvelle ligne) -->
<div class="container">
    <p>Contenu</p>
</div>

<!-- span : conteneur en ligne (dans un texte) -->
<p>Bonjour <span class="highlight">monde</span> !</p>
```

- `<div>` est utilisé pour regrouper des éléments en bloc.
- `<span>` est utilisé pour styliser une partie de texte en ligne.

---

### Formulaires

```html
<form action="/submit" method="POST">
    <label for="email">Email :</label>
    <input type="email" id="email" name="email" placeholder="exemple@email.com">

    <label for="message">Message :</label>
    <textarea id="message" name="message"></textarea>

    <button type="submit">Envoyer</button>
</form>
```

- `action` : URL où les données sont envoyées.
- `method` : `GET` (dans l'URL) ou `POST` (dans le corps).
- `<label for="id">` : associe le label à l'input correspondant.

---

### Tableaux

```html
<table>
    <thead>
        <tr>
            <th>Nom</th>
            <th>Âge</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Alice</td>
            <td>30</td>
        </tr>
    </tbody>
</table>
```

---

## Résumé des fichiers

| Fichier | Concept principal |
|---------|-------------------|
| `0-index.html` | Structure minimale `<html>` |
| `3-index.html` | `<head>` complet, métadonnées, `<body>` sémantique |
| `5-index.html` | `<header>`, `<main>`, `<footer>` |
| `6-index.html` | `<nav>` dans le header |
| `7-index.html` | `<section>` dans le main |
| `8-index.html` | `<article>` dans les sections |
| `9-index.html` | `<aside>` |
| `10-index.html` | Hiérarchie des titres `<h1>` → `<h3>` |
| `12-index.html` | `<p>` paragraphes dans les sections |
| `14-index.html` | `<span>` pour texte en ligne |
| `15-index.html` | `<div>` comme conteneurs |
| `16-index.html` | `<ul>` et `<li>` pour la navigation |
| `17-index.html` | `<nav>` avec liste de liens |
| `18-index.html` | `<a>` liens dans la nav |
| `20-index.html` | `<a>` liens dans les sections |
| `21-index.html` | Logos et liens vers la home |
| `22-index.html` | `<img>` dans les articles |
| `27-index.html` | Page complète avec nav, sections, articles |
| `35-index.html` | Formulaires HTML |
| `36-index.html` | Tableau HTML |
