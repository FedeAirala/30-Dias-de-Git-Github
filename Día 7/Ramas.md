# Ramificaciones en Git

Una rama en Git es una bifurcación de la rama original de un proyecto, ya sea local o remoto. Esto permite mantener el proyecto sin modificaciones, mientras en la/las ramas creadas se va haciendo cambios, una vez realizado los mismos, agregados y cambiados en la rama bifurcada, se puede fusionar con la rama principal del proyecto para cometer los cambios realizados en la rama bifurcada.

#### Enumeración de las ramas del directorio

        ' git branch'

 * Enumera las ramas del directorio.


#### Creación de una rama

        'git branch "Nombre de la rama"'

* De esta manera se crea una bifuración de la rama en la que nos encontramos.

#### Cración de ramas remotas

* El comando git branch también funciona con ramas remotas. Para trabajar en ramas remotas, primero hay que configurar un repositorio remoto y añadirlo a la configuración del repositorio local.

        'git remote add "nombre_remoto" "url_remoto"'

### Operaciones comunes en ramas

      *  git branch: muestra información de las ramas.
      *  git branch "branch": crea una rama de nombre branch.
      *  git branch -d "branch": elimina la rama si no tiene cambios realizados por confirmar.
      * git branch -D "branch": elimina la rama aunque tenga modificaciones no confirmadas.
      * git branch -a: cambia el nombre de la rama actual branch.

### Moverse a una rama creada

        ' git checkout "nombre de la rama"

* 'git checkout -b "nombre de la rama": crea una nueva rama y se posiciona en ella.

### Procedimientos básicos para Ramificar y Fusionar



![alt text](https://git-scm.com/book/en/v2/images/basic-branching-1.png)

        'git checkout -b "Nombre de la rama"

Crea la nueva rama y se posiciona en ella, en este caso apuntaría a C2. Se realizan las modificaciones que deseamos.

        'git status'

Vemos que Git haya visto las modificaciones

        ' git add "Nombre del archivo modificado"

Se rastrea el archivo y se deja preparado para hacer el commit

        'git commit -m "Modificación realizada"

Se confirma la modificación

        ' git checkout master'

Nos posicionamos en la rama a la que queremos enviar los cambios (estos también pueden ser a otras ramas, pero no es lo habitual).

        ' git merge'

Si no hay conflictos, se fusiona el cambio en la rama master, en el caso de haberlos se deben guardar primero los cambios en la rama donde se hizo la modificación y luego realizar los pasos para fusionar.
