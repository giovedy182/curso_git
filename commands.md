# Iniciar git, en la ruta actual:
git init
# Ver si hay archivos nuevos en el fs:
git status
# Agregar archivos al git:
git add commands.md
# Eliminar el archivo del git:
git rm --cached commands.md
# Enviar el archivo al repositorio del git:
git commit -m "Este es el primer commit"
# Ver la configuracion del git:
git config --list
# Ver donde estan las configuracion guardadas del git:
git config --list --show-origin
# Agregar el name y email a la confuguracion del git:
git config --global user.name "Giovedy Marmolejo"
git config --global user.email "giovedy.182@gmail.com"
