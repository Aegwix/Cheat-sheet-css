# 🎨 Manipuler les polices en CSS

## 🎯 Propriétés de base pour les polices

| Propriété           | Rôle                                                  | Exemple                             |
|---------------------|--------------------------------------------------------|-------------------------------------|
| `font-family`       | Définit la police à utiliser                           | `font-family: 'Arial', sans-serif;` |
| `font-size`         | Taille du texte                                         | `font-size: 16px;`                  |
| `font-weight`       | Épaisseur (gras, normal, etc.)                         | `font-weight: bold;` ou `400`       |
| `font-style`        | Style de texte (normal, italique...)                   | `font-style: italic;`               |
| `line-height`       | Hauteur de ligne (espacement vertical entre les lignes) | `line-height: 1.5;`                |
| `letter-spacing`    | Espacement entre les lettres                           | `letter-spacing: 1px;`              |
| `text-transform`    | Met en majuscules, minuscules ou capitalise           | `text-transform: uppercase;`        |
| `text-align`        | Alignement du texte                                    | `text-align: center;`               |

---

## 🧪 Exemple de style CSS

```css  
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  font-size: 18px;
  font-weight: 400;
  font-style: normal;
  line-height: 1.6;
  letter-spacing: 0.5px;
  text-transform: none;
  text-align: justify;
```

## 🌐 Utiliser des polices extérieure 

### 1. Choisir une police
Rends-toi sur un site et choisis la police que tu veux utiliser.

### 2. Copier le lien d'importation
Google Fonts par exemple fournit une balise `<link>` à insérer dans la balise `<head>` de ton fichier HTML.

### 3. Coller le lien dans ton HTML
Ajoute le lien dans la section `<head>` de ton document pour importer la police.

### 4. Utiliser la police dans ton CSS
Déclare la police avec `font-family` dans ton fichier CSS.

<br>

# 🧩 Comprendre la notion de cascade en CSS

La **cascade** est le mécanisme utilisé par le navigateur pour déterminer **quelle règle CSS appliquer** lorsqu’il y a plusieurs règles en conflit.

## 📌 Trois principes de la cascade :

#### 1. **Spécificité**
Plus un sélecteur est précis, plus il a de poids.

- Exemple de poids :
  - `#id` → très spécifique
  - `.classe` → moyennement spécifique
  - `element` → peu spécifique

#### 2. **Ordre d’apparition**
Si deux règles ont la même spécificité, la dernière lue par le navigateur sera appliquée.

#### 3. **Importance**
La déclaration `!important` force l'application d'une règle, même si une autre est plus spécifique.

```css
  color: red !important;
```
<br>

# 🌱 Comprendre l'héritage en CSS

En CSS, certaines propriétés sont **automatiquement héritées** par les éléments enfants depuis leur parent.

## 🧬 Exemple de propriétés héritables :
- `color`
- `font-family`
- `font-size`
- `line-height`
- `text-align`
- `visibility`

## ❌ Non héritées par défaut :
Des propriétés comme `margin`, `padding`, `border`, `background`, etc., **ne sont pas héritées** automatiquement.

---

## ✅ Forcer l’héritage
On peut forcer un élément à hériter une propriété avec la valeur `inherit`.

```css
h2 {color: inherit;}
```

<br>

# 📦 Comprendre le fonctionnement de Flexbox

**Flexbox** est une méthode CSS pour organiser, aligner et distribuer les éléments dans un conteneur, même avec des tailles dynamiques.

## Principes de base :

- **`display: flex`** : Active Flexbox sur le conteneur.
- **`flex-direction`** : Définit la direction des éléments (`row`, `column`, `row-reverse`, `column-reverse`).
- **`justify-content`** : Aligne les éléments sur l'axe principal (horizontal par défaut) :
  - `flex-start`, `flex-end`, `center`, `space-between`, `space-around`, `space-evenly`.
- **`align-items`** : Aligne les éléments sur l'axe secondaire (vertical par défaut) :
  - `flex-start`, `flex-end`, `center`, `baseline`, `stretch`.
- **`flex-wrap`** : Permet de faire passer les éléments à la ligne :
  - `wrap` (les éléments passent à la ligne), `nowrap` (ils restent sur la même ligne).

## Propriétés des éléments enfants :

- **`flex-grow`** : Contrôle la capacité d’un élément à grandir pour remplir l’espace.
- **`flex-shrink`** : Contrôle la capacité d’un élément à rétrécir si nécessaire.
- **`flex-basis`** : Définit la taille initiale de l'élément avant toute répartition de l’espace.

## Raccourci :

- **`flex`** combine `flex-grow`, `flex-shrink` et `flex-basis` en une seule ligne.

---

## Résumé :
- Flexbox est utilisé pour disposer des éléments de façon flexible et adaptable.
- Utilise `display: flex` pour activer, `flex-direction` pour la disposition, et `justify-content` + `align-items` pour l'alignement des éléments.

<br>

# 📦 Comprendre CSS grid

## 🧱 1. Le concept de base
CSS Grid te permet de diviser un conteneur en lignes et colonnes (un peu comme un tableau) et de placer les éléments enfants (les "grid items") à l’intérieur de cette grille.
```CSS
<div class="grid-container">
  <div>1</div>
  <div>2</div>
  <div>3</div>
</div>
```
## 🎯 Utiliser CSS Grid

### 🧱 1. Activer la grille
```css
.container {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  gap: 10px;
} 
```

### 📐 2. Colonnes & Lignes
```CSS
grid-template-columns: 200px 1fr 2fr;
grid-template-rows: 100px auto 100px;
```

### 🧩 3. Positionner un élément
```CSS
.item1 {
  grid-column: 1 / 3; /* De la colonne 1 à 3 (occupe 2 colonnes) */
  grid-row: 1 / 2;
}
```

### 🔠 4. Zones nommées (grid-template-areas)
```Css
.container {
  display: grid;
  grid-template-areas:
    "header header"
    "sidebar main"
    "footer footer";
  grid-template-columns: 1fr 3fr;
}

.header  { grid-area: header; }
.sidebar { grid-area: sidebar; }
.main    { grid-area: main; }
.footer  { grid-area: footer; }
```

### 📱 5. Responsive automatique
```CSS
grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
```