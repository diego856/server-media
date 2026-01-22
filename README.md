# 🎬 Home Media Server (Docker)

Este repositorio contiene la orquestación en **Docker Compose** para desplegar un servidor de medios automatizado utilizando la suite *arr*.

## 🚀 Servicios Incluidos

* **Sonarr:** Gestión y descarga automática de Series de TV.
* **Radarr:** Gestión y descarga automática de Películas.
* **Jackett:** Proxy de indexadores (Torrents) para conectar con Sonarr y Radarr.

## 📋 Requisitos

* Docker Desktop instalado.
* Una estructura de carpetas local para las configuraciones (ver *Notas Importantes*).

## 📄 Documentación Completa

Para ver el paso a paso detallado de la configuración, los indexadores y cómo conectar los servicios, consulta el siguiente documento:

👉 **[Ver Guía de Configuración en Google Docs](https://docs.google.com/document/d/1EZ0vU58icq1t8oUcNZAGJvHG7osmrCefVSWYhQs2OfI/edit?tab=t.0)**

## 🛠️ Instalación y Uso

1.  Clona este repositorio:
    ```bash
    git clone [https://github.com/Diego856/server-media.git](https://github.com/Diego856/server-media.git)
    ```
2.  Ubícate en la carpeta del proyecto.
3.  Levanta los contenedores en segundo plano:
    ```bash
    docker-compose up -d
    ```

## ⚠️ Notas Importantes sobre Datos (Backup)

Este repositorio **solo contiene la estructura** (`docker-compose.yml`).

Las configuraciones sensibles (bases de datos, claves de API, historial de descargas) se almacenan localmente en tu máquina (por defecto en `C:\DockerData`). **Asegúrate de tener copias de seguridad de esa carpeta manualmente**, ya que no se suben a GitHub por seguridad.