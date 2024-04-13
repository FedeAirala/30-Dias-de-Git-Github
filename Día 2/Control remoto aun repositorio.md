# Control Remoto a un repositorio

### Crear un repositorio remoto

+ Iniciar cesión en github.com y crear un repostorio
+ Asignar un nombre que coincida con el local
+ Crearlo de visualización pública

### Conectar tu repositorio local con control remoto

* git remote set-url origin "Dirección del repositorio github" (Windows)
* git remote add origin "Dirección del repositorio github" (Mac)
* git push origin master : se envía la rama llamada master a github origin

# Fork y clones

Cuando se bifurca (Fork) un repositorio , estás creando una copia al remoto en Github
y una vez bifurcado, se clona (copia) desde Github a la pc local para trabajarlo.
Luego, en la terminal, se clona el repositorio en la pc,  se creará una carpeta por lo que no es 
necesario crear una.

#### Para realizar lo anterior se deben ejecutar los siguientes comandos

1. cd.. : para elegir la carpeta en donde copiar el repositorio que se va a clonar
2. git clone "Ruta del repositorio" : se copia el repositorio en la carpeta seleccionada y/o creada
3. cd "Nombre de la carpeta del repositorio copiado"

#### Conectarse al repositorio original

Se puede nombrar la conexión como desee pero generalmente se utiliza upstream

* git remote add upstream https://github.com/"Ruta del repositorio"
* git remote -v : para verificar que la conexión se haya realizado, en caso contrario lanzaráun error.