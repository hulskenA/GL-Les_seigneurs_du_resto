### Récape commandes `GIT`

+ `git status` => voir la liste des fichiers et commits différents entre le repo local et le repo distant
+ `git add <fileName>` => ajout/indexation du fichier `<fileName>`
+ `git commit -m "type(where): what"` => nomination du/des changement(s) ajoutés précédemments (example en Karma commit)
+ `git merge <branchName>` => fusionne la branche actuelle avec la branche `<branchName>`
+ `git push` => ajouts des différents commits sur le repo distant
+ `git pull <branchName>` => merge la branche git distante `<branchName>` avec la branche locale (Si ce paramètre n'est pas précisé cela se fera sur la branche actuelle)
+ `git fetch && git rebase` => applique les différents commits du repo distant sur le repo local
+ `git checkout <fileName>` => supprime les modifications non indexés de `<fileName>`
+ `git branch` => liste toutes les branches du repo locales
+ `git branch -d <branchName>` => supprime la branche `<branchName>`
+ `git checkout <branchName>` => se déplace sur la branche `<branchName>` locale
+ `git checkout -b <branchName>` => crée une nouvelle branch `<branchName>` et se déplace dessus

***A vérifier:***
+ `git reset HEAD` => supprime les modifications non indexé
+ `git reset ~HEAD` => supprime le derniers commit local
