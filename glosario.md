# Qué es cada cosa

Las palabras que más preguntas han generado, explicadas con un ejemplo de este mismo sitio. [Volver al inicio](./)

## Repositorio

Una carpeta de proyecto guardada en GitHub, con el historial de todos los cambios. Aquí viven los archivos del grupo: el plan, los scripts, el Dockerfile y las páginas del sitio. Debe ser **público** para que el docente lo abra sin iniciar sesión. Se crea en GitHub con el botón «New» y se le pone un nombre, por ejemplo `so-proyecto-g07`.

En el Sprint 0 lo único que se entrega en el campus es **el enlace del repositorio**. Se ve así: `https://github.com/usuario/so-proyecto-g07`.

## Archivo .md (Markdown)

Un archivo de texto con extensión `.md` que GitHub muestra con formato: títulos con `#`, listas con `-`, tablas con `|`. Se escribe directamente en GitHub: botón «Add file → Create new file», el nombre del archivo y el texto. No necesita ningún programa especial.

## Plan de trabajo (plan/plan-de-trabajo.md)

Un archivo en la carpeta `plan` que dice **quién hace qué y cuándo**: una tabla con cada integrante, su rol y los archivos que son suyos, y las fechas de los sprints. Sirve para dos cosas: el docente revisa que los commits de cada uno toquen su parte, y en la sustentación cada integrante explica la parte que aquí dice que hizo. [Ver el ejemplo](plan/plan-de-trabajo.md).

## Ficha de verificación de versión (plan/ficha-version.md)

Un archivo en la carpeta `plan` donde el grupo demuestra que **comprobó la versión de cada distribución antes de descargarla**: fecha de lanzamiento, hasta cuándo recibe seguridad, si funciona en VirtualBox, si el instalador permite particionado manual, si hay guía oficial de Docker y si existe la imagen en Docker Hub. Cada respuesta lleva su enlace. [Ver el ejemplo](plan/ficha-version.md).

## Commit

Un guardado con nombre en el historial del repositorio. Cada vez que crean o editan un archivo en GitHub y pulsan «Commit changes», hacen un commit. El **mensaje** dice qué cambió. Bueno: «agrego la partición /var a la ficha». No aceptado: «update», «cambios». Cada integrante hace al menos 2 commits por sprint (sprints 1, 2 y 3) desde su propia cuenta de GitHub.

## Sprint

Un periodo corto de trabajo con una meta y una entrega al final. Son cuatro (0, 1, 2 y 3), más la sustentación. Cada uno cierra a las 11:55 p. m. del día anterior a la clase.

## Sitio web del grupo

Lo que está leyendo ahora. GitHub Pages convierte los archivos `.md` del repositorio en páginas web. Una página por sprint, con una captura por punto, los comandos usados y el video.

## Captura de terminal

Una imagen **completa** (sin recortes ni ediciones) donde se lee el comando, su resultado, el prompt (`usuario@equipo`) y la fecha del sistema (comando `date`).

## Código del sprint

Una cadena corta de letras y números (por ejemplo `XX00-AB12`) que el docente publica en el campus 48 horas antes del cierre. No es un programa. Se guarda con `echo "código" > codigo_sprint1.txt` en las dos VMs y se muestra con `cat` y `date` en el video, para comprobar que se grabó en ese sprint.
