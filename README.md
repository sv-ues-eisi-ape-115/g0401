## Paso 1 - Instalar sqlite3 y preparar el directorio de trabajo
Actualizar lista de paquetes e instalar sqlite3

$ sudo apt update && sudo apt install -y sqlite3

Verificar la instalación

$ sqlite3 --version

Crear el directorio de trabajo del laboratorio

$ mkdir -p ~/lab_g0401/cafeteria

$ cd ~/lab_g0401/cafeteria

$ pwd
/home/alumno/lab_g0401/cafeteria
## Paso 2 - Crear el archivo DDL — ddl.sql

Crea el archivo ddl.sql con el editor de tu preferencia (nano, vim, gedit). Este archivo define toda la estructura de la BD

nano ddl.sql

$ sqlite3 ape115_cafeteria.db < ddl.sql

Tablas creadas: 5

 Verificar desde el cliente interactivo

$ sqlite3 ape115_cafeteria.db

sqlite> .tables

sqlite> .schema producto

...

sqlite> .quit

PRAGMA foreign_keys — punto crítico de SQLite: SQLite deshabilita las claves foráneas por defecto para compatibilidad histórica.

Debes escribir PRAGMA foreign_keys = ON; al inicio de CADA sesión o script.
En Java (G0402) se activa una vez al abrir cada Connection con el DAO.

## Paso 3 - Crear el archivo de datos — dml_insert.sql

nano dml_insert.sql
$ sqlite3 ape115_cafeteria.db < dml_insert.sql

Datos insertados OK

Productos: 15

Clientes: 5

Ventas: 5

## Paso 4 - Consultas SELECT — DML básico y avanzado

Crea el archivo consultas_basicas.sql y ejecuta cada sección:

$ sqlite3 ape115_cafeteria.db < consultas_basicas.sql

Regla de oro — Nunca UPDATE/DELETE sin WHERE: Antes de ejecutar un UPDATE o DELETE, transfórmalo en SELECT con los mismos filtros.

Verifica cuántas filas devuelve. Si el número es correcto, ejecuta el UPDATE/DELETE.
En SQLite puedes activar el modo seguro con: PRAGMA secure_delete = ON;
## Paso 5 - GROUP BY, HAVING y funciones de agregación

consultas_agrupadas.sql

$ sqlite3 ape115_cafeteria.db < consultas_agrupadas.sql
## Paso 6 - Subconsultas — Tres tipos
subconsultas.sql

$ sqlite3 ape115_cafeteria.db < subconsultas.sql
## Paso 7 - Vistas y Triggers con sintaxis SQLite

objetos.sql

$ sqlite3 ape115_cafeteria.db < objetos.sql


## Paso 8 - Índices y optimización — PRAGMA explain

indices.sql

$ sqlite3 ape115_cafeteria.db < indices.sql




