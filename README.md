# Guía 3.1.2  API REST con Spring Boot y Swagger

Desarrollo FullStack II

API REST básica que realiza operaciones CRUD sobre una entidad `Book` (libro), documentada con Swagger UI.

## Tecnologías

- Java 17
- Spring Boot 2.5.5
- Spring Web
- Spring Data JPA
- Base de datos H2 (en memoria)
- Springfox 3.0.0 (Swagger)
- Maven

> Se usa Spring Boot 2.5.5 porque Springfox 3.0.0 no es compatible con versiones más nuevas de Spring Boot.

## Requisitos previos

- JDK 17 instalado (con Java 21 o superior puede fallar con esta versión de Spring Boot)
- Un IDE (el proyecto se desarrolló en VS Code con el Extension Pack for Java)


## Estructura del proyecto

```
src/main/java/com/example/demo/
├── DemoApplication.java
├── SwaggerConfig.java
├── controller/
│   └── BookController.java
├── model/
│   └── Book.java
├── repository/
│   └── BookRepository.java
└── service/
    └── BookService.java
```

## Endpoints

| Método | Ruta              | Descripción                |
|--------|-------------------|----------------------------|
| GET    | `/api/books`      | Lista todos los libros     |
| GET    | `/api/books/{id}` | Obtiene un libro por su id |
| POST   | `/api/books`      | Crea un libro nuevo        |
| PUT    | `/api/books/{id}` | Actualiza un libro         |
| DELETE | `/api/books/{id}` | Elimina un libro           |

Ejemplo de cuerpo para POST y PUT (el `id` se genera automáticamente):

```json
{
  "title": "Cien años de soledad",
  "author": "Gabriel García Márquez"
}
```

## Base de datos

La aplicación usa H2 en memoria: **los datos se pierden al detener la aplicación**.

Consola H2: [http://localhost:8080/h2-console](http://localhost:8080/h2-console)

- JDBC URL: `jdbc:h2:mem:testdb`
- Usuario: `sa`
- Contraseña: `password`

## Documentación de la API

- Swagger UI: [http://localhost:8080/swagger-ui/](http://localhost:8080/swagger-ui/)
- Especificación: [http://localhost:8080/v2/api-docs](http://localhost:8080/v2/api-docs)

## Autora

Claudia González – Duoc UC
