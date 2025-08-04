  

# PeliculasAPP – MongoDB Modelado

  

Este repositorio contiene el modelado de base de datos en MongoDB para una aplicación web llamada **PeliculasApp**. La aplicación permite a los usuarios llevar el registro de su progreso al ver series, películas y leer libros.

  

## 📁 Descripción General del Repositorio

  

Este proyecto incluye 5 colecciones principales, cada una representada por un archivo `.json`:

| Archivo | Colección | Descripción |
|---|---|---|
| usuarios.json | `usuarios` | Información de los usuarios registrados, incluyendo su nombre, correo, teléfono y listas personalizadas. |
| recursos.json | `recursos` | Contiene los recursos multimedia como libros, series y películas con detalles como formato, género y plataforma. |
| listas.json | `listas` | Listas personalizadas de recursos creadas por cada usuario. |
| historial.json | `historial` | Registro de progreso de los usuarios con cada recurso (estado, fecha de inicio y fin). |
| reseñas.json | `reseñas` | Reseñas y valoraciones hechas por los usuarios sobre los recursos. |

## 🗂 Estructura de la Base de Datos

### 📦 usuarios
- `_id`: ObjectId
- `nombre`: string
- `correo`: string
- `telefono`: string
- `listas`: [ObjectId]

### 🎬 recursos
- `_id`: ObjectId
- `titulo`: string
- `formato`: string (Libro, Película, Serie)
- `genero`: string
- `plataforma`: string
- `anio`: number
- `tags`: [string]

### 📋 listas
- `_id`: ObjectId
- `id_usuario`: ObjectId
- `nombre`: string
- `descripcion`: string
- `recursos`: [ObjectId]

### 📖 historial
- `_id`: ObjectId
- `id_usuario`: ObjectId
- `id_recurso`: ObjectId
- `estado`: string (pendiente, en progreso, terminado)
- `fecha_inicio`: date
- `fecha_fin`: date (opcional)

### ⭐ reseñas
- `_id`: ObjectId
- `id_usuario`: ObjectId
- `id_recurso`: ObjectId
- `comentario`: string
- `nota`: number (1 a 5)
- `fecha`: date


## 🧾 Comandos para Importar los Archivos en MongoDB

  

Para importar las colecciones en tu base de datos MongoDB local, usa los siguientes comandos:

  

```bash

mongoimport  --db  mis_recursos_app  --collection  usuarios  --file  usuarios.json  --jsonArray

mongoimport  --db  mis_recursos_app  --collection  recursos  --file  recursos.json  --jsonArray

mongoimport  --db  mis_recursos_app  --collection  listas  --file  listas.json  --jsonArray

mongoimport  --db  mis_recursos_app  --collection  historial  --file  historial.json  --jsonArray

mongoimport  --db  mis_recursos_app  --collection  reseñas  --file  reseñas.json  --jsonArray

```

  

Asegúrate de ubicarte en la carpeta donde estén los archivos `.json` descargados antes de ejecutar los comandos.

  

## ✅ Requisitos


- [x] Relación entre usuarios y sus recursos (vía historial y listas).

- [x] Sistema de reseñas y valoración.

- [x] Modelado coherente y con datos realistas.

- [x] Al menos 50 registros en las colecciones principales.

  

---
## 📌 Autor
- Anylorena Torres Ávila





---
Realizado como parte del taller de **Bases de Datos No Relacionales** – MongoDB
