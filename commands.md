# Comandos utiles de GIT v.1 16/08/2024 #
## Giovedy
# Ver la configuracion del git:
git config --list
# Ver donde estan las configuracion guardadas del git:
git config --list --show-origin
# Agregar el name y email a la confuguracion del git:
git config --global user.name "Giovedy Marmolejo"
git config --global user.email "giovedy.182@gmail.com"
# Iniciar git, en la ruta actual:
git init
# Cambiar el nombre de Master a MAIN
git branch -m main
# Ver si hay archivos nuevos en el fs:
git status
# Agregar un archivos especifico al git:
git add commands.md
# Agregar todos los archivos de la carpeta al git:
git add .
# Eliminar el archivo del git, pero los mantiene en el disco duro
git rm --cached commands.md
# Eliminar el archivo del git, y tambien elimina del disco duro
git rm --force commands.md
# Enviar el archivo al repositorio del git con comantario:
git commit -m "Este es el primer commit"
# Enviar el archivo al repositorio del git sin comentario:
# Abre un VIM, pero para guardar es "SHIFT+z+z"
git commit 
# Ver los commits del archivo:
git log commands.md
# Ver los cambios del archivo:
git show commands.md
# Ver la diff de dos commtis diferentes:
git diff 75ba5f889a93c3d967f929bfa2ad60d25ad8318b 25bb18b3ccf92fcfeb6130a56c6be2c2bb1580fa
# Regresar a una version anterior, sin conciderar los archivos q estanen stage
git reset f273dcc4d123b53dbec46f3a614c45b4ac39514b --hard
# Regresar a una version anterior, conciderando los archivos q estanen stage
git reset f273dcc4d123b53dbec46f3a614c45b4ac39514b --soft
# Ver los commits especificaos en los archivos
git log --stat
# Para obtemer el archivo de un determinadon commit
git checkout 25bb18b3ccf92fcfeb6130a56c6be2c2bb1580fa commands.md
git checkout master commands.md
# Comando para hacer add y commit, pero esto solo funciona con archivos que hayan tenido add previamente.
git commit -am "Ingresar mensaje del commit"
# Crear una nueva rama
git branch developer
# Moverse entre ramas
git checkout developer
# Listar los branch
git branch
# Hacer merge en el master, trayendo los cambios del developer
# para hacer el marge los repos deben estar commiteados
git merge developer
# Pasos para ssh-keys:
# Windows
ssh-keygen -t rsa -b 4096 -C "youremail@example.com"
# Comprobar proceso, agregarlo y listar 
eval $(ssh-agent -s)
ssh-add ~/.ssh/id_rsa
ssh-add -l
# Agregar las configuraciones ssh
vim ~/.ssh/config
Host *
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/id_rsa
# Agregar al ssh-add
ssh-add -k ~/.ssh/id_rsa
# Listar los repos remotos (Github)
git remote
# Crear el repo remoto origin:
git remote add origin https://github.com/giovedy182/curso_git.git
# Lista los repos remotos con detalle:
git remote -v
origin  https://github.com/giovedy182/curso_git.git (fetch)
origin  https://github.com/giovedy182/curso_git.git (push)
# Hacer push al origin (Github) desde el repo local main:
git push origin main
### La primera vez sale este conflicto:
##### To https://github.com/giovedy182/curso_git.git
#####  ! [rejected]        main -> main (fetch first)
##### error: failed to push some refs to 'https://github.com/giovedy182/curso_git.git'
##### hint: Updates were rejected because the remote contains work that you do not
##### hint: have locally. This is usually caused by another repository pushing to
##### hint: the same ref. If you want to integrate the remote changes, use
##### hint: 'git pull' before pushing again.
##### hint: See the 'Note about fast-forwards' in 'git push --help' for details.
# Para correcgirlo ejecutar un pull:
git pull origin main
### Pero muestar este error:
##### remote: Enumerating objects: 3, done.
##### remote: Counting objects: 100% (3/3), done.
##### remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
##### Unpacking objects: 100% (3/3), 886 bytes | 80.00 KiB/s, done.
##### From https://github.com/giovedy182/curso_git
#####  * branch            main       -> FETCH_HEAD
#####  * [new branch]      main       -> origin/main
##### fatal: refusing to merge unrelated histories
# Para corregir ejecutar el pull --allow-unrelated-histories
git pull origin main --allow-unrelated-histories
# Deberia de mostrar este mensaje de ok:
##### From https://github.com/giovedy182/curso_git
#####  * branch            main       -> FETCH_HEAD
##### Merge made by the 'ort' strategy.
#####  README.md | 2 ++
#####  1 file changed, 2 insertions(+)
#####  create mode 100644 README.md
# Ver el log mejorado:
git log --all --graph --decorate --oneline
# Alias en git
git config --global alias.logtree "log --all --graph --decorate --oneline"
git config --global alias.superlog "log --graph --abbrev-commit --decorate --date=relative --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(bold yellow)%d%C(reset)' --all"
# Usar un alias de git
git logtree
git superlog
