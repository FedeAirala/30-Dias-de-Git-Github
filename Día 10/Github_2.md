#### Notificaciones por correo electrónico

Cuando alguien realiza un cambio en el código y te crea un Pull Request, debes recibir una notificación por correo electrónico avisándote. Este te dará una lista de los archivos cambiados y como fueron cambiados. 

Para fusionar esto sin tener que añadirla al local podemos ejecutar

    'git pull <URL> patch_1'

 Si lo deseas, puedes crear y cambiar a una rama y luego ejecutar el comando para fusionar los cambios del Pull Request.

Las otras URL interesantes son las de .diff y .patch, que como su nombre lo indica, proporcionan “diff unificados” y formatos de parche del Pull Request.

Ejemplo :     'curl https://github.com/tonychacon/fade/pull/1.patch | git am'

#### Colaboración en el Pull Request

Puedes participar en una discusión con la persona que generó el Pull Request. Puedes comentar líneas concretas de código, comentar commits completos o comentar el Pull Request en sí mismo, utilizando donde quieras el formato Markdown.

Cada vez que alguien comenta, recibirás nuevas notificaciones por correo, lo que te permite vigilar todo lo que pasa. Cada correo tendrá un enlace a la actividad que ha tenido lugar y, además, puedes responder al comentario simplemente contestando al correo.

Una vez que el código está como quieres y deseas fusionarlo, puedes copiar el código y fusionarlo localmente, mediante la sintaxis ya conocida de 

    'git pull <url> <branch>'

Si decides que no quieres fusionar, también puedes cerrar el Pull Request y la persona que lo creó será notificada.

#### Archivos especiales

Hay dos archivos especiales que GitHub detecta y maneja si están presentes en el repositorio.

#### README

En primer lugar tenemos el archivo README, que puede estar en varios formatos. Puede estar con el nombre README, README.md, README.asciidoc y alguno más. Cuando GitHub detecta su presencia en el proyecto, lo muestra en la página principal, con el renderizado que corresponda a su formato.

En muchos casos este archivo se usa para mostrar información relevante a cualquiera que sea nuevo en el proyecto o repositorio. Esto incluye normalmente cosas como:

* Para qué es el proyecto

* Cómo se configura y se instala

* Ejemplo de uso

* Licencia del código del proyecto

* Cómo participar en su desarrollo

Puesto que GitHub hace un renderizado del archivo, puedes incluir imágenes o enlaces en él para facilitar su comprensión.

#### CONTRIBUTING

El otro archivo que GitHub reconoce es CONTRIBUTING. Si tienes un archivo con ese nombre y cualquier extensión, GitHub mostrará algo como Apertura de un Pull Request cuando existe el archivo CONTRIBUTING. cuando se intente abrir un Pull Request.

