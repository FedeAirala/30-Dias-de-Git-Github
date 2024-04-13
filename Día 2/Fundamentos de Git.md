# Fundamentos de Git

#### Obteniendo un repositorio

Existen dos maneras:

1. ##### Crear directorio Git

	Desde un directorio existente y exportarlo a git
	Se debe ir al directorio y ejecutar desde la terminal el siguiente comando

       'git init'

2. ##### Clonar un repositorio existente
	Para este caso se debe utilizar el siguiente comando 

       'git clone [url]'
	
	Dónde [url] es la dirección del repositorio que desea clonar (copiar). Este comando crea un directorio con todos los archivos que tenga ese repostorio y ya está inicializado con Git.

	Vemos los estados del repositorio inicializado

		'git status'

	Este nos deberia mostrar que no hay cambios porque cuando lo crea aún no tiene modificaciones, y debería mostrar por pantalla
	lo siguiente
		'On branch master
	nothing to commit, working directory clean'

	Ahora supongamos que creamos una archivo nuevo en el directorio llamado Readme.txt
	Volvemos a revisar el estado y nos sale el mensaje
		'On branch master
		Untracked files:
  		(use "git add <file>..." to include in what will be committed)

   		 README

		nothing added to commit but untracked files present (use "git add" to track)'

 3. ##### Rastrear archivos

	Para comenzar a rastrear el archivo README usamos el comando

		' git add README'

	Ahora revisamos los estados

		' git status'

	Veremos el mensaje
		'On branch master
		Changes to be committed:
  		(use "git reset HEAD <file>..." to unstage)

    		new file:   README'

	Lo que nos dice que el archivo está siendo rastreado por Git y preparado para ejecutar el cambio.
	Para confirmar los cambios ejecutamos el comando

		' git commit -m "Mensaje"'

	Una vez ejecutado el comando anterior Git guarda los cambios el directorio, se le asigna un mensaje con el cuál luego
	podremos ver en los estados los distintos cambios que hemos realizado.