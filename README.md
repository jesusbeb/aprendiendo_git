Aprendiendo comandos de git

----------- CONFIGURACIÓN INICIAL -------------------------------
git config --global user.name "jesusbeb"
configura git con este nombre de usuario

git config --global user.email jesusbelb@gmail.com
configura git con este correo electronico

git config --global core.editor "code --wait"
Este comando configura VS Code como editor de texto predeterminado. code --wait es para que la terminal se quede esperando hasta que cerremos VS code

git config --global -e
nos muestra nuestro archivo de configuracion global, que se abrira en VS code, si todo salio bien

git config --global core.autocrlf true
lleva true estando en S.O Windows

-----------------------------------------------------------------------------------------------

git config -h
nos muestra mas opciones de configuracion

ls
lista de archivos en la carpeta que estamos

ls -a
muestra directorios ocultos

pwd
muestra en que directorio estamos

cd ..
regresa al directorio anterior

tecla tab: autocompleta los comandos

mkdir nombre_de_carpeta
crea una carpeta

git init
se inicializa un repositorio dentro de git

code .
abre la carpeta en la que nos encontramos pero dentro del editor de codigo

git status
muestra el estado actual del repositorio

Untracked files: son los archivos que git no esta siguiendo, que no se han agregado

git add
seleccionar los archivos que se quieran pasar a la etapa stage (no necesariamente se veran reflejados en el repositorio, es una etapa intermedia)

git add archivo1.txt
agrega el archivo1.txt a la etapa de stage

git add .txt
agrega todos los archivos .txt

git add .
agrega todos los archivos que se encuentren en la carpeta o repositorio

git add archivo1.txt archivo2.txt
asi se agregan dos o mas archivos a la vez, separandalos por espacios

git commit -m "Descripcion del commit"
Hace un commit con una descripcion entre las comillas

git commit
Abre el editor de texto con un archivo donde nos indica detalles del archivo modificado. En la primer linea se pueda escribir el commit o comentario y se cierra la ventana de ese archivo

git restore --staged archivo1.txt
deshace el cambio de haber agregado a la etapa de stage, el archivo1.txt

rm archivo2.txt
Elimina el archivo2.txt

git rm archivo2.txt
Elimina el archivo2.txt y agrega ese cambio a la etapa de stage

git restore archivo2.txt
recupera un archivo eliminado

mv archivo.txt archivo1.txt
cambia el nombre del archivo.txt a archivo1.txt

git mv archivo1.txt archivo.txt
cambia nombre de archivo e inmediatamente hace un commit, para agregarle una descripcion se usa git commit -m "Descripcion"

Archivo .gitignore
se crea el archivo .gitignore sin extension, su contenido tendra agregados los archivos o carpetas que se deseen ignorar, este archivo tambien se tendra que agregar o hacer commit con "git add .gitignore"

git status -s
muestra informacion mas resumida
M 	roja, fue modificado y no se ha agregado al stage para despues hacer commit
M 	verde, fue modificado y ya se agrego al stage para hacer commit
?? 	no se ha agregado y git no le da seguimiento
AM	agregado pero se ha modificado

git diff
nos muestra todos los cambios dentro de los codigos de los archivos que estamos modificando y aun no hemos agregado al stage. Con la tecla q, salimos de este comando

git diff --staged
nos muestra los cambios que se han hecho en los codigos de los archivos y que ya se encuentran en la etapa de staged

git log
nos muestra el historial de todos los cambios

git log --oneline
nos muestra el historial mas corto. Salimos con la letra q

cat archivo2.txt
muestra el contenido de archivo2.txt


RAMAS

git branch
Nos dice en que rama estamos

git checkout -b ramab
crea una nueva rama llamada ramab y se cambia automaticamente a esa rama

git checkout main
cambia hacia la rama principal. Puede ser main o master

git merge ramab
trae los cambios de un archivo en la ramab a la rama en que estamos ubicados

git push
sube los cambios realizados a github

git checkout -b ramaC
se cambia de la rama principal a la ramaC

git push -u origin ramaC
crea una nueva rama en el repositorio


SINCRONIZAR CON GITHUB.COM

Creamos un nuevo repositorio:

Le agregamos un nombre, sin descripcion, sin un readme, sin gitignore y sin licencia.

En la siguiente ventana, en la parte de "…or create a new repository on the command line", copiamos la linea que empieza con: 
git remote add origin https://github.com/usuario/...
y la pegamos en la terminal de git
git remote --> indica que tenemos un servidor remoto donde se subiran los cambios
add origin --> indicamos de donde obtenemos el codigo
http:// --> le indicamos la url

despues regresamos a github.com y copiamos la linea de abajo
git push -u origin main
y pegamos en la terminal
este comando sirve para subir los cambios con respecto a la rama que estemos trabajando
-u --> crea la rama
origin --> donde sera creada
main --> como se llamara

Al haber presionado enter nos pedira nuestro nombre de usuario de github
Despues nos pedira un password, sin embargo este no es con el que entramos a nuestra cuenta de github, sera un token que se obtiene de la siguiente manera:
En gitgub nos vamos a Settings, Developer Settings, Personal Access tokens, Generate new token, le indicamos un nombre al token, tiempo de expiracion y los alcances que tendra el token (en este ejemplo se selecciono "repo" junto con todas sus opciones). Finalmente damos clic en Generate token, copiamos y pegamos en la terminal.

Asi se empezara a subir el repo a github

Para continuar agregando codigo simplemente lo vamos creando en el editor de codigo, vamos a la terminal escribimos "git add" para agregar los archivos, hacemos commit y finalmente escribimos:

git push
y asi se suben los cambios

SI ESTAMOS CREANDO UNA NUEVA RAMA PERO AUN NO QUEREMOS HACER MERGE CON MASTER PERO QUE SI ESTE EN EL REPOSITORIO
Nos cambiamos de rama con "git checkout -b Nombre_de_la_rama y escribimos
git push -u origin Nombre_de_la_rama

y esto creara dicha rama en el repositorio



https://www.youtube.com/watch?v=VdGzPZ31ts8&t=1073s
