# PracticaSpringProductosParte1

# API REST CRUD - Spring Boot + MySQL

## Descripción
Esta API RESTful ha sido desarrollada en el contexto del Módulo Profesional 3 (Programación), dentro de la práctica M3 - UF6. Permite realizar operaciones CRUD (Crear, Leer, Actualizar y Eliminar) sobre una tabla de productos almacenada en una base de datos MySQL.

## Tecnologías utilizadas
- Java 17
- Spring Boot 3.x
- Spring Data JPA
- MySQL 8.x
- Postman (para pruebas)

## Configuración de la base de datos

1. Crear la base de datos en MySQL:
```sql
CREATE DATABASE productos_db;
```

2. Configurar las credenciales de acceso en el archivo:
`src/main/resources/application.properties`

```
spring.datasource.url=jdbc:mysql://localhost:3306/productos_db
spring.datasource.username=TU_USUARIO
spring.datasource.password=TU_CONTRASEÑA

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
server.port=8081
```

## Cómo ejecutar el proyecto

1. Clonar el repositorio o descargar el código fuente.
2. Abrir el proyecto en IntelliJ IDEA u otro IDE compatible con Spring Boot.
3. Ejecutar la clase principal: `CrudApiApplication.java`
4. Acceder a la API desde: `http://localhost:8081/api/productos`

## Endpoints disponibles

| Método | URL                          | Descripción                    |
|--------|------------------------------|--------------------------------|
| GET    | /api/productos               | Lista todos los productos      |
| GET    | /api/productos/{id}          | Consulta un producto por ID    |
| POST   | /api/productos               | Crea un nuevo producto         |
| PUT    | /api/productos/{id}          | Actualiza un producto existente|
| DELETE | /api/productos/{id}          | Elimina un producto por ID     |

## Pruebas realizadas

Las pruebas se realizaron utilizando Postman y validan que cada operación CRUD funciona correctamente:

- ✔ `GET /api/productos` devuelve `200 OK` y lista de productos.
- ✔ `POST /api/productos` crea un producto y devuelve `200 OK` o `201 Created`.
- ✔ `GET /api/productos/{id}` devuelve `200 OK` o `404 Not Found`.
- ✔ `PUT /api/productos/{id}` actualiza un producto correctamente.
- ✔ `DELETE /api/productos/{id}` elimina el producto con código `204 No Content`.

Se adjunta el documento `Pruebas_API_Productos.pdf` con la descripción de los tests.

## Autor
Carlos Palomino – Equipo 1 (API & Base de Datos)  
Profesor/a: Carmen Quintás



# PracticaSpringProductosParte2

## Cliente Java Swing - Consumo de API REST

## Descripción
Cliente de escritorio desarrollado en Java (Swing) que se conecta a la API REST de productos para permitir la gestión visual (CRUD) de los datos.

## Tecnologías utilizadas
- Java 17
- Java Swing
- HTTP Client (Java 11+)
- Jackson (para manejar JSON)

## Requisitos previos
- Tener la API ejecutándose en `http://localhost:8081/api/productos`
- Tener configurado Java 11 o superior
- Jackson en el classpath (`com.fasterxml.jackson.core:jackson-databind`)

## Funcionalidades del cliente

| Acción     | Método HTTP | Endpoint REST                | Descripción                            |
|------------|-------------|------------------------------|----------------------------------------|
| Listar     | GET         | /api/productos               | Muestra todos los productos            |
| Crear      | POST        | /api/productos               | Añade un nuevo producto                |
| Actualizar | PUT         | /api/productos/{id}          | Modifica el producto seleccionado      |
| Eliminar   | DELETE      | /api/productos/{id}          | Elimina el producto seleccionado       |

## Cómo ejecutar el cliente

1. Abrir el archivo `ClienteApp.java` y ejecutar el método `main()`.
2. Interactuar con la interfaz gráfica:
   - Ver lista de productos.
   - Añadir nuevos productos.
   - Editar productos seleccionados.
   - Eliminar productos seleccionados.

## Autor
Biel Fernández – Equipo 2 (Cliente gráfico)
