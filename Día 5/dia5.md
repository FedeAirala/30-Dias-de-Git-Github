# Remotos

#### Trabajar con remotos

Esto consta de poder trabajar con repositorios que están en internet, ya sean propios o de terceros. Se pueden tener varios de ellos. Gestionar estos repositorios, que pueden ser de sólo lectura o lectura y escritura, significa que vamos a poder 

*  Leer datos de ellos.
*  Enviar datos cada vez que necesitemos compartir un trabajo.

Para gestionar repositorios debemos saber como

* Añadir un repositorio remoto.
* Eliminar remotos no válidos.
* Gestionar ramas.
* Definir si deben rastrearse o no.
* y más.

#### Ver tus conexiones remotas

Para ver las conexiones remotas utilizamos el comando

        'git remote'

Muestra todas las conexiones remotas que tenemos, si hemos clonado algún repositorio al menos mostraría origin.

    Ejemplo:

        Clonamos un repositorio utilizando git clone [url]
        Nos posicionamos dentro del directorio que contiene la rama origin y ejecutamos git remote.
    Por terminal debería aparecernos origin.

        Tambíen podemos usar git remote -v, que nos muestras las distintas conexiones remotas que tenemos mostrando el usuario y la url del mismo

    origin    https://github.com/usuario1/dir1 (fetch)
    origin    https://github.com/usuario1/dir1 (push)
    usuario2  https://github.com/usuario2/dir1 (fetch)
    usuario2  https://github.com/usuario2/dir1 (push)
    usuario3  https://github.com/usuario3/dir1 (fetch)
    usuario3  https://github.com/usuario3/dir1 (push)


#### Añadir repositorios remotos

Para añadir un repostirio remoto

        'git remote add [nombre] [url]'

Supongamos que tenemos solo nuestro usuario1 y añadimos usuario2

        'git remote add u2  https://github.com/usuario2/dir1
        'git remote -v'
         origin    https://github.com/usuario1/dir1 (fetch)
         origin    https://github.com/usuario1/dir1 (push)
         u2  https://github.com/usuario2/dir1 (fetch)
         u2  https://github.com/usuario2/dir1 (push)

Ahora para poder traer todos los cambios que se van realizando a usuario2 solo debemos ejecutar

        'git fetch u2'

#### Traer y combinar remotos

Como hemos visto 'git fetch remote-name' este comando traera todos los datos que no tenemos de dicho remoto.
Si clonas un repositorio, el comando de clonar automáticamente añade ese repositorio remoto con el nombre “origin”. Por lo tanto, git fetch origin se trae todo el trabajo nuevo que ha sido enviado a ese servidor desde que lo clonaste (o desde la última vez que trajiste datos). Es importante destacar que el comando git fetch solo trae datos a tu repositorio local - ni lo combina automáticamente con tu trabajo ni modifica el trabajo que llevas hecho. La combinación con tu trabajo debes hacerla manualmente cuando estés listo.

#### Enviar a tus remotos

        'git push origin master'

Al ejecutar el comando anterior se envía tu rama master a tu servidor origin. Esto sólo se permitirá si noha habido cambios en el origin antes de tu envío, si los hubiese primero tienes que traer todos los cambios realizados y luego enviar tus cambios.

#### Inspeccionar un remoto

        'git remote show origin'

Este comando nos muestra información sobre un remoto en particualr, en este caso del remoto origin nos puede mostrar:

* Url del repositorio remoto.
* Rama en la que se encuentra y a la que enviará los cambios si ejecutamos 'git push'.
* Ramas remotas que aún no tenemos.
* Ramas remotas eliminadas.
* Y varias ramas que serán combinadas automáticamente.

#### Eliminar y renombrar remotos

         'git remote rename u2 usuario2'

Cambia el nombre de la rama, este cambiará también la referencia u2/master por usuario2/master.

        'git remote rm usuario2'

Con este comando eliminados el remoto usuario2, ya sea porque ha dejado de ser colaborador o porque se ha cambiado de servidor.

