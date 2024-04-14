# Cambiar nombre de archivos

Si quieres renombrar un archivo en Git, puedes ejecutar algo como

    'git mv README.md README'


Ejecutando y viendo el estado

    'git status'

On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

Nos aparece este mensaje porque Git no rastrea cambios de nombre de archivos, pero si lo ve.

# Historial de confirmaciones

El comando para ver todas las confirmaciones realizadas o las que se importaron con algún repositorio clonado utilizamos el comando log

    'git log'

 Ejemplo de un hitorial de confirmaciones de un repostirio clonado utilizando git log

     git log

     commit ca82a6dff817ec66f44342007202690a93763949
     Author: Scott Chacon <schacon@gee-mail.com>
     Date:   Mon Mar 17 21:52:11 2008 -0700

       changed the version number

     commit 085bb3bcb608e1e8451d4b2432f8ecbe6306e7e7
     Author: Scott Chacon <schacon@gee-mail.com>
     Date:   Sat Mar 15 16:40:33 2008 -0700

       removed unnecessary test

     commit a11bef06a3f659402fe7563abf99ad00de2209e6
     Author: Scott Chacon <schacon@gee-mail.com>
     Date:   Sat Mar 15 10:31:28 2008 -0700

    first commit

### Opciones útiles de git log --pretty=format lista algunas de las opciones más útiles aceptadas por format.

#### Tabla 1. Opciones útiles de git log --pretty=format
Opción	Descripción de la salida

    %H        Hash de la confirmación
    %h        Hash de la confirmación abreviado
    %T        Hash del árbol
    %t        Hash del árbol abreviado
    %P        Hashes de las confirmaciones padre
    %p        Hashes de las confirmaciones padre abreviados
    %an       Nombre del autor
    %ae       Dirección de correo del autor
    %ad       Fecha de autoría (el formato respeta la opción -–date)
    %ar       Fecha de autoría, relativa
    %cn       Nombre del confirmador
    %ce       Dirección de correo del confirmador
    %cd       Fecha de confirmación
    %cr       Fecha de confirmación, relativa
    %s        Asunto

El autor es la persona que escribió el trabajo, el commit es el que realizó algún cambio.

Las opciones oneline y format son especialmente útiles combinadas con otra opción llamada --graph. Ésta añade un pequeño gráfico ASCII mostrando tu historial de ramificaciones y uniones:

    git log --pretty=format:"%h %s" --graph
    * 2d3acf9 ignore errors from SIGCHLD on trap
    *  5e3ee11 Merge branch 'master' of git://github.com/dustin/grit
    |\
    | * 420eac9 Added a method for getting the current branch.
    * | 30e367c timeout code and tests
    * | 5a09431 add timeout protection to grit
    * | e1193f8 support for heads with slashes in them
    |/
    * d6016bc require time for xmlschema
    *  11d191e Merge branch 'defunkt' into local

Además de estas opciones git log tiene muchas otras opciones de filtrado y de maneras de mostrar los datos, si quieres saber más acerca de ellos puedes visitar la web oficial de Git y seguir la documentación.

# Deshacer cosas

### Deshacer cosas

En algunas ocaciones deseamos deshacernos de cosas que hayamos realizado. Para ello podemos utilizar varios comando, pero hay que tener cuidado de cómo utilizarlos ya que en algunos casos no vamos a poder recuperar lo que hayamos deshecho.

* Cuando realizamos algún cambio luego de haber confirmado o si queremos cambiar el mensaje del commit:

      ' git commit --amend'

### Deshacer un archivo preparado

Las siguientes dos secciones demuestran cómo lidiar con los cambios de tu área de preparación y tú directorio de trabajo.

    git add .
    git status
    On branch master
    Changes to be committed:
    (use "git reset HEAD <file>..." to unstage)

       renamed:    README.md -> README
       modified:   CONTRIBUTING.md

De lo anterior podemos notar que Git a visto un cambio de nombre de un archivo y la modificación de otro.

Justo debajo del texto “Changes to be committed” (“Cambios a ser confirmados”, en inglés), verás que dice que uses git reset HEAD <file>... para deshacer la preparación. Por lo tanto, usemos el consejo para deshacer la preparación del archivo CONTRIBUTING.md:

     git reset HEAD CONTRIBUTING.md
     Unstaged changes after reset:
     M   	CONTRIBUTING.md
     git status
     On branch master
     Changes to be committed:
     (use "git reset HEAD <file>..." to unstage)

        renamed:    README.md -> README

     Changes not staged for commit:
     (use "git add <file>..." to update what will be committed)
     (use "git checkout -- <file>..." to discard changes in working directory)

       modified:   CONTRIBUTING.md

### Deshacer un archivo modificado

En el caso de que hayamos hechoun cambio a un archivo y querramos restaurarlo git status nos dice como hacerlo en el siguiente ejemplo

     Changes not staged for commit:
     (use "git add <file>..." to update what will be committed)
     (use "git checkout -- <file>..." to discard changes in working  directory)

     modified:   CONTRIBUTING.md

Allí se te indica explícitamente como descartar los cambios que has hecho. Hagamos lo que nos dice:

    git checkout -- CONTRIBUTING.md
    git status
    On branch master
    Changes to be committed:
    (use "git reset HEAD <file>..." to unstage)

       renamed:    README.md -> README
       
Ahora puedes ver que los cambios se han revertido.

Importante
Es importante entender que git checkout -- [archivo] es un comando peligroso. Cualquier cambio que le hayas hecho a ese archivo desaparecerá - acabas de sobreescribirlo con otro archivo. Nunca utilices este comando a menos que estés absolutamente seguro de que ya no quieres el archivo.


