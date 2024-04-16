# Etiquetado

Esta posibilidad de etiquetar puntos en el historial se utilizan generalmente para marcar versiones. En este apartado veremos como listar, crear y los distintos tipos que existen.

#### Listar etiquetas

        'git tag'

Comando que se utiliza para listar etiquetas. El orden en el que aparece no necesariamente es el orden de importancia.

        ' git tag -l 'v 1.5.6'
Este lista las etiquetas de una versión especifica.

#### Crear etiquetas

*  Etiquetas anotadas
    
    Estas etiquetas se guardan en una base de datos de Git, para crearla se utiliza el comando

        'git tag -a'
        
    Ejemplo: git tag -a v1.2 -m "mi versión 1.2", crea una etiqueta v1.2 con el mensaje de la misma.

* Etiquetas ligeras

     Esta etiqueta ligera no es más que el checksum de un commit guardado en un archivo - no incluye más información y para crearla se utiliza el comando

        ' git tag "nombre de la etiqueta"

    No se deben pasar los argumentos -a, -s o -m.

Para ver la información que contiene cada etiqueta se utiliza 

          ' git show "nombre de la etiqueta" 


* Etiquetado tardío

    Utilizado cuando se quiere etiquetar un commit realizado anteriormente

    ' git tag -a "etiqueta" "cheksum"


* Compartir etiquetas

      ' git push origin --tags

    Envía información de las etiquetas a rama origin

* Sacar etiqueta

    En Git, no puedes sacar (check out) una etiqueta, pues no es algo que puedas mover. Si quieres colocar en tu directorio de trabajo una versión de tu repositorio que coincida con alguna etiqueta, debes crear una rama nueva en esa etiqueta

      ' git checkout -b "version2" "v2.0"'



# Alias

Si no quieremos escribir el nombre completo de cada comando de Git, podemos crear un alias para cada comando mediante git config. Algunos ejemplos de ellos pueden ser:

        ' git config --global alias.co checkout '
        ' git config --global alias.br branch '
        ' git config --global alias.ci commit '
        ' git config --global alias.st status '


Esto significa por ejemplo que 

        ' git config checkout '
        ' git congfig co '

Ejecuten el mismo comando, ya que hemos etiquetado a checkout con co mediante la configuración más arriba explicada.

De esta manera también se pueden crear alias para extensiones de comando muchos más largas como

        ' git config --global alias.last 'log -1 HEAD '
        ' git last '

git last lanzaría de esta manera la última confirmación realizada.



