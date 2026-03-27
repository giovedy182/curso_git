# Comandos del Git
## Comandos utiles de GIT v.1 16/08/2024 #
* Ver la configuracion del git:
``` bash
git config --list
```
* Ver donde estan las configuracion guardadas del git:
```bash
git config --list --show-origin
```
* Agregar el name y email a la confuguracion del git:
    * name
    ```bash
    git config --global user.name "Giovedy Marmolejo"
    ```
    * email
    ```bash
    git config --global user.email "giovedy.182@gmail.com"
    ```
* Cambiar de master a main la rama principal
```bash
git config --global init.defaultBranch main
```
* Iniciar git, en la ruta actual:
```bash
git init
```
* Cambiar el nombre de Master a MAIN
```bash
git branch -m main
```
* Ver si hay archivos nuevos en el fs:
```bash
git status
```
* Agregar un archivos especifico al git:
```bash
git add commands.md
```
* Agregar todos los archivos de la carpeta al git:
```bash
git add .
```
* Eliminar el archivo del git, pero los mantiene en el disco duro
```bash
git rm --cached commands.md
```
* Eliminar el archivo del git, y tambien elimina del disco duro
```bash
git rm --force commands.md
```
* Enviar el archivo al repositorio del git con comantario:
```bash
git commit -m "Este es el primer commit"
```
* Enviar el archivo al repositorio del git sin comentario:
*Abre un VIM, pero para guardar es "SHIFT+z+z"*
```bash
git commit
```
* Ver los commits del archivo:
```bash
git log commands.md
```
* Ver los cambios del archivo:
```bash
git show commands.md
```
* Ver la diff de dos commtis diferentes:
```bash
git diff 75ba5f889a93c3d967f929bfa2ad60d25ad8318b 25bb18b3ccf92fcfeb6130a56c6be2c2bb1580fa
```
* Regresar a una version anterior, sin conciderar los archivos q estanen stage
```bash
git reset f273dcc4d123b53dbec46f3a614c45b4ac39514b --hard
```
* Regresar a una version anterior, conciderando los archivos q estanen stage
```bash
git reset f273dcc4d123b53dbec46f3a614c45b4ac39514b --soft
```
* Ver los commits especificaos en los archivos
```bash
git log --stat
```
* Para obtemer el archivo de un determinadon commit
```bash
git checkout 25bb18b3ccf92fcfeb6130a56c6be2c2bb1580fa commands.md
```
```bash
git checkout master commands.md
```
* Comando para hacer add y commit, pero esto solo funciona con archivos que hayan tenido add previamente.
```bash
git commit -am "Ingresar mensaje del commit"
```
* rear una nueva rama
```bash
git branch developer
```
* Moverse entre ramas
```bash
git checkout developer
```
* Listar los branch
```bash
git branch
```
* Hacer merge en el master, trayendo los cambios del developer
  *para hacer el marge los repos deben estar commiteados*
```bash
git merge developer
```
* Pasos para ssh-keys:
* Windows
```bash
ssh-keygen -t rsa -b 4096 -C "youremail@example.com"
```
* Comprobar proceso, agregarlo y listar
```bash
eval $(ssh-agent -s)
ssh-add ~/.ssh/id_rsa
ssh-add -l
```
* Agregar las configuraciones ssh
```bash
vim ~/.ssh/config
Host *
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/id_rsa
```
* Agregar al ssh-add
```bash
ssh-add -k ~/.ssh/id_rsa
```
 Listar los repos remotos (Github)
```bash
git remote
```
* Crear el repo remoto origin:
```bash
git remote add origin https://github.com/giovedy182/curso_git.git
```
* Lista los repos remotos con detalle:
```bash
git remote -v
```
```bash
origin  https://github.com/giovedy182/curso_git.git (fetch)
origin  https://github.com/giovedy182/curso_git.git (push)
```
* Hacer push al origin (Github) desde el repo local main:
    * Comando:
    ```bash
    git push origin main
    ```
    * *La primera vez sale este conflicto:*
    ```bash
     To https://github.com/giovedy182/curso_git.git
     ! [rejected]        main -> main (fetch first)
     error: failed to push some refs to 'https://github.com/giovedy182/curso_git.git'
     hint: Updates were rejected because the remote contains work that you do not
     hint: have locally. This is usually caused by another repository pushing to
     hint: the same ref. If you want to integrate the remote changes, use
     hint: 'git pull' before pushing again.
     hint: See the 'Note about fast-forwards' in 'git push --help' for details.
    ```
    * *Para correcgirlo ejecutar un pull:*
    ```bash
    git pull origin main
    ```
    * *Pero muestra este error:*
    ```bash
    remote: Enumerating objects: 3, done.
    remote: Counting objects: 100% (3/3), done.
    remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
    Unpacking objects: 100% (3/3), 886 bytes | 80.00 KiB/s, done.
    From https://github.com/giovedy182/curso_git
    * branch            main       -> FETCH_HEAD
    * [new branch]      main       -> origin/main
    fatal: refusing to merge unrelated histories
    ```
    * *Para corregir ejecutar el pull --allow-unrelated-histories*
    ```bash
    git pull origin main --allow-unrelated-histories
    ```
    *Deberia de mostrar este mensaje de ok:*
    ```bash
     From https://github.com/giovedy182/curso_git
      * branch            main       -> FETCH_HEAD
     Merge made by the 'ort' strategy.
      README.md | 2 ++
      1 file changed, 2 insertions(+)
      create mode 100644 README.md
    ```
* Ver el log mejorado:
```bash
git log --all --graph --decorate --oneline
```
* Alias en git
```bash
git config --global alias.logtree "log --all --graph --decorate --oneline"
```
```bash
git config --global alias.superlog "log --graph --abbrev-commit --decorate --date=relative --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(bold yellow)%d%C(reset)' --all"
```
* Usar un alias de git
```bash
git logtree
```
```bash
git superlog
```

