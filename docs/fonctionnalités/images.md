# Utilisation des images

Le thème Material for MkDocs offre de nombreuses options pour afficher et interagir avec les images.

## Image simple avec légende

Pour afficher une image, utilisez la syntaxe Markdown standard. Le texte entre guillemets deviendra la légende sous l'image.

![Une image placeholder](../assets/image.png "Ceci est la légende de l'image")

## Alignement des images

Vous pouvez aligner une image à gauche ou à droite pour que le texte s'enroule autour d'elle.

![Image alignée à gauche](../assets/demo_image.png){ align=left width="300" }

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor massa, nec semper lorem quam in massa. In Tincidunt et pugna et porttitor. Mauris ultrices, justo vitae conubia nostra.

<br clear="left" />

![Image alignée à droite](../assets/image.png){ align=right width="300" }

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor massa, nec semper lorem quam in massa. In Tincidunt et pugna et porttitor. Mauris ultrices, justo vitae conubia nostra.

<br clear="right" />

## Grille d'images

Vous pouvez afficher plusieurs images côte à côte en utilisant une grille.

!!! grid

    ![Image 1](../assets/demo_image.png "Première image")
    ![Image 2](../assets/image.png "Seconde image")

# Image depuis un lien externe

![Photo de pigeons s'envolant](https://images.pexels.com/photos/29236029/pexels-photo-29236029.jpeg "Légende optionnelle pour l'image")

## Avantages et inconvénients
Avantage : Vous n'avez pas besoin de stocker l'image dans votre projet, ce qui peut l'alléger.

Inconvénient : Votre site devient dépendant d'un serveur externe. Si le lien vers l'image est modifié ou supprimé, l'image disparaîtra de votre page.
