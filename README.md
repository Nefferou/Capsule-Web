# TP – Capsule Web

## ➕ Étape 1 – Créer la structure du projet
1. Crée un dépôt GitHub et le cloner sur votre PC *(Rappel : `git clone <nom-du-projet>`)*
2. Dans ce dossier, ajoute :  
   - Un fichier `index.html`
   - Un dossier `css`
        - Un fichier `style.css` dans ce dossier  
   - Un dossier `images`
        - *Une image de ton choix*
3. Choisir un IDE pour faire votre travail (Visual Studio, IntelliJ etc...)

### Arborescence attendue
``` bash
nom-du-projet/        ← dossier du projet (cloné depuis GitHub)
│
├── index.html        ← fichier principal (point d’entrée du site)
│
├── css/              ← dossier contenant les styles
│   └── style.css     ← fichier CSS externe
│
└── images/           ← dossier contenant les images
    └── exemple.png   ← ton image de test (nom au choix)
```

---

## 🏗️ Étape 2 – Structure HTML de base
Chaque page HTML commence avec une déclaration `<!DOCTYPE html>` puis une structure en `<html>`, `<head>` et `<body>`. Le `<head>` contient les informations techniques, le `<body>` le contenu visible.
 
> ℹ️ La structure d'une page HTML se compose de 4 balises de base :
> - La balise déclarative `<!DOCTYPE html>`
> - La balise racine `<html>`
> - La balise de paramétrage `<head>` (dans `<html>`)
> - La balise de corps du site `<body>` (dans `<html>`)

Un fichier HTML est toujours enregistré avec l’extension `.html`.

Dans `index.html` :  
```html
<!DOCTYPE html>
<html lang="fr">

<head>
    <meta charset="UTF-8">
    <title>Mon premier site</title>
</head>

<body>
    <header>
        <h1>Bienvenue sur mon site</h1>
        <nav>
            <!-- A faire plus tard -->
        </nav>
    </header>

    <main>
        <section>
            <h2>Introduction</h2>
            <p>Ceci est un paragraphe avec du <strong>gras</strong> et de <em>l’italique</em>.</p>
            <p>Un lien vers <a href="">Mon projet GitHub</a></p> <!-- Mettre le lien de votre projet GitHub -->
            <p>Une image : <img src="" alt=""></p> <!-- Mettre le chemin vers votre image -->
        </section>
    </main>

    <footer>
        <p>Prénom Nom - Mon premier site</p>
    </footer>
</body>

</html>
```

Maintenant allez voir le resultat par vous même en ouvrant votre fichier `index.html` sur votre navigateur

---

## ✨ Étape 3 – Relier le CSS
Ici on demande au fichier HTML d’aller chercher un fichier externe `style.css` pour appliquer les couleurs et les mises en forme.
> ⚠️ Le fichier `style.css` doit se trouver dans le dossier `css/`, sinon le chemin ne fonctionnera pas.

Dans `index.html`, dans la balise `<head>` ajouter :
```html
<link rel="stylesheet" href="css/style.css">
``` 

Puis dans `css/style.css` faites votre premier style : 
```css
/* Style global */
body {
  font-family: Arial, sans-serif; /* Police d'écriture */
  background: rgb(255, 255, 255); /* Couleur du fond */
  color: rgb(0, 0, 0); /* Couleur du texte */
  margin: 0; /* Espace extérieur */
  padding: 0; /*Espace intérieur */
}

/* Couleur du lien */
a { 
    color:rgb(255, 255, 255); 
}
```

> ℹ️ Pour d&finir une couleur, 3 formats s'offre à vous :
> - Nom de couleur `color: red;`
> - RGB `color: rgb(255, 0, 0);`
> - Hexadecimal `color: #ff0000;`

Maintenant allez voir le résultat avec votre style personnalisé

---

## 🧪 Étape 4 – Tester quelques propriétés utiles
Essayez de changer la couleur, la taille de police (`font-size`), ou le fond (`background-color`).  
```css
h1 {
    color:rgb(255, 255, 255);
    text-align: center;
}

p {
    margin-bottom: 1rem; /* On ajoute un espace en bas de chaque paragraphe */
}

img {
    width: 200px;
    border: 2px solid rgb(255, 255, 255); /* Taille ; Type ; Couleur de la bordure */
}
```
> [Lien pour plus de balises HTML](https://facemweb.com/blog/creation-site/liste-balises-html/)  
> [Lien pour plus de paramètres CSS](https://developer.mozilla.org/fr/docs/Web/CSS/Reference)

---

## 🧪 Étape 5 – Tester des sélecteurs
Ajoute dans ton HTML :  
```html
<p id="unique">Je suis un paragraphe unique avec un ID.</p>
<p class="exemple">Je suis un des paragraphes avec une classe.</p>
<p class="exemple">Je suis aussi un des paragraphes avec une classe.</p>
```

Et dans ton CSS :  
```css
#unique {
    color:rgb(255, 255, 255);
}

.exemple {
    color:rgb(255, 255, 255);
}
```

Avec `.exemple`, plusieurs paragraphes auront la même couleur.  
Avec `#unique`, seul celui qui a cet ID changera.

> ℹ️ Rappel : 
> - `p` : Sélectionne toutes les balises `<p>`
> - `#unique` : Sélectionne l'élément avec l'id "unique"
> - `.exemple` : Sélectionne tous les éléments avec la class "exemple"

---

## 🔳 Étape 6 – Découverte du Box Model (+ les espaces et bordures)
Le Box Model est fondamental : chaque élément HTML est comme une boîte avec un contenu, un padding (intérieur), une bordure, et une marge (extérieur).
Ajoute dans ton HTML :  
```html
<div class="box">Une boîte simple</div>
```

Et dans ton CSS :  
```css
.box {
  background:rgb(255, 255, 255);
  padding: 20px;     /* Espace intérieur */
  border: 3px solid #34d399;
  margin: 20px;      /* Espace extérieur */
}
```

Il y a 4 couches autour d’un élément : **contenu**, **padding**, **bordure** et **margin**.

> ℹ️ Quelques unités en CSS :
> - `px` : pixel (taille fixe)
> - `%` : pourcentage de l'élément père
> - `vw` : pourcentage de la largeur de la fenêtre
> - `vh` : pourcentage de la hauteur de la fenêtre

---

## 🪟 Étape 7 – Créer une Grid
Ajoute dans ton HTML :  
```html
<section id="mise-en-page">
    <h2>Mise en page avec Grid</h2>
    <div class="grid">
        <header class="zone">Header</header>
        <aside class="zone">Sidebar</aside>
        <main class="zone">Contenu</main>
        <footer class="zone">Footer</footer>
    </div>
</section>
```

Dans ton CSS :  
```css
.grid {
    display: grid; /* Type voulu */
    grid-template-columns: 1fr 4fr; /* Séparation en 2 colonnes de taille 1fr et 4fr */
    grid-template-rows: auto 1fr auto; /* Séparation en 3 lignes de taille auto, 1fr et auto */
    grid-template-areas: /* Définition des zones */
        "header header"
        "aside  main"
        "footer footer";
    gap: 10px; /* Espace entre chaque case de la Grid */
}

.zone {
    background:rgb(255, 255, 255);
    padding: 10px;
    border: 1px solid rgb(255, 255, 255);
}

/* Association des balises aux zones nommées précédemment */
.grid header {
    grid-area: header;
}

.grid aside {
    grid-area: aside;
}

.grid main {
    grid-area: main;
}

.grid footer {
    grid-area: footer;
}
```

Ici, la première colonne prend 1 fraction *(1fr)* et la deuxième 4 fractions *(4fr)*, donc la deuxième colonne sera 4 fois plus large que la première.

### Résultat attendu
```bash
+------------------------------------+
|              Header                |
+-----------+------------------------+
|  Sidebar  |        Content         |
+-----------+------------------------+
|              Footer                |
+------------------------------------+
```

---

## 🔗 Étape 8 – Tester le Positionnement
La propriété position permet de dire comment un élément est placé dans la page : normal, décalé, absolu, ou fixé à l’écran.

Ajoute dans ton HTML :  
```html
<div class="pos pos-static">Static</div>
<div class="pos pos-relative">Relative</div>
<div class="wrapper">
  <div class="pos pos-absolute">Absolute</div>
</div>
<div class="pos pos-fixed">Fixed</div>
```

Dans ton CSS :  
```css
/* Style global de cette partie */
.pos {
  background: #111827;
  color: #fff;
  padding: 10px;
  margin-bottom: 10px;
  border: 1px solid #374151;
}

/* Static = par défaut */
.pos-static { position: static; }

/* Relative */
.pos-relative {
  position: relative;
  top: 5px; /* Déplacement de 5px vers le bas */
  left: 5px; /* Déplacement de 5px vers la droite */
}

/* Absolute */
.wrapper { /* Boite parent */
  position: relative;
  height: 80px;
  border: 1px dashed rgb(255, 255, 255);
}
.pos-absolute { /* Element concerné */
  position: absolute;
  top: 10px; /* Placement à 10px du haut */
  right: 10px; /* Placement à 10px de la droite */
  background:rgb(255, 255, 255);
}

/* Fixed */
.pos-fixed {
  position: fixed;
  bottom: 10px; /* Placement en bas de l'écran */
  right: 10px; /* Placement à droite de l'écran */
  background:rgb(255, 255, 255);
}
```
> ⚠️ Un élément en absolute se place toujours par rapport à son parent le plus proche en relative.
---

## ✅ Étape 9 – Bonnes pratiques
- Toujours séparer HTML (contenu) et CSS (style).  
- Indenter correctement le code.  
- Nommer les classes CSS le plus clairement possible.  
- Utiliser des balises sémantiques (`<header>`, `<main>`, `<footer>`).  
- Ne pas mettre d’images sans attribut `alt`.  

---