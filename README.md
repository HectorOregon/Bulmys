# Proyecto: Bulmys

## Descripción
En este proyecto se intentara codificar y armar un programa funcional y eficiente enfocado en la visualizacion
y reproduccion de albumes y mixtapes dentro de la indusria musical ya sea mainstream o underground

## Motivación
intentar recrear un antiguo programa realizadohace ya un par de años pero mejorado y optimizado aprovechando los conocimientos adquiridos a los largo del tiempo.

## Tech Stack
- Lenguaje de programación: C or java
- Editor de código: Visual Studio Code o derivado
- Control de versiones: Git y GitHub  
- Base de datos: MySQL

- Nota: como el proyecto esta en fase de planeacion el Tech Stack esta sujeto a cambios.

## Normalización de la Base de Datos

Para el diseño de la base de datos se aplicaron las siguientes formas normales:

**Primera Forma Normal (1FN):**  
Se aseguró que todos los campos tengan valores atómicos y que cada tabla tenga una clave primaria.

**Segunda Forma Normal (2FN):**  
Se eliminaron dependencias parciales separando la información en diferentes tablas, como la tabla Reproduccion para registrar las reproducciones de canciones.

**Tercera Forma Normal (3FN):**  
Se eliminaron dependencias transitivas. Por ejemplo, la información del artista se almacena únicamente en la tabla Artista y se relaciona mediante claves foráneas con Álbum y Canción.

# Diccionario de Datos

## Tabla: Usuario

| Campo | Tipo de dato | Clave | Descripción |
|------|--------------|------|-------------|
| id_usuario | INT | PK | Identificador único del usuario |
| nombre | VARCHAR | — | Nombre del usuario |
| email | VARCHAR | — | Correo electrónico del usuario |
| contraseña | VARCHAR | — | Contraseña del usuario |


## Tabla: Artista

| Campo | Tipo de dato | Clave | Descripción |
|------|--------------|------|-------------|
| id_artista | INT | PK | Identificador único del artista |
| nombre | VARCHAR | — | Nombre del artista o grupo |


## Tabla: Album

| Campo | Tipo de dato | Clave | Descripción |
|------|--------------|------|-------------|
| id_album | INT | PK | Identificador del álbum |
| id_artista | INT | FK | Artista al que pertenece el álbum |
| titulo | VARCHAR | — | Título del álbum |


## Tabla: Cancion

| Campo | Tipo de dato | Clave | Descripción |
|------|--------------|------|-------------|
| id_cancion | INT | PK | Identificador de la canción |
| id_artista | INT | FK | Artista que interpreta la canción |
| id_album | INT | FK | Álbum al que pertenece la canción |
| titulo | VARCHAR | — | Título de la canción |
| duracion | TIME | — | Duración de la canción |


## Tabla: Reproduccion

| Campo | Tipo de dato | Clave | Descripción |
|------|--------------|------|-------------|
| id_reproduccion | INT | PK | Identificador de la reproducción |
| id_usuario | INT | FK | Usuario que reproduce la canción |
| id_cancion | INT | FK | Canción reproducida |
| fecha | DATETIME | — | Fecha y hora en que se realizó la reproducción |
