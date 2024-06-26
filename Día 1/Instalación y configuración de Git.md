# ¿Qué es Git?

Git es un software de código abierto (gratuito para que cualquiera lo use) escrito por Linus Torvalds, quien también escribió el sistema operativo Linux.

Es un programa para realizar un seguimiento de los cambios a lo largo del tiempo, conocido en programación como control de versiones .

Este control de versiones tiene la ventaja de que todo lo que controla lo va rastreando, esto quiere decir que cualquier cambio que se ejecute en alguna de las versiones Git lo  va a saber, lo muestra y lo cambia en caso de confirmar que lo este rastreado.

# Instalación de Git

Windows : se recomienda descargar GitHub para Windows, que incluye Git y tiene una instalación más sencilla: windows.github.com . Utilice Git Shell para su terminal.

Mac : También puedes descargar GitHub para Mac, que incluye Git, mac.github.com (desde Preferencias, selecciona la instalación de herramientas de línea de comandos) o
Descargue Git solo en: git-scm.com/downloads y siga las instrucciones de instalación.

# Configuración de Git

* git --version :  para ver la versión de git instalada.
* git config --global user.name "<Tu nombre>": establece un nombre de usuario para git de manera global en el sistema.
* git config --global user.email "<tuemail@ejemplo.com>" : establece el email en el sistema.

Los últimos 2 comandos los utiliza git para saber quien está realizando los cambios.

# Creación de carpetas e incialización en git 

* mkdir "nombre de la carpeta" : crea una carpeta.
* cd "nombre de la carpeta": se posiciona dentro de la carpeta.
* git init: crea una instancia de git para un proyecto en la carpeta.

# Verificación de estados y agregar cambios

Se crea un nuevo archivo .txt dentro de carpeta creada: "hola_mundo.txt"

* git status: verifica cambios y si hay algun error devuelve 'fatal: No es un repositorio git"
* git add hola_mundo.txt: se agrega el archivo al repositorio local
* git commit -m "Comentario del cambio realizado"

Realizar más cambios: agrego otra línea al archivo txt creado.

* git diff: muestra las diferencias entre el archivo creado y lo cambiado.
* git add . : agrega todos los cambios realizados (de todas las carpetas en caso de que haya más de una).
* git commit -m "Comentario del/los cambios realizados