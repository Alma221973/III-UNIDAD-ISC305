
# III-UNIDAD-ISC305

## API REST de Personas con Laravel

Proyecto desarrollado para la asignatura ISC-305 Programación Web.

El proyecto consiste en una API REST que permite registrar, consultar, actualizar y eliminar personas, utilizando Laravel, MySQL y respuestas en formato JSON.

## Tecnologías utilizadas

- Laravel 13
- PHP 8.4
- MySQL
- Composer
- Postman
- Git y GitHub

## Requisitos

- PHP 8.4.1 o superior, compatible con las dependencias del proyecto.
- Composer 2.
- MySQL.
- Git.
- Postman.

## Instalación del proyecto

Clonar el repositorio:

```bash
git clone https://github.com/Alma221973/III-UNIDAD-ISC305.git
cd III-UNIDAD-ISC305/backend
composer install
```

Crear el archivo de configuración en Windows:

```powershell
Copy-Item .env.example .env
```

Generar la clave de la aplicación:

```bash
php artisan key:generate
```

## Configuración de la base de datos

Crear la base de datos en MySQL:

```sql
CREATE DATABASE isc305_unidad3
CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
```

Configurar las siguientes variables en el archivo .env:

```env
APP_NAME="API Personas ISC305"
APP_URL=http://127.0.0.1:8000

DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=isc305_unidad3
DB_USERNAME=TU_USUARIO_MYSQL
DB_PASSWORD=TU_CONTRASENA

SESSION_DRIVER=file
CACHE_STORE=file
QUEUE_CONNECTION=sync
```

Utilizar las credenciales correspondientes a la instalación local de MySQL.

Ejecutar las migraciones:

```bash
php artisan config:clear
php artisan migrate
```

## Ejecutar el proyecto

```bash
php artisan serve
```

URL base:

http://127.0.0.1:8000/api

## Endpoints de la API

| Método | Endpoint | Descripción |
|---|---|---|
| GET | /api/hola | Mensaje de bienvenida |
| GET | /api/personas | Mostrar todas las personas |
| GET | /api/personas/{id} | Consultar una persona |
| POST | /api/personas | Crear una persona |
| PUT | /api/personas/{id} | Actualizar una persona |
| DELETE | /api/personas/{id} | Eliminar una persona |

## Ejemplo de datos JSON

```json
{
    "dni": "0000000000001",
    "nombre": "Ana López",
    "fecha_nacimiento": "2000-05-15"
}
```

## Validaciones

- Todos los campos son obligatorios.
- El DNI debe contener exactamente 13 dígitos.
- No se permiten DNI duplicados.
- El nombre admite un máximo de 100 caracteres.
- La fecha de nacimiento debe ser válida y no puede ser futura.
- Al actualizar, una persona puede conservar su propio DNI.

## Códigos de respuesta HTTP

| Código | Descripción |
|---|---|
| 200 | Consulta o actualización exitosa |
| 201 | Registro creado correctamente |
| 204 | Registro eliminado correctamente |
| 404 | Registro no encontrado |
| 422 | Error de validación |

## Pruebas con Postman

Las operaciones de la API se pueden probar utilizando la colección ubicada en la carpeta postman del repositorio.

Las peticiones deben incluir el encabezado:

Accept: application/json

Las peticiones POST y PUT también deben incluir:

Content-Type: application/json

La API se utiliza localmente con datos ficticios y todavía no cuenta con autenticación.

## Asignatura

ISC-305 - Programación Web

III Unidad - Desarrollo de API REST con Laravel.
