# Déployer sur GitHub Pages
Mettre votre site en ligne est un processus automatisé grâce à **GitHub Actions**. Une fois configuré, chaque modification de votre projet mettra à jour le site public.

## 1. Télécharger les fichiers sur GitHub

- **Créez un nouveau dépôt** sur votre compte GitHub.
- Sur la page du dépôt, cliquez sur **"Add file" > "Upload files"**.
- Faites glisser tous vos fichiers (`mkdocs.yml`, le dossier `docs`, etc.) dans la fenêtre.
- Validez en cliquant sur **"Commit changes"**.

## 2. Créer le workflow de déploiement

Le workflow est un fichier qui contient les instructions pour que GitHub construise et publie votre site.

- Dans votre dépôt, allez dans l'onglet **"Actions"** et cliquez sur **"set up a workflow yourself"**.
- Copiez le code ci-dessous et collez-le dans l'éditeur.

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
      build:
        runs-on: ubuntu-latest
        steps:
          - uses: actions/checkout@v4
          - uses: actions/setup-python@v5
            with:
              python-version: 3.x
          - run: pip install mkdocs-material pymdown-extensions
          - run: mkdocs build
          - uses: actions/upload-pages-artifact@v3
            with:
              path: './site'

      deploy:
        environment:
          name: github-pages
          url: ${{ steps.deployment.outputs.page_url }}
        runs-on: ubuntu-latest
        needs: build
        steps:
          - name: Deploy to GitHub Pages
            id: deployment
            uses: actions/deploy-pages@v4
```

- Validez le fichier en cliquant sur **"Commit changes"**.

## 3. Activer GitHub Pages

- Allez dans l'onglet **"Settings" > "Pages"** de votre dépôt.
- Dans la section "Build and deployment", sous "Source", sélectionnez **"GitHub Actions"**.
- L'action va se lancer. Une fois terminée, l'URL de votre site apparaîtra sur cette même page.
