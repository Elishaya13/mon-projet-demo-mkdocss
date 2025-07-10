# Annotations

## Annotation de code

Les annotations permettent d'ajouter des notes sur des lignes de code spécifiques, qui apparaissent lorsque l'on clique sur le numéro correspondant.

```python title="Exemple avec de code avec annotations"
class Connexion:
  def __init__(self, host, port):
    self.host = host # (1)
    self.port = port
    self.connect()

  def connect(self):
    print(f"Connexion à {self.host}:{self.port}...") # (2)

  def disconnect(self):
    pass # (3)
```

1. Le constructeur de la classe initialise les attributs de l'instance.
2. Cette méthode simule une connexion au serveur. La f-string permet de formater la chaîne de caractères avec les variables `host` et `port`.
3. La commande `pass` est une instruction qui ne fait rien. Elle est utilisée ici comme un placeholder pour une future implémentation.

## Annotation dans un Onglet

Il est également possible de combiner ces fonctionnalités pour des cas d'usage plus complexes.

=== "Tab 1"

    Lorem ipsum dolor sit amet, (1) consectetur adipiscing elit.
    { .annotate }

    1.  :man_raising_hand: I'm an annotation!

=== "Tab 2"

    Phasellus posuere in sem ut cursus (1)
    { .annotate }

    1.  :woman_raising_hand: I'm an annotation as well!

## Annotation dans une admonition

!!! note annotate "Phasellus posuere in sem ut cursus (1)"

    Lorem ipsum dolor sit amet, (2) consectetur adipiscing elit. Nulla et
    euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo
    purus auctor massa, nec semper lorem quam in massa.

1.  :man_raising_hand: I'm an annotation!
2.  :woman_raising_hand: I'm an annotation as well!
