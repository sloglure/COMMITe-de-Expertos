# Ximena Lovers
Trabajo grupal para el ramo Desarrollo de Aplicaciones Web, se analizara y utilizara en HTML lo siguiente: Docker, Nginx, Bootstrap, CSS 

## Documentación proceso de Docker

## Descripción

Este proyecto contiene un sitio web estático servido mediante **Nginx** dentro de un contenedor Docker.

La configuración mostrada en la demostración utiliza la imagen base `nginx:alpine` y copia los archivos del proyecto al directorio que Nginx utiliza para servir contenido web.

## Requisitos

- Docker Desktop instalado y ejecutándose.
- El proyecto debe contener el archivo `Dockerfile`.
- Los archivos del sitio web deben estar dentro de la carpeta del proyecto.

## Estructura de Docker

El archivo `Dockerfile` utilizado es:

```dockerfile
FROM nginx:alpine
COPY . /usr/share/nginx/html
```

### Explicación

- `FROM nginx:alpine`: utiliza Nginx basado en Alpine Linux como imagen base.
- `COPY . /usr/share/nginx/html`: copia el contenido del proyecto al directorio público de Nginx.

## Construir la imagen Docker

Primero, abrir PowerShell y ubicarse en la carpeta del proyecto:

```powershell
cd C:\Users\catal\OneDrive\Documentos\GitHub\COMMITE-de-Expertos\proyecto-grupo
```

Luego, construir la imagen con:

```powershell
docker build -t mi-sitio-web .
```

El punto (`.`) indica que Docker debe utilizar la carpeta actual como contexto de construcción.

## Ejecutar el contenedor

Una vez creada la imagen, ejecutar:

```powershell
docker run -p 8080:80 --name contenedor-lovers mi-sitio-web
```

### Explicación del comando

- `docker run`: crea y ejecuta un contenedor.
- `-p 8080:80`: conecta el puerto `8080` del equipo con el puerto `80` del contenedor, donde Nginx atiende las solicitudes HTTP.
- `--name contenedor-lovers`: asigna el nombre `contenedor-lovers` al contenedor.
- `mi-sitio-web`: indica la imagen Docker que se utilizará.

## Comprobar que el sitio funciona

Con el contenedor ejecutándose, abrir un navegador y acceder a:

```text
http://localhost:8080
```

El sitio web debería mostrarse desde el contenedor Docker.
