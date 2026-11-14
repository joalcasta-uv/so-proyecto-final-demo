# Sprint 2 · Servicios

> **Página de ejemplo.** Tiene la misma estructura que la del Sprint 1: un apartado por punto, con lo que se hizo, los comandos y la captura. [Volver al inicio](../)

- **Qué se pide en este sprint (8 puntos):** usuarios y grupo, sudo y permisos, firewall, llave SSH y actualización, script gráfico, script de consola, procesos y Docker Engine.
- **Qué se entrega en el campus:** el enlace del sitio.
- **Qué más:** video de 4 minutos, los dos scripts en el repositorio, 2 commits por integrante y `codigo_sprint2.txt` en el home del usuario principal.

## Cómo se organiza cada punto

Para cada uno de los 8 puntos la página lleva:

1. **Qué hicimos:** dos o tres frases con sus palabras.
2. **Comandos:** los que ejecutaron, en un bloque de código.
3. **Captura:** completa, con el prompt (`usuario@equipo`) y la fecha (`date`). Una captura puede mostrar varios comandos seguidos si se leen completos.
4. **Qué significa:** una explicación breve de lo que muestra la captura.

## Ejemplo: punto «Usuarios y grupo»

Creamos un usuario por integrante (ana, luis y marta), el grupo `proyecto` y la carpeta `/srv/proyecto`, donde el grupo lee y escribe y los demás no entran.

Comandos: `id`, `getent group proyecto`, `ls -ld /srv/proyecto`, un acceso permitido y uno negado.

**[Captura: id, getent y ls -ld, y después un touch dentro de /srv/proyecto que funciona con un usuario del grupo y falla con otro que no lo es]**

Qué significa: la línea de `ls -ld` muestra permisos `drwxrws---`: el dueño y el grupo tienen acceso total y los demás ninguno.

Los otros siete puntos se documentan con el mismo formato.

## Scripts

Los dos scripts están en la carpeta `scripts/` del repositorio. En la página va un enlace a cada uno, una captura del script ejecutándose (desde el ícono en el caso del gráfico) y, en el de consola, un caso que funciona y uno que falla con su código de salida.

## Video del sprint (4 minutos)

Aquí va el enlace del video de YouTube.
