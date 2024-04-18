# Ramas Remotas

 Las ramas remotas funcionan como marcadores, para recordarte en qué estado se encontraban tus repositorios remotos la última vez que conectaste con ellos. Suelen referenciarse como (remoto)/(rama). Por ejemplo, si quieres saber cómo estaba la rama master en el remoto origin, puedes revisar la rama origin/master.

        Ejemplo: supongamos que tenemos un servidor Git en nuestra red, en git.versionorigin.com, hacemos un clone y Git automáticamente lo denominará origin, traerá todos sus datos, y denominará la copia local origin/mster. Proporciona tu rama master local, apuntando tu rama local a la misma rama master/origin, de manera que podamos trabajar sobre ella.


![alt text](https://git-scm.com/book/en/v2/images/remote-branches-1.png)
Imagen sacada del libro de documnetación de la página oficial de Git

Si en este momento hacemos cambios sobre la rama master y alguien más hace push sobre el origin, Git verá que en origin que la rama master ha cambiado de posición, pero no hará cambios en la rama local. Para sincronizar con los cambios hechos en origin

    'git fetch origin'

Este comando traerá los cambios realizados y cambiará el origin en tu rama local.
Supongamos ahora que los cambios realizados los hizo usuario2, para poder ver los cambios realizados por ese contribuyente

    'git fetch usuario2'

Donde no traerá los cambios realizados que no teníamos en el local.

Cuando deseamos compartir nuestros cambios debemos llevar (push) expresamente las ramas que queremos compartir, ya que las ramas locales no se sincronizan automáticamente con las remotas.

Si tienes una rama llamada server, con la que vas a trabajar en colaboración; puedes llevarla al remoto de la misma forma que llevaste tu primera rama. Con el comando 
    
        'git push (remoto) (rama)'

En el caso de que desearamos que en el remoto esa rama tome algún nombre en particular debemos usar el comando

        ' git push (remoto) (rama):(otra rama)'
    
#### Traer y fusionar ramas

A pesar de que el comando git fetch trae todos los cambios que no tienes del servidor, este no modifica tu directorio de trabajo. Simplemente obtendrá los datos y dejará que tú mismo los fusiones. Sin embargo, existe un comando llamado git pull, el cuál básicamente hace git fetch seguido por git merge en la mayoría de los casos.

#### Eliminar ramas remotas

Imagines que tenemos una rama en la que ya se han realizado los cambios y se fusionaron con origin, si deseamos elimanar esa rama podríamos utilizar el comando

    'git push origin --delete (rama)'
Una vez ejecutado este comando, lo que hace Git es eliminar el puntero a esa rama, el cuál permanece en un historial de eliminaciones, durante un tiempo, hasta que el recolector de basura se ejecute, de manera que si la has borrado accidentalmente, suele ser fácil recuperarla.


# Reorganizar el trabajo realizado

En git tenemos dos formas de integrar cambios, una es a traves del comando merge que lo vimos anteriormente, otra es reorganizando el trabajo (rebase).Ahora veremos como utilizarla y en que casos no es conveniente.

#### Reorganización Básica

Supongamos que tenemos una rama origin/master y una rama master en local en la que hemos realizado y confirmado algunos cambios. Veremos dos ramas, una con los cambios realizados en master y otra en donde está origin/master. Si quisieramos confirmar los cambios podemos realizar un merge, donde se crearía una instantánea nueva de cada rama y el ancestro común. 

![alt text](https://git-scm.com/book/en/v2/images/basic-rebase-2.png)


Otra forma de hacerlo sería capturar los cambios realizados en C4 y replicarlos encima de  C3 utilizando los siguientes comandos en el caso de la figura anterior

    'git checkout experiment'
    'git rebase master'
    'git checkout master'
    'git merge experiment'

Ejecutando esto

![alt text](https://git-scm.com/book/en/v2/images/basic-rebase-4.png)


donde la instantánea apuntada por C4' es exactamente la misma apuntada por C5.
Y Así tendríamos la forma de reorganizar los cambios que se van realizando sobre el trabajo.

### Esto no es recomendable hacerlo en repositorios públicos, ya que podrían traer cambios a otros usuarios, en los que se les va a resultar muy difícil ver y llevar los cambios hechos al momento de reorganizar.






    