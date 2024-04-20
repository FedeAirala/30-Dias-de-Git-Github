# Github

#### Creación y configuración de la cuenta.



Se visita https://github.com, se rellenan los campos necesarios y pulsa el botón verde grande “Sign up for GitHub”. Ya tienes una cuenta Github.

Ahora bien puedes acceder a los repositorios Git utilizando el protocolo https://, identificándote con el usuario y la contraseña que acabas de elegir. Sin embargo, para simplificar el clonado de proyectos públicos, no necesitas crearte la cuenta. Es decir, la cuenta sólo la necesitas cuando comienzas a hacer cosas como bifurcar (fork) proyectos y enviar tus propios cambios más tarde.

#### Acceso con SSh

* Si prefieres usar SSH, necesitas configurar una clave pública. Si aún no la tienes, mira cómo generarla en Generando tu clave pública SSH.
* Abre tu panel de control (settings) de la cuenta utilizando el enlace de la parte superior derecha de la ventana.
* Aquí selecciona en el lado izquierdo la opción “SSH keys”
* Desde ahí, pulsa sobre "Add an SSH key", proporcionando un nombre y pegando los contenidos del archivo ~/.ssh/id_rsa.pub (o donde hayas definido tu clave pública) en el área de texto, y pulsa sobre “Add key”

Después dentro de Github tienes varias opciones para configurarlo como más desees (Iconos, Direcciones de correo, accesos, etc)


#### Participando de proyectos

Si queremos participar de un proyecto existente puedes bifurcarlo (fork) que consiste en crear una copia completa de repositorio totalmente bajo nuestro control.
Luego podemos hacer las modificaciones que deseemos y enviamos esos cambios al repositorio original, esto se hace con Pull Request, en donde se envía esos cambios al propietario original, se revisa esos cambios, y el propietario puede aceptarlos e integrarlos a su original o bien rechazarlos.

#### Flujo de trabajo en Github

Funcionamiento habitual

    1. Se crea una rama a partir de master.

    2. Se realizan algunos commits hacia esa rama.

    3. Se envía esa rama hacia tu copia (fork) del proyecto.

    4. Abres un Pull Request en GitHub.

    5. Se participa en la discusión asociada y, opcionalmente, se realizan nuevos commits.

    6. El propietario del proyecto original cierra el Pull Request, bien fusionando la rama con tus cambios o bien rechazándolos.

#### Creación de pull request

    1. Clonar nuestro fork en nuestro equipo

    2. Crear la rama, que sea descriptiva

    3. Realizar nuestros cambios

    4. Comprobar los cambios

    5. Realizar un commit de los cambios en la rama

    6. Enviar nuestra nueva rama de vuelta a nuestro fork  

Ahora tenemos los cambios realizados en nuestro proyecto fork. Luego lo que hacemos es crear una pull request al repositorio original y se siguen los pasos para integrar al repositorio original o no en el caso de que sea rechazado.

#### Mantenerse actualizados

Abrimos en nuestra terminal, la carpeta en donde tenemos el proyecto Git. Lanzamos el comando git pull, y este actualizará nuestro proyecto con todos los cambios que se han realizado en el original.

#### Mantenimiento de un proyecto

Primero creamos un repositorio y lo hacemos presionando en el botoón 'New Repository', esto nos llevará a un formulario en donde tenemos que rellenar los campos y luego presionar 'Create repository'. Como este repositorio está vacío Github nos mostrará instrucciones para crear un repostorio Git o conectarlo a un proyecto existente. Una vez en Github podemos dar la URL a cualquiera con quien querramos compartirla. Cada proyecto en GitHub es accesible mediante HTTPS como https://github.com/<usuario>/<proyecto>, y también con SSH con la dirección git@github.com:<usuario>/<proyecto>. Git puede obtener y enviar cambios en ambas URL, ya que tienen control de acceso basado en las credenciales del usuario.

#### Añadir colaboradores

Si deseamos trabajar con otras personas debemos añadirlas como colaboradores. Al añadirlas estas tendrán permiso de lectura y escritura. Para poder realizar esto debemos presionar el botón 'Collaborators' de la barra de menú. Teclear el usuario en la caja y persionar 'Add Collaborator'

#### Gestión de Pull Request

Los Pull Requests pueden venir de una rama en una bifurcación del repositorio, o pueden venir de una rama del mismo repositorio. La única diferencia es que, en el primer caso procede de gente que no tiene acceso de escritura a tu proyecto y quiere integrar en el tuyo cambios interesantes, mientras que en el segundo caso procede de gente con acceso de escritura al repositorio


