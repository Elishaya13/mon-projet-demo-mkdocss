# Déployer sur GitHub Pages
Mettre votre site en ligne est un processus automatisé grâce à **GitHub Actions**. Une fois configuré, chaque modification de votre projet mettra à jour le site public.
Il existe deux méthodes principales pour déployer un site MkDocs sur GitHub Pages.

1.  **Méthode standard** : Idéale pour les sites simples, sans gestion de versions.
2.  **Méthode avec `mike`** : Parfaite pour les projets qui nécessitent de gérer plusieurs versions de la documentation (ex: `1.0.0`, `1.1.0`, etc.).

---
## Méthode 1 : Déploiement Standard (sans versions)

Cette méthode publie la dernière version de votre branche `main` sur le site.

### 1. Configuration de `mkdocs.yml`

Assurez-vous que votre fichier `mkdocs.yml` est correctement configuré, sans mention de `mike`.

### 2. Création du workflow

Créez un fichier dans `.github/workflows/deploy.yml` avec le contenu suivant :

```yaml
name: Deploy MkDocs site to GitHub Pages

on:
  push:
    branches: ["main"] # ou "master"
  workflow_dispatch:

permissions:
  contents: read
  pages: write
  id-token: write

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-python@v5
        with:
          python-version: 3.x
      - name: Install dependencies
        run: pip install mkdocs-material pymdown-extensions # Ajoutez vos autres plugins ici
      - name: Build with MkDocs
        run: mkdocs build
      - name: Upload artifact
        uses: actions/upload-pages-artifact@v3
        with:
          path: './site'
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4
```

- Validez le fichier en cliquant sur **"Commit changes"**.

### 3. Activer GitHub Pages

- Allez dans l'onglet **"Settings" > "Pages"** de votre dépôt.
- Dans la section "Build and deployment", sous "Source", sélectionnez **"GitHub Actions"**.
- L'action va se lancer. Une fois terminée, l'URL de votre site apparaîtra sur cette même page.

## Méthode 2 : Déploiement avec `mike` (avec versions)

Cette méthode est celle que nous utilisons actuellement. Elle permet de publier des versions spécifiques de votre documentation.

### 1. Configuration de `mkdocs.yml`

Votre fichier `mkdocs.yml` doit inclure le plugin `mike` et la configuration `extra` correspondante :

```yaml
plugins:
  - search
  - mike

extra:
  version:
    provider: mike
```
### 2. Création du workflow

Créez un fichier dans `.github/workflows/deploy.yml` avec le contenu suivant :

```yaml
name: Deploy MkDocs site with Mike

on:
  workflow_dispatch: # Déclenchement manuel

permissions:
  contents: write

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-python@v5
        with:
          python-version: 3.x
      - name: Install dependencies
        run: pip install mkdocs-material mike # Ajoutez vos autres plugins ici
      - name: Configure Git author
        run: |
          git config user.name "${{ github.actor }}"
          git config user.email "${{ github.actor_id }}+${{ github.actor }}@users.noreply.github.com"
      - name: Deploy with Mike
        run: mike deploy 1.0.0 latest --push --update-aliases
```
### 3. Activation de GitHub Pages
Allez dans **"Settings" > "Pages"** de votre dépôt.

Sous "Build and deployment", pour "Source", sélectionnez **"Deploy from a branch"**.

Choisissez la branche `gh-pages` et le dossier `/ (root)`.
