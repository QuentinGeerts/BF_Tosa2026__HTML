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