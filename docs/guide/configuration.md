# Configuration du projet

Le cœur de votre site MkDocs est le fichier `mkdocs.yml`. C'est ici que vous définissez l'apparence, la structure et les fonctionnalités de votre documentation.

## Paramètres principaux

Voici quelques-uns des paramètres les plus importants que nous utilisons dans ce projet :

```yaml
# Le nom qui apparaît en haut à gauche du site
site_name: Projet de Démo MkDocs

# Le thème utilisé (Material est le plus populaire)
theme:
  name: material
  language: fr # Traduit les éléments comme "Rechercher" en français

# La structure de votre menu de navigation
nav:
  - 'Accueil': index.md
  - 'Guide de démarrage':
    - 'Installation': guide/installation.md
    - 'Configuration': guide/configuration.md
```

Activer des fonctionnalités
Le thème Material est rempli de fonctionnalités que vous pouvez activer simplement en les ajoutant sous la clé features.

Par exemple, pour ajouter des onglets de navigation et un bouton pour copier le code :

```yaml

theme:
  name: material
  features:
    - navigation.tabs
    - content.code.copy
```

Étendre Markdown avec des extensions
Pour rendre votre contenu plus riche (comme les admonitions ou les diagrammes), vous utilisez des markdown_extensions.

!!! tip "Astuce"
La configuration la plus importante pour les diagrammes Mermaid est pymdownx.superfences. Elle permet à MkDocs de reconnaître les blocs de code mermaid et de les traiter correctement.

```yaml
markdown_extensions:
  - admonition
  - pymdownx.superfences:
      custom_fences:
        - name: mermaid
          class: mermaid
          format: !!python/name:pymdownx.superfences.fence_code_format
```
