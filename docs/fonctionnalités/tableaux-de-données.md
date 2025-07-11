# Tableaux de données

Le thème Material for MkDocs transforme automatiquement les tableaux Markdown standards en tableaux de données interactifs avec des en-têtes triables.

## Exemple de tableau

La syntaxe utilise des barres verticales `|` pour séparer les colonnes et des tirets `-` pour délimiter l'en-tête.

| Centré          | Gauche          | Droite      |
|:---------------:|:--------------  |------------:|
| Contenu centré  | Aligné à gauche | 100,00 €    |
| `du code`       | *de l'italique* | **du gras** |
| Cellule 3       | Cellule 4       | 5,00 €      |

### Contenus alignés

Si vous souhaitez aligner une colonne spécifique sur `left`, `center` ou `right`, vous pouvez utiliser la syntaxe Markdown standard en plaçant des caractères `:` au début et/ou à la fin de la ligne de séparation.

=== "Gauche"

Le contenu est aligné à gauche
| Gauche         | Gauche          | Gauche      |
|:---------------|:--------------  |:------------|
| Contenu gauche | Aligné à gauche | 100,00 €    |
| `du code`      | *de l'italique* | **du gras** |
| Cellule 3      | Cellule 4       | 5,00 €      |

=== "Droite"

Le contenu est aligné à droite
| Droite          | Droite          | Droite      |
|----------------:|----------------:|------------:|
| Contenu droit   | Aligné à droite | 100,00 €    |
| `du code`       | *de l'italique* | **du gras** |
| Cellule 3       | Cellule 4       | 5,00 €      |

=== "Centre"

Le contenu est aligné au centre
| Centré          | Centré          | Centré      |
|:---------------:|:---------------:|:-----------:|
| Contenu centré  | Aligné au centre| 100,00 €    |
| `du code`       | *de l'italique* | **du gras** |
| Cellule 3       | Cellule 4       | 5,00 €      |
