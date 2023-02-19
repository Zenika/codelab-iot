# Codelab

site : https://zenika.github.io/codelab-iot/

## Préparation TP

Créer un nouveau [mockbin](https://mockbin.org/) avec tout les paramètres par défaut puis reporter l'url dans le fichier `_config.yml` dans les clés `endpoint.http`, *bien enlever le `s`* et `endpoint.https`.

## Dev

- Installer ruby en version 3.1.3, utiliser [asdf](https://asdf-vm.com/) si possible

- Installation des dépendances :
```shell
bundle install
```

- Lancement du serveur local :
```shell
bundle exec jekyll serve -t --incremental
```

- Aller sur http://127.0.0.1:4000/codelab-iot/
