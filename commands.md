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
# Eliminar el archivo del git:
git rm --cached commands.md
# Enviar el archivo al repositorio del git:
git commit -m "Este es el primer commit"
# Ver los commits del archivo:
git log commands.md
# Ver los cambios del archivo:
git show commands.md

