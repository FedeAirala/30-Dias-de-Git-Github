# Protocolos en servidores Git

Para poder realizar cualquier colaboración en Git, se necesita tener un repositorio remoto, en donde los colaboradores sean capaces de acceder al repositorio incluso si tu computadora no está en línea – muchas veces es útil tener un repositorio confiable en común. Por lo tanto, el método preferido para colaborar con otra persona es configurar un repositorio intermedio al cual ambos tengan acceso, y enviar (push) y recibir (pull) desde allí.

### Los protocolos

#### Protocolo local

En este, el repositorio remoto es simplemente otra carpeta en el disco local. Si dispones de un sistema de archivos compartido, podrás clonar (clone), enviar (push) y recibir (pull) a/desde repositorios locales basado en archivos. Para clonar un repositorio como estos, o para añadirlo como remoto a un proyecto ya existente, usa el camino (path) del repositorio como su URL. Por ejemplo, para clonar un repositorio local, puedes usar algo como:

    ' git clone <ruta del proyecto> '
O como:

    git clone file:///ruta del proyecto'

En el primer caso Git copiará directamente los archivos que necesita, mientras que en el segundo caso, utilizando 'file' Git lanza el proceso que usa habitualmente para transferir datos sobre una red; proceso que suele ser mucho menos eficiente.

Para añadir un repositorio local a un proyecto Git existente, puedes usar algo como:

    ' git remote add local_proj ruta del proyecto'

Con lo que podrás enviar (push) y recibir (pull) desde dicho remoto exactamente de la misma forma a como lo harías a través de una red.

#### Protocolos HTTP

HTTP Inteligente 

*  funciona de forma muy similar a los protocolos SSH y Git, pero se ejecuta sobre puertos estándar HTTP/S y puede utilizar los diferentes mecanismos de autenticación HTTP. Esto significa que puede resultar más fácil para los usuarios, puesto que se pueden identificar mediante usuario y contraseña (usando la autenticación básica de HTTP) en lugar de usar claves SSH.


HTTP Tonto

* Si el servidor no dispone del protocolo HTTP “Inteligente”, el cliente de Git intentará con el protocolo clásico HTTP que podemos llamar HTTP “Tonto”. Este protocolo espera obtener el repositorio Git a través de un servidor web como si accediera a archivos normales.
 Para permitir acceso de lectura con HTTP, debes hacer algo similar a lo siguiente:

    cd ruta del directorio
    
    git clone --bare /path/to/git_project gitproject.git

    cd gitproject.git

    mv hooks/post-update.sample hooks/post-update

    chmod a+x hooks/post-update

#### Protocolos SSH

SSH es un protocolo muy habitual para alojar repositorios Git en hostings privados. Esto es así porque el acceso SSH viene habilitado de forma predeterminada en la mayoría de los servidores, y si no es así, es fácil habilitarlo. Además, SSH es un protocolo de red autenticado sencillo de utilizar.

Para clonar un repositorio a través de SSH, puedes indicar una URL ssh:// tal como:

    ' git clone ssh://user@server/project.git'

También puedes usar la sintaxis estilo scp del protocolo SSH:

    'git clone user@server:project.git'

Pudiendo asimismo prescindir del usuario; en cuyo caso Git asume el usuario con el que estés conectado en ese momento.

#### Protocolo Git

Viene incorporado con Git. Escucha por un puerto dedicado (9418) y nos da un servicio similar al del protocolo SSH; pero sin ningún tipo de autentificación. Para que un repositorio pueda exponerse a través del protocolo Git, tienes que crear en él un archivo git-daemon-export-ok; sin este archivo, el “demonio” no hará disponible el repositorio. Pero, aparte de esto, no hay ninguna otra medida de seguridad. O el repositorio está disponible para que cualquiera lo pueda clonar, o no lo está

