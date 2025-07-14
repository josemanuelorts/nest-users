NestJS User Service

Este proyecto es un servicio REST construido con NestJS que permite crear y listar usuarios. Al crear un usuario, se validan los datos, se obtienen detalles adicionales de una API externa, y se almacenan en una base de datos SQLite ligera.

Funcionalidades

- POST /users: Crea un usuario con nombre y email.
- GET /users: Lista todos los usuarios almacenados.
- Validación de datos de entrada con DTOs y pipes.
- Obtención de datos adicionales desde API externa (https://reqres.in).
- Registro de todas las peticiones mediante middleware.
- Manejo centralizado de errores.
- Limitación de peticiones (throttling).
- Almacenamiento persistente con SQLite.

Requisitos

- Node.js (v16+ recomendado)
- npm o yarn
- SQLite (no requiere configuración extra, el archivo se crea automáticamente)

Instalación y ejecución

1. Clona el repositorio:

   git clone https://github.com/tu-usuario/nombre-del-repo.git
   cd nombre-del-repo

2. Instala las dependencias:

   npm install

3. Corre la aplicación:

   npm run start

4. La API estará disponible en http://localhost:3000

Pruebas básicas

- Crear usuario:

  curl -X POST http://localhost:3000/users -H "Content-Type: application/json" -d '{"name":"Juan","email":"juan@example.com"}'

- Listar usuarios:

  curl http://localhost:3000/users

Notas

- La base de datos SQLite se guarda en ./data/sqlite.db.
- El throttling limita el número de peticiones para evitar abusos.
- Middleware registra cada petición con método, ruta y timestamp en consola.

---
