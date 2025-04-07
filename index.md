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