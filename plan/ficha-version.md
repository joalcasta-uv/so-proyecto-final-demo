# Ficha de verificación de versión · Grupo 07

> **Ejemplo.** Así se llena plan/ficha-version.md. Los datos de la tabla son de muestra para mostrar el formato: cada grupo debe comprobar los suyos en las páginas oficiales el día que llena la ficha.

## ¿Qué es esta ficha?

Antes de descargar una distribución hay que comprobar que su versión sirve para el proyecto. Esta ficha es la prueba de que lo comprobaron. Se llena una vez por cada distribución del grupo (la gráfica, la de consola y la imagen base del Dockerfile) y cada respuesta lleva el enlace de donde sacaron el dato. No se descuentan puntos si la versión más reciente no sirve: se evalúa que lo hayan verificado.

Distribuciones del grupo 07: Xubuntu (gráfica), Rocky Linux (consola) y Alpine (imagen base).

## Ejemplo completo: Rocky Linux (VM de consola)

| Pregunta | Respuesta | Enlace donde lo comprobamos |
|---|---|---|
| Versión elegida y fecha de lanzamiento | Rocky Linux 9 (dato de muestra: escriban el número exacto, por ejemplo 9.x, y la fecha que dice la página de descargas) | https://rockylinux.org/download |
| Hasta cuándo recibe actualizaciones de seguridad | Fecha final de soporte que publica el proyecto para esa versión | https://docs.rockylinux.org/ |
| Requisitos de hardware y si funciona en VirtualBox | Requisitos mínimos de RAM, CPU y disco. Sí funciona: la instalamos en una VM de VirtualBox con 2 GB y 2 CPU | https://docs.rockylinux.org/ |
| ¿El instalador permite particionado manual? | Sí. El instalador (Anaconda) tiene la opción «Personalizada» en destino de la instalación | https://docs.rockylinux.org/ |
| Guía oficial para instalar Docker Engine en esa familia | Docker no tiene una página propia para Rocky. Usamos la de la familia CentOS/RHEL y lo dejamos documentado | https://docs.docker.com/engine/install/ |
| Imagen base del Dockerfile para esa versión | La imagen oficial existe en Docker Hub con la etiqueta de la versión elegida | https://hub.docker.com/_/rockylinux |

Si una respuesta es «no» o «no hay guía», lo dicen con una captura o un enlace y usan la versión anterior inmediata. Eso no baja la nota.

## Xubuntu (VM gráfica)

Se llena con las mismas seis preguntas. Además de lo anterior, anotan aquí cuánta RAM le dieron a la VM (2 GB como mínimo, 4 GB si la distribución lo pide) y por qué.

## Alpine (imagen base del Dockerfile)

Se llena con las mismas seis preguntas. Para la imagen base importa sobre todo la última: que exista en Docker Hub la etiqueta de la versión que eligieron, y que el gestor de paquetes sea el que van a usar en el Dockerfile (apk).
