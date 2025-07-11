# Grilles (Grids)

Les grilles permettent d'organiser le contenu en colonnes, ce qui est idéal pour les pages d'index.

## Grille de cartes (Card grid)

C'est la méthode la plus courante. Chaque élément est présenté dans une "carte" qui réagit au survol de la souris.

<div class="grid cards" markdown>

-   :material-clock-fast:{ .lg .middle } __Installation Rapide__

    ---

    Installez le thème et soyez opérationnel en quelques minutes.

    [:octicons-arrow-right-24: Voir le guide d'installation](../guide/installation.md)

-   :fontawesome-brands-markdown:{ .lg .middle } __Juste du Markdown__

    ---

    Concentrez-vous sur le contenu et générez un site statique moderne et responsive.

    [:octicons-arrow-right-24: Voir les fonctionnalités](./admonitions.md)

</div>

## Grille générique

Vous pouvez aussi organiser des éléments plus complexes, comme des blocs de code ou des onglets, dans une grille.

<div class="grid" markdown>

!!! note "Note importante"

    Les grilles sont responsives. Sur mobile, les éléments s'afficheront les uns en dessous des autres.

```python title="Exemple de code"
# Ce bloc de code fait partie de la grille
print("Hello, Grid!")
```
</div>

## Grille avec des onglets

<div class="grid" markdown>

=== "Onglet 1 : Python"

    ```python
    # Cet onglet est dans une grille
    print("Hello, Tab 1!")
    ```

=== "Onglet 2 : JavaScript"

    ```javascript
    // Cet onglet est aussi dans la grille
    console.log("Hello, Tab 2!");
    ```

</div>

## Grille avec exemples combinés

<div class="grid" markdown>

=== "Unordered list"

    * Sed sagittis eleifend rutrum
    * Donec vitae suscipit est
    * Nulla tempor lobortis orci

=== "Ordered list"

    1. Sed sagittis eleifend rutrum
    2. Donec vitae suscipit est
    3. Nulla tempor lobortis orci

``` title="Content tabs"
=== "Unordered list"

    * Sed sagittis eleifend rutrum
    * Donec vitae suscipit est
    * Nulla tempor lobortis orci

=== "Ordered list"

    1. Sed sagittis eleifend rutrum
    2. Donec vitae suscipit est
    3. Nulla tempor lobortis orci
```

</div>
