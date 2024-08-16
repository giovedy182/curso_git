# Ver la configuracion del git:
git config --list
# Ver donde estan las configuracion guardadas del git:
git config --list --show-origin
# Agregar el name y email a la confuguracion del git:
git config --global user.name "Giovedy Marmolejo"
git config --global user.email "giovedy.182@gmail.com"
# Iniciar git, en la ruta actual:
git init
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
# Hacer merge al master desde el master, trayendo los cambios del developer
git merge developer