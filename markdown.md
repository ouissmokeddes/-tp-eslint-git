# Etape 1 : Initialisation du projet et instaation d'ESLint

asma@asma-XPS-13-9305:~/Documents/tp-eslint-git$ git branch -a

-   origin
    -- incorrect. Normalement, on doit voir _ main ou _ master. Ici, la branche locale a été mal nommée origin, ce qui est réservé au dépôt distant. Cela peut entraîner des conflits ou des erreurs lors des pushs.

asma@asma-XPS-13-9305:~/Documents/tp-eslint-git$ git branch -m main
asma@asma-XPS-13-9305:~/Documents/tp-eslint-git$ git push -u origin main
...
asma@asma-XPS-13-9305:~/Documents/tp-eslint-git$ git branch

-   main
    -- Pour corriger l'erreur, j'ai d'abord renommé la branche locale avec git branch -m main, puis je l'ai poussée vers le dépôt distant avec git push -u origin main. Cela a permis d'établir un lien correct entre la branche locale main et la branche distante sur GitHub.

# ETAPE 2 : Test d’ESLint sur un fichier JavaScript

asma@asma-XPS-13-9305:~/Documents/tp-eslint-git$ npx eslint app.js

/home/asma/Documents/tp-eslint-git/app.js
7:7 error 'unusedVar' is assigned a value but never used no-unused-vars
19:7 error 'message' is assigned a value but never used no-unused-vars
21:5 error Unexpected constant condition no-constant-condition
25:7 error 'tableau' is assigned a value but never used no-unused-vars
32:10 error 'toutFaire' is defined but never used no-unused-vars
52:7 error 'd' is assigned a value but never used no-unused-vars
54:10 error 'fetchData' is defined but never used no-unused-vars
58:7 error 'nombres' is assigned a value but never used no-unused-vars
62:1 error Unexpected 'debugger' statement no-debugger

✖ 9 problems (9 errors, 0 warnings)

    -- Des erreurs sur le fichier app.js

asma@asma-XPS-13-9305:~/Documents/tp-eslint-git$ npx eslint app.js
asma@asma-XPS-13-9305:~/Documents/tp-eslint-git$
-- erreurs fixées en supprimants toutes les variables déclarées mais non utilisées

# ETAPE 3 : Intégration avec Git Hooks (Husky)

Pas d'erreurs

# ETAPE 4 : Configuration avancée d’ESLint

-- J’ai essayé d’ajouter des règles personnalisées dans le fichier eslint.config.mjs, mais je n’ai pas réussi à le faire fonctionner correctement à cause d’erreurs de parsing liées au type de module (commonjs vs module). Après plusieurs tentatives, j’ai gardé la configuration par défaut sans les règles avancées.

# ETAPE 5 : Mise en place de GitHub Actions

asma@asma-XPS-13-9305:~/Documents/tp-eslint-git$ git commit -m "Test 2 ajout non coforme"
husky - DEPRECATED

Please remove the following two lines from .husky/pre-commit:

#!/usr/bin/env sh
. "$(dirname -- "$0")/\_/husky.sh"

They WILL FAIL in v10.0.0

/home/asma/Documents/tp-eslint-git/utils.js
5:7 error 'age' is assigned a value but never used no-unused-vars

✖ 1 problem (1 error, 0 warnings)

husky - pre-commit script failed (code 1)
asma@asma-XPS-13-9305:~/Documents/tp-eslint-git$
-- commit bloqué
