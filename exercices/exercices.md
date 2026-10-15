# Énoncés d'exercices


## 1. Les éléments de base

Créer une première page de présentation à propos de vous.
Vous devrez décrire : 
- Informations personnelles (h2)
- Vos hobbies (h2)
- La liste de vos films / séries préférées (h2)
  - Séries (h3)
  - Films (h3)

## 2. Les tableaux

Créer une page `exo_02.html` contenant deux tableaux, ainsi qu'une feuille de style `exo_02.css` reliée à la page.

### Partie A : Bon de commande (structure d'un tableau)

Reproduire le bon de commande suivant :

| Réf. | Produit           | Quantité | Prix unitaire | Total    |
| ---- | ----------------- | -------- | ------------- | -------- |
| R001 | Clavier mécanique | 2        | 79,90 €       | 159,80 € |
| R002 | Souris sans fil   | 1        | 29,99 €       | 29,99 €  |
| R003 | Écran 27 pouces   | 2        | 249,00 €      | 498,00 € |
| R004 | Câble HDMI        | 3        | 9,50 €        | 28,50 €  |
| Total de la commande |  |  |              | 716,29 € |

Contraintes :
- Le tableau a une légende (`caption`) : « Bon de commande n°2026-042 »
- Le tableau est découpé en trois parties : `thead`, `tbody` et `tfoot`
- Les en-têtes de colonnes sont des `th` avec l'attribut `scope="col"`
- La référence de chaque produit (R001, R002…) est un `th` avec l'attribut `scope="row"`
- Dans le pied du tableau, la cellule « Total de la commande » s'étend sur 4 colonnes

### Partie B : Horaire de la semaine (fusion de cellules)

Reproduire l'horaire de la semaine 3 de la formation :

```
+-----------------------------------------------------------------------------+
|                    Semaine 3 — du 12 au 16 octobre                          |
+------------+-------------+------------+------------+------------+-----------+
|            | Lundi 12    | Mardi 13   | Mercredi 14| Jeudi 15   | Vendredi 16|
+------------+-------------+------------+------------+------------+-----------+
| Matin      | Positionne- |            |            | Responsive |           |
|            | ment        |    Self    |    Self    | et HTML    |   Self    |
+------------+-------------+   study    |   study    | avancé     |   study   |
| Après-midi | Flexbox     |            |            +------------+           |
|            |             |            |            | Coaching   |           |
+------------+-------------+------------+------------+------------+-----------+
```

Contraintes :
- Le titre « Semaine 3 — du 12 au 16 octobre » est dans le `thead` et s'étend sur toute la largeur du tableau
- La ligne des jours est aussi dans le `thead`, avec des `th` et l'attribut `scope="col"`
- « Matin » et « Après-midi » sont des `th` avec l'attribut `scope="row"`
- Les journées de self study occupent le matin **et** l'après-midi (une seule cellule par journée)
- Chaque jour de cours avec Quentin a une cellule différente le matin et l'après-midi

Astuce : avant d'écrire le code, comptez le nombre de cellules de chaque ligne. Une cellule fusionnée vers le bas « prend la place » d'une cellule dans la ligne suivante.

### Partie C : Mise en forme (CSS)

Dans `exo_02.css` :
- Fusionner les bordures des cellules (`border-collapse`)
- Ajouter une bordure de 1px à toutes les cellules (`th` et `td`) et un espacement intérieur (`padding`)
- Donner une couleur de fond aux en-têtes (`thead`)
- Placer la légende du bon de commande sous le tableau (`caption-side`)
- Aligner à droite les colonnes de prix et de quantité, à l'aide d'une classe
- Donner une couleur de fond différente aux cellules « Self study » et « Coaching », à l'aide de deux classes

### Bonus

- Vérifier votre page avec le validateur du W3C : https://validator.w3.org/#validate_by_input
- Ajouter une ligne « TVA (21 %) » et une ligne « Total TVAC » dans le pied du bon de commande


## 3. Menu de navigation et carte du café

Créer le dossier `exo03` avec une page `index.html` et un dossier `css` contenant `style.css` et `variables.css`.

### Partie A : Structure HTML

La page du café "Le Grain" contient :
- Un menu de navigation avec 5 liens : Accueil, Carte, Événements, Galerie, Contact. Le lien "Carte" a la classe `actif` (c'est la page en cours)
- Un titre `h1` et un paragraphe d'introduction
- Un tableau "Nos boissons" avec une légende et 3 colonnes : Boisson, Taille, Prix (au moins 6 boissons)

Les prix sont écrits **sans** le symbole € dans le HTML : `<td class="prix">2.50</td>`

### Partie B : Le menu (CSS)

- Les couleurs et la police sont définies dans `variables.css` (`:root`), importé dans `style.css` avec `@import`
- Le menu est horizontal (`display: flex` sur le `ul`), sans puces, avec un espace entre les liens (gap)
- Les liens sont en majuscules, sans soulignement, avec une marge intérieure en `em`
- **Au survol** (`:hover`) : le lien change de couleur de fond et de couleur de texte
- **Au clic** (`:active`) : le lien prend une troisième couleur
- **Au focus** (`:focus`) : le lien a un contour visible
- Le lien `.actif` est souligné par une bordure en bas et précédé d'un " ▸ " ajouté en CSS (`::before`)
- Le dernier lien "Contact" ressemble à un bouton, avec une bordure (`:last-child`)

### Partie C : La carte (CSS)

- Une ligne sur deux du `tbody` a une couleur de fond (`nth-child`)
- La ligne survolée change de couleur (`tr:hover`)
- Le symbole "€" est ajouté après chaque prix en CSS (`::after`)
- Le tableau fait 80 % de la largeur de la page (en centré )

Contraintes sur les unités :
- Toutes les tailles de texte sont en `rem`
- Les couleurs utilisent au moins 3 notations différentes (nom, hexadécimal, `rgb()`/`rgba()` ou `hsl()`)

### Bonus

- La première lettre du paragraphe d'introduction est une lettrine (`::first-letter`)
- Ajouter un thème sombre automatique avec `@media (prefers-color-scheme: dark)`
- Utiliser une police téléchargée avec `@font-face`

Lien vers le Google Fonts : <https://fonts.google.com/>


## 4. Formulaire d'inscription avec icônes

La salle d'escalade "Le Bloc" veut un formulaire d'inscription en ligne. Chaque champ affiche une petite icône à l'intérieur de la zone de saisie, à gauche du texte.

Créez un dossier `exo04` avec une page `index.html` et un fichier `css/style.css`.

### Partie A : le HTML

- Un titre `h1` "Inscription" et un court paragraphe d'introduction
- Un formulaire avec les champs suivants, chacun avec son `label` :
  - Prénom et Nom (deux champs texte)
  - E-mail
  - Téléphone
  - Date de naissance
  - Niveau (liste déroulante : Débutant, Intermédiaire, Confirmé)
  - Un message libre (zone de texte, sans icône)
- Un bouton "S'inscrire"
- Chaque champ avec icône est regroupé avec son icône dans un même conteneur
- L'icône est un simple caractère dans un `span` (`@` pour l'e-mail, `#` pour le téléphone...), ou une petite image de 16px

### Partie B : les icônes dans les champs

- L'icône est placée **à l'intérieur** du champ, à gauche, grâce au couple `position: relative` / `position: absolute`
- L'icône est centrée verticalement dans le champ
- Le texte saisi ne passe pas sous l'icône
- Les champs prennent toute la largeur du formulaire, sans déborder

### Partie C : la mise en page

- Le formulaire fait 500px de large maximum et est centré dans la page
- Les champs Prénom et Nom sont côte à côte, sur une même ligne, et se partagent la largeur à parts égales
- Les `label` sont au-dessus des champs
- Le bouton "S'inscrire" est aligné à droite du formulaire
- Un lien "Besoin d'aide ?" reste visible en bas à droite de l'écran, même quand on fait défiler la page

### Bonus

- L'icône change de couleur quand son champ a le focus
- Une deuxième icône, à droite du champ e-mail, affiche un "✓" vert quand l'adresse est valide (pensez aux pseudo-classes de formulaire)
- Sur le formulaire, les champs Téléphone et Date de naissance sont eux aussi côte à côte

---

## 5. Mise en page d'un jeu de cartes

Vous devez mettre en page l'écran d'un jeu de cartes en ligne. Le HTML est fourni : **vous ne le modifiez pas** (sauf pour le bonus), tout se fait en CSS.

Créez un dossier `exo05` avec une page `index.html` contenant le code ci-dessous, et un fichier `css/style.css`.

```html
<!doctype html>
<html lang="fr">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Jeu de cartes</title>
    <link rel="stylesheet" href="css/style.css" />
  </head>
  <body>
    <div class="jeu">
      <header class="entete">
        <h1>La Bataille</h1>
        <p class="score">Score : 12</p>
      </header>

      <aside class="pioche">
        <h2>Pioche</h2>
        <div class="carte dos"></div>
      </aside>

      <main class="plateau">
        <h2>Votre main</h2>
        <div class="main-joueur">
          <div class="carte rouge">
            <span class="coin haut">A ♥</span>
            <span class="symbole">♥</span>
            <span class="coin bas">A ♥</span>
          </div>
          <div class="carte noire">
            <span class="coin haut">7 ♠</span>
            <span class="symbole">♠</span>
            <span class="coin bas">7 ♠</span>
          </div>
          <div class="carte rouge selectionnee">
            <span class="coin haut">R ♦</span>
            <span class="symbole">♦</span>
            <span class="coin bas">R ♦</span>
          </div>
          <div class="carte noire">
            <span class="coin haut">10 ♣</span>
            <span class="symbole">♣</span>
            <span class="coin bas">10 ♣</span>
          </div>
          <div class="carte rouge">
            <span class="coin haut">D ♥</span>
            <span class="symbole">♥</span>
            <span class="coin bas">D ♥</span>
          </div>
        </div>
      </main>

      <footer class="actions">
        <button>Piocher</button>
        <button>Jouer la carte</button>
      </footer>
    </div>
  </body>
</html>
```

### Partie A : la mise en page générale (Grid)

- `.jeu` est une grille avec `grid-template-areas` :
  - l'en-tête sur toute la largeur en haut
  - la pioche à gauche (200px de large) et le plateau à droite (le reste)
  - les actions sur toute la largeur en bas
- Dans l'en-tête, le titre est à gauche et le score à droite, alignés verticalement
- Les boutons des actions sont centrés et espacés

### Partie B : une carte

- Une carte mesure 100px de large sur 140px de haut, avec un fond blanc et une bordure
- Les cartes `.rouge` ont leur texte en rouge, les cartes `.noire` en noir
- Le grand symbole (`.symbole`) est centré horizontalement et verticalement dans la carte
- Les coins sont positionnés en `absolute` : `.haut` dans le coin supérieur gauche, `.bas` dans le coin inférieur droit
- La carte `.dos` (pioche) n'a pas de contenu : elle a seulement une couleur de fond unie qui la distingue des autres

### Partie C : la main du joueur

- Les cartes de la main sont côte à côte, avec un espace entre elles
- Si la fenêtre est trop étroite, les cartes passent à la ligne
- Les cartes gardent toujours leur largeur de 100px, même quand la place manque
- La carte `.selectionnee` est décalée de 20px vers le haut **sans faire bouger les autres cartes**, et a une bordure plus épaisse

### Bonus

- Au survol, une carte de la main monte légèrement
- L'en-tête reste visible en haut de l'écran quand on fait défiler la page
- La pioche ressemble à un paquet : ajoutez deux cartes `.dos` dans le HTML et superposez-les avec un léger décalage entre chacune


## 6. Le refuge "Les Pattes Libres"

Créer le site d'un refuge animalier, sur une seule page `index.html` avec une feuille de style `css/style.css`.

### Contenu de la page

1. **En-tête** : un logo en SVG et un menu (Accueil, Nos animaux, Adopter, Contact) avec des liens vers les sections de la page
2. **Accueil** : un titre, un paragraphe de présentation et une grande image
3. **Nos animaux** : 6 cartes (photo, nom, âge), chacune avec un attribut `data-espece` ("chien" ou "chat")
4. **Une journée au refuge** : une vidéo
5. **Adopter** : un formulaire de demande d'adoption
6. **Pied de page** : l'adresse du refuge et un lien vers sa page Facebook

### Partie A : Responsive

- La balise `<meta name="viewport">` est présente
- Le CSS est écrit en **mobile first**, avec une media query `@media (min-width: 768px)`
- Le menu est **vertical sur mobile** et **horizontal sur ordinateur** (Flexbox)
- Les cartes sont sur **1 colonne sur mobile** et **3 colonnes sur ordinateur** (Grid)
- Aucune image ne dépasse de l'écran (`max-width: 100%`)

### Partie B : HTML avancé

- Le logo est un **SVG** dessiné par vous (une patte : un ovale et 4 petits cercles)
- Les cartes des chats et des chiens ont une couleur de bordure différente, grâce à un **sélecteur d'attribut** sur `data-espece`
- La vidéo a des contrôles, une image `poster` et un texte de secours
- Le formulaire contient :
  - nom et e-mail **obligatoires**
  - le choix de l'animal (liste déroulante)
  - une case "Recevoir la newsletter" **cochée par défaut**
  - un champ "Refuge" **désactivé**, contenant "Bruxelles"
- Le lien Facebook s'ouvre dans un **nouvel onglet**
- Les titres utilisent une police importée avec `@font-face`

### Ressources

- Photos : https://unsplash.com ou https://www.pexels.com/fr-fr/
- Vidéos : https://www.pexels.com/fr-fr/videos/ (choisissez la plus petite taille)
- Polices : https://fonts.google.com (bouton "Get font", puis "Download all")

### À déposer

- Le dossier du projet en `.zip`
- Deux captures d'écran : affichage ordinateur et affichage mobile (outils de développement, mode responsive)