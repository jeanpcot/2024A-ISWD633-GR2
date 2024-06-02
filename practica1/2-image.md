### Indicaciones para la práctica
El contenido solicitado entre paréntesis angulares debe ser reemplazado y los paréntesis angulares deben ser eliminados.

# Imagen
Es un archivo único que contiene todos los programas, librerías, dependencias y configuraciones necesarias para instalar y/o ejecutar una aplicación o un conjunto de aplicaciones.
![Imagen](imagenes/imagen.PNG)


## ¿Cuál es la relación entre una imagen y un contenedor? 
COMPLETAR: Una imagen es una plantilla que define el contenido y configuración de un contenedor. Un contenedor es una instancia en ejecución creada a partir de una imagen.

![Imagen y contenedores](imagenes/imagenYcontenedores.JPG)
## Comandos para imágenes

### Descargar imagen
Descarga la última versión de la imagen disponible en el registro de Docker.

```
docker pull <nombre imagen> 
```

Descarga una versión específica de la imagen, cada imagen tiene etiquetas (tags) para diferentes versiones.
Una imagen puede tener la etiqueta latest para representar la última versión, si no se especifica una etiqueta se hará referencia a la versión latest.

```
docker pull <nombre imagen>:<tag>
```

Descargar la imagen **hello-world**
COMPLETAR: `docker pull hello-world`

**¿Qué es nginx?**
Nginx es un servidor web y un servidor proxy inverso de alto rendimiento, conocido por su capacidad de manejar grandes volúmenes de conexiones simultáneas con eficiencia. Además de servir contenido web estático, también se utiliza para balanceo de carga, proxy de correo y como un proxy inverso para HTTP, HTTPS, SMTP, POP3 e IMAP.

Descargar la imagen  **nginx** en la versión **alpine**
COMPLETAR: `docker pull nginx:alpine`

### Listar imágenes

```
docker images
```
![image](https://github.com/jeanpcot/2024A-ISWD633-GR2/assets/161987855/2d93d3ad-74f1-4015-8af5-143f393b689a)


**Identificadores**
En Docker, se utilizan varios identificadores para diferenciar de manera única los elementos del sistema, como imágenes, contenedores, volúmenes y redes. Estos identificadores son generados automáticamente por Docker y son únicos dentro del contexto del sistema Docker en el que se encuentran. 

### Inspeccionar una imagen
El comando docker inspect se utiliza para obtener información detallada sobre un objeto de Docker específico, como un contenedor, una imagen, un volumen o una red.  Proporciona información en formato JSON sobre el objeto especificado.

```
docker inspect <nombre imagen>
docker inspect <nombre imagen>:<tag>
```

Inspeccionar la imagen hello-world 
COMPLETAR: docker inspect hello-world


**¿Con qué algoritmo se está generando el ID de la imagen**
COMPLETAR: El ID de la imagen en Docker se genera utilizando el algoritmo de hash SHA-256. Este algoritmo produce un identificador único y seguro basado en el contenido de la imagen, garantizando que cualquier cambio en la imagen resulte en un ID diferente.

### Filtrar imágenes

```
docker images | grep <termino a buscar>

```

### Para eliminar una imagen
Eliminar permanentemente la imagen de tu sistema Docker.

```
docker rmi <nombre imagen>:<tag>
```

Eliminar la imagen hello-world 
COMPLETAR: # docker image rm hello-world

-f: Es la opción para forzar la eliminación de la imagen incluso si hay contenedores en ejecución que utilizan esa imagen.
Cuando eliminas una imagen Docker, Docker no elimina automáticamente los contenedores que se han creado a partir de esa imagen. Esto significa que, aunque hayas eliminado la imagen, el contenedor seguirá ejecutándose normalmente.  
**Considerar**
Eliminar una imagen no afecta a los contenedores que se han creado a partir de esa imagen, a menos que esos contenedores dependan de archivos o configuraciones específicas de la imagen eliminada. En ese caso, es posible que los contenedores se comporten de manera inesperada después de eliminar la imagen.
Es una buena práctica detener y eliminar todos los contenedores que dependan de una imagen antes de eliminar la imagen en sí.

```
docker rmi -f <nombre imagen>:<tag>
```

