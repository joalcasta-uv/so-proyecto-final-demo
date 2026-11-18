# Sprint 3 · Cierre

> **Página de ejemplo.** Muestra cómo se ve la página del último sprint: un apartado por cada punto, con lo que se hizo, los comandos, la captura y una explicación corta. Las capturas se describen entre corchetes; en su sitio van las imágenes reales, completas, con el prompt y la fecha. [Volver al inicio](./)

- **Qué se pide en este sprint (5 puntos):** Dockerfile, contenedor, Docker Hub, Kubernetes y sitio web.
- **Qué se entrega en el campus:** el enlace de este sitio.
- **Qué más:** el video de 5 minutos, 2 commits por integrante, el archivo `codigo_sprint3.txt` en el home del usuario principal de las dos VMs, el Dockerfile y el YAML en el repositorio y la imagen pública en Docker Hub.

## 1. Dockerfile

Partimos de la imagen base asignada al grupo 07, Alpine. Con su gestor de paquetes (`apk`) instalamos git, curl, un editor y un compilador, y creamos un usuario sin permisos de administrador. Cada instrucción lleva un comentario.

```dockerfile
# Imagen base asignada al grupo 07 (la versión sale de la ficha)
FROM alpine:<versión de la ficha>

# Herramientas pedidas: git, curl, un editor (nano) y un compilador (build-base trae gcc y make)
RUN apk add --no-cache git curl nano build-base

# Usuario sin permisos de administrador
RUN adduser -D estudiante

# Desde aquí todo corre como ese usuario
USER estudiante
WORKDIR /home/estudiante

# Al iniciar el contenedor abre una terminal
CMD ["sh"]
```

Comandos: `docker build -t g07-alpine:1.0 .` y `docker images`

**[Captura 1: el Dockerfile abierto en el repositorio]**

**[Captura 2: docker build terminando bien y docker images mostrando g07-alpine, con prompt y fecha]**

## 2. Contenedor

Ejecutamos un contenedor interactivo con la imagen y mostramos cada comando: `run`, `ps`, `exec`, `logs`, `stop`, `rm` e `inspect`. Para cada uno una captura y una explicación breve.

| Comando | Qué hace |
|---|---|
| docker run -it --name g07 g07-alpine:1.0 | Crea y arranca el contenedor con una terminal |
| docker ps -a | Lista los contenedores, también los detenidos |
| docker exec -it g07 sh | Abre otra terminal dentro de un contenedor que ya corre |
| docker logs g07 | Muestra lo que el contenedor escribió en su salida |
| docker stop g07 | Detiene el contenedor |
| docker rm g07 | Elimina el contenedor detenido |
| docker inspect g07 | Muestra su configuración completa (red, usuario, rutas) |

**[Captura 3 a 5: los siete comandos, con su resultado, el prompt y la fecha]**

## 3. Docker Hub

Etiquetamos la imagen como `usuario/nombre:versión`, la publicamos, borramos la copia local y la bajamos de nuevo.

Comandos: `docker tag g07-alpine:1.0 usuario/g07-alpine:1.0`, `docker push usuario/g07-alpine:1.0`, `docker rmi usuario/g07-alpine:1.0` y `docker pull usuario/g07-alpine:1.0`

El README de la imagen en Docker Hub dice el nombre del grupo, la distribución base, las herramientas instaladas y el comando `docker run` para usarla.

**[Captura 6: el push terminado]**

**[Captura 7: la página pública de la imagen en Docker Hub, con la URL a la vista]**

**[Captura 8: el pull después de borrar la imagen local]**

**[Captura 9: el README de la imagen]**

## 4. Kubernetes

En la VM de consola (con 3 GB de RAM) instalamos Minikube, que trae su propio `kubectl` (vale escribir `kubectl` o `minikube kubectl --`), y lo arrancamos con el usuario normal, no con sudo ni como root: `minikube start --driver=docker`

Creamos un Deployment con 2 réplicas de nuestra imagen de Docker Hub. Como la imagen no tiene un servicio, el YAML lleva `command: ["sleep", "infinity"]` para que el contenedor no termine.

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: g07-deployment
spec:
  replicas: 2
  selector:
    matchLabels:
      app: g07
  template:
    metadata:
      labels:
        app: g07
    spec:
      containers:
      - name: g07
        image: usuario/g07-alpine:1.0
        command: ["sleep", "infinity"]
```

Comandos: `kubectl get nodes`, `kubectl apply -f deployment.yaml`, `kubectl get pods -o wide`, `kubectl exec -it NOMBRE-DEL-POD -- sh` (dentro: `git --version` y `whoami`), `kubectl scale deployment g07-deployment --replicas=4`, `kubectl delete pod NOMBRE-DEL-POD` y de nuevo `kubectl get pods`.

**[Captura 10: kubectl get nodes con el nodo Ready]**

**[Captura 11: el YAML en el repositorio y kubectl get pods -o wide con 2 réplicas]**

**[Captura 12: git --version y whoami dentro del pod]**

**[Captura 13: get pods con 4 réplicas, antes y después de borrar un pod]**

**Quién recrea el pod borrado:** el Deployment. Él crea un ReplicaSet y el ReplicaSet se encarga de que siempre haya 4 pods corriendo. Al borrar uno, el ReplicaSet ve que quedan 3 y crea otro para volver a 4.

## 5. Sitio web

El sitio completo cumple el contenido mínimo. Esta página de portada es el modelo: [ver la portada](./).

- Portada con el objetivo, los integrantes y lo que hizo cada uno.
- Distribuciones elegidas, con la versión y la ficha de verificación.
- Una página por sprint (0, 1, 2 y 3).
- Cuadro comparativo del instalador de su distribución, de mínimo 6 filas.
- Conclusiones: un párrafo por integrante, con su nombre, de 4 a 6 líneas.
- Declaración de uso de inteligencia artificial y enlace al repositorio.
- Abre sin iniciar sesión.

## Código del sprint

Comandos: `echo "XX00-AB12" > codigo_sprint3.txt`, `cat codigo_sprint3.txt` y `date`, en las dos VMs. El código lo publica el docente en el campus 48 horas antes del cierre.

## Video del sprint (5 minutos)

Pantalla continua y sin cortes. Cada integrante muestra su parte, dice su nombre y qué hizo en los primeros 10 segundos, y aparece su cara.

Aquí va el enlace del video de YouTube (público o no listado).

## Lo que hizo cada integrante en este sprint

| Integrante | Qué hizo | Commits |
|---|---|---|
| Ana | Revisó las páginas del sitio, completó las conclusiones y entregó el enlace en el campus | 2 |
| Luis | Instaló Minikube en la consola y creó el Deployment | 2 |
| Marta | Escribió el Dockerfile, publicó la imagen en Docker Hub y grabó el video | 3 |
