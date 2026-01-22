# 🎬 Home Media Server (Docker)

Este repositorio contiene la orquestación en **Docker Compose** para desplegar un servidor de medios automatizado utilizando la suite *arr*.

## 🚀 Servicios Incluidos

* **Sonarr:** Gestión y descarga automática de Series de TV.
* **Radarr:** Gestión y descarga automática de Películas.
* **Jackett:** Proxy de indexadores (Torrents) para conectar con Sonarr y Radarr.

## 📋 Requisitos Previos

* **Docker Desktop** instalado y corriendo.
* **Git** instalado.

## 📄 Documentación Completa

Para ver el paso a paso detallado de la configuración interna de los programas, los indexadores y cómo conectarlos, consulta el siguiente documento:

👉 **[Ver Guía de Configuración en Google Docs](https://docs.google.com/document/d/1EZ0vU58icq1t8oUcNZAGJvHG7osmrCefVSWYhQs2OfI/edit?tab=t.0)**

---

## 🛠️ Instalación y Puesta en Marcha

# 🎬 Home Media Server (Docker)

Este repositorio contiene la orquestación en **Docker Compose** para desplegar un servidor de medios automatizado utilizando la suite *arr* (Sonarr, Radarr y Jackett).

## 🚀 Servicios Incluidos

- **Sonarr:** Gestión y descarga automática de series de TV.
- **Radarr:** Gestión y descarga automática de películas.
- **Jackett:** Proxy de indexadores (torrents) para conectar con Sonarr y Radarr.

## 📋 Requisitos Previos

- **Docker Desktop** instalado y ejecutándose.
- **Git** instalado.

## 📄 Documentación Completa

Para ver el paso a paso detallado de la configuración interna de los programas, los indexadores y cómo conectarlos, consulta:

👉 [Guía de Configuración (Google Docs)](https://docs.google.com/document/d/1EZ0vU58icq1t8oUcNZAGJvHG7osmrCefVSWYhQs2OfI/edit?tab=t.0)

---

## 🛠️ Instalación y Puesta en Marcha

1. Clona el repositorio y ve al directorio del proyecto:

```bash
git clone https://github.com/Diego856/server-media.git
cd server-media
```

2. Elige tu escenario de instalación:

### A) Instalación nueva (desde cero)

Si es la primera vez que instalas esto y no tienes un backup previo:

- Abre `docker-compose.yml` con tu editor de texto favorito.
- IMPORTANTE: Revisa la sección `volumes`. Debes cambiar las rutas de la izquierda (por ejemplo `C:\\...` o `D:\\...`) para que coincidan con las carpetas de TU computadora donde guardas las películas y series.

Ejemplo: si tus series están en `E:\\MisSeries`, cambia la línea correspondiente a:

```
- E:\\MisSeries:/tv
```

- Inicia el servidor:

```bash
docker-compose up -d
```

Resultado: Docker creará las carpetas de configuración automáticamente y los servicios arrancarán con la configuración por defecto.

### B) Restauración desde Backup (recuperar tu configuración)

Si ya tienes un backup (por ejemplo al reinstalar o mover el servidor):

1. Restaura la carpeta de datos (ej. `DockerData`) en la misma ruta donde estaba antes (por ejemplo `C:\\DockerData`).
2. Verifica que las letras de unidad y rutas de los discos coincidan con las de tu configuración anterior (ej. `D:\\Plex`). Si cambiaron, ajusta `docker-compose.yml` en la sección `volumes`.
3. Inicia el servidor:

```bash
docker-compose up -d
```

Resultado: Docker detectará los datos existentes y los servicios arrancarán con tu configuración anterior.

---

## ⚠️ Notas sobre seguridad y backups

- Este repositorio solo contiene la definición/estructura (`docker-compose.yml`). Las configuraciones sensibles (bases de datos, claves de API, etc.) viven localmente en la carpeta de datos (por ejemplo `DockerData`).
- Para usuarios nuevos: la carpeta de datos se genera al iniciar los contenedores.
- Haz backups periódicos de esa carpeta; no se sube a GitHub por seguridad.

---

## 🧾 Actualizar este README en GitHub

Para subir los cambios locales al repositorio remoto, ejecuta en tu terminal (VS Code / PowerShell):