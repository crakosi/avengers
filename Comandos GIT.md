# Comandos Git

## Inicializa el proyecto para el repositorio
git init

## Agrega todos los archivos a memoria
git add .

## Agrega los archivos modificados
git add -A

## Agrega todos los archivos modificados txt de todo el proyecto
git add "*.txt"

##A grega los achivos txt del directorio actual
git add *.txt

## Agrega todos los archivos
git add --all

## Agrega los archivos que enlistemos
git add archivo1.txt style.css ...

## Agrega todos los pdf dentro de la carpeta PDFs
git add pdfs/*.pdf

## Agrega los archivos al repositorio con un comentario
git commit -m "algun comentario"

## Recuperamos el ultio commit hecho.
git checkout -- .

## Muestra los archivos modificados/ En que rama estamos ubicados.
git status

##M uesta los archivos del stage
git status -s

##M uestra los archivos modificados y la rama(branch)
git status  -s -b
git status -sb

## Muestra los commit realizados
git log

## Excluye algun archivo que se agrego con el add
## Quita archivos de stage
git reset nombre_archivo.xml
git reset *.extension_archivo

## Posible error/warning que tienen:
git config core.autocrlf true

## Alias de comandos-- En esta caso el comando se llamara lg y ejecutara todo lo que este
## entre comilas
git config --global alias.lg "log --oneline --decorate --all --graph"

## Quedando como:
git lg

## Abre archvio global muestras las configuraciones realizadas:
git config --global -e

## Muestra las configuraciones globales realizadas:
git config --global -l

## Muestra los cambios realizados entre el ultimo commit y lo que tenemos:
git diff

## Muestra los archivos que estan en el stage y no estan en el commit:
git diff --stage

<!-- Un RESET es para reiniciar a una version anterior -->

## Quitar el archivo que esta en el stage y no queremos aun hacer commit:
git reset  HEAD nombre_archivo.exesion_archivo

## Para revertir los cambios de un solo archivo y ponerlo como en el head:
git checkout -- nombre_archivo

## Revertir los cambios de un archivo de un punto de la historia
 git checkout 55df4c2 nombre_archivo

## Modificar  mensajes de un commit anterior 
git commit --amend  -m "Mensaje nuevo"

## Reset del commit anterior al head  o a un ppunto de la historia :
git reset  --soft  HEAD^  
git reset --soft ea34sd

## Podemos movernos a un punto de la historia :
git reset --mixed  343e3ed


## Regrsamos a un punto de la historia y se eliminan los mayores a ese punto.:
git reset --hard 34f43

## Mostramos todos los log del historial:
git reflog

## Mostar el log de un archivo en particular
git log --follow -p nombre_archivo
** Tambien podemos ver esto con el alias
git lg  -- nombre_archivo

<!-- Archivos con git -->

## Renombramos un archivo con git:
git mv nombre_archivo_actual  nombre_archivo_nuevo

## Eliminar un archivo:
git rm nombre_archivo

## Actualizar el stage :
git -u

## Para ignorar archivo creamos un archivo extension .gitignore:
    Este archivo lo tenemos que subir 

<!-- Un BRANCh es una rama del proyecto  -->

## Para crear un rama:
git branch nombre_rama

#Para crear una rama y movernos al ella al mismo tiempo:
git checkout -b  nombre_rama

## Mostar las diferencias entre ramas:
git diff nombre_rama1 nombre_rama2

## Para movernos entre ramas:
git checkout nombre_rama

## Para unir los cambios de diferentes ramas:
git merge nombre_rama

## Para ver el listado de ramas:
git  branch

## Para eliminar una rama:
git branch  -d nombre_rama

## Para forzar el borrado en caso de algún error:
git branch -D test

 <!-- Un TAG es una version del proyecto -->

## Crear tags
git tag nombre_tag

## Ver todos los tags del repositorio
git tag 

## Borrar el tag
git tag -d nombre_tag

## Crear tag con descripcion
git tag -a nombre_tag -m "Descripcion del tag.."

## Crear un tag de un punto de la historia anterior 
git tag -a nombre_tag 3e344 -m "Descripcion del tag..."a

## Mostar la descripcion del tag
git show nombre_tag 

<!-- Un STASH es guardar los cambios que tienes en ese 
momento y regresar al ultimo comit -->

## Crear un stash
git stash

## Crear un stash con una descripcion
git stash save "Mensaje de descripcion ..."

## Mostar la lista de stash
git stash  list 

## Recumeramos los cambios del stash y se elimina
git stash pop

## Borrar el stash
git stash drop

## restaurar una entrada del stash en particular
git stash apply stash@{1}

## Mostar mas inofmracion del stash
git stash list  --stat
git sow stash 

## Mostar infromacion de un stash en particular
git show stash{1}

##Borrar todas las entradas de stash´s sin confirmacion
git stash clear

 <!-- Git REBASE sirve para poner una rama mas adelante de la version del master 
 el reabe se hace sobre la rama no en el master. Despues se pasa al master y se hace 
 un merge -->
## Estando en la rama a poner en rebase 
git rebase master

## Rebase interactivo 
git rebase -i HEAD~3

## Para unir commits con rebase squash
git  rebase -i HEAD~4  <----- Ultimos 4 commits

## Para modificar un commit
git rebase -i HEAD~1


## Revertit un archivo 
git checkout -- nombre_archivo

## Reverti commit manteniendo los cambios 
git reset  HEAD^

git rebase --continue


## Clonar un repositorio
git clone ruta_url nombre_carpeta

## Mostar el fetch y el push
git remote -v

<!-- Trabajando con FORKS -->


## Actualizar el fork. Mostar los cambios del repositorio original
git remote add upstream url_repositorio

## Bajar cambios del repositorio
git pull upstream master 

## Actualizar repositorio 
git push

## Sincroniar ramas con el repositorio 
git push  origin :nombre_rama

## Actualizar ramas con el repositorio 
git remote prune origin 

## Crear tags
 git tag -a V0.0.2 6923649 -m "VDescripcion del tag"

 ## Tag del master 
 git tag -a V1.0.0 -m "VDescripcion del tag

 ## Subir tags al repositorio 
 git push --tags

 ## Para subir un cambio haciendo referencia a un issue
git push commit  -am "Agregamos a ..  fixes #5"
git push commit  -am "Agregamos a ..  closes #5"



