# Ignorar archivos

 En algunas ocaciones cuando modificamos archivos, se generan archivos que no queremos que Git añada. Para ello
podemos crear un archivo .gitignore, todos los archivos agregados al mismo son los que no queremos que Git lo tenga
en cuenta cuando se van a confirmar los cambios.

#### Creando un fichero gitignore

Para realizar esto utilizamos el comando

    ' touch .gitignore'

Si miramos en nuestro directorio en este momento se debería haber creado un fichero .gitignore y todo lo que se encuentre 
dentro del mismo git no lo tomará en cuenta a la hora de revisar los estados por lo que no se confirmarán.

 # Cambios preparados y no preparados

¿Qué has cambiado pero aun no has preparado? y 
¿Qué has preparado y está listo para confirmar?

Cuando se quiere ver exactamente que ha cambiado y no solo los archivos que han cambiado cuando los estados,
podemos utilizar el comando diff, que nos muestra las líneas exactas que fueron cambiadas o eliminadas

    ' git diff'

# Confirmando cambios

Una vez que estamos preparados para confirmar los cambios utilizamos el comando commit

    ' git commit -m "Mensaje"'

 Una vez lanzado este comando podemos ver la rama y que nombre le puso al cambio.

# Eliminar archivos

Para eliminar archivos de Git, debes eliminarlos de tus archivos rastreados 
(o mejor dicho, eliminarlos del área de preparación) y luego confirmar. 
Para ello existe el comando git rm, que además elimina el archivo de tu 
directorio de trabajo de manera que no aparezca la próxima vez como un archivo no rastreado.

	' git rm "Nombre del archivo"

 Otra cosa que podemos hacer con rm es mantener el archvio pero eliminarlo del área de preparación
de la siguiente manera

	' git rm --cache "Nombre del archivo'


