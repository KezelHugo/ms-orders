# ms-orders - Gestión de Órdenes de Compra

> Este microservicio es parte del proyecto original: [Repositorio principal](https://github.com/KezelHugo/parcial)
> 
> En el repositorio original están la colección de Postman y el informe de Sonar.

`ms-orders` permite crear órdenes de compra asociadas a productos, validar stock remotamente y consultar órdenes por cliente.

---

## Cómo ejecutar el microservicio

### Requisitos

- Java 17+
- Maven
- MySQL

### Base de datos

Ambos microservicios usan la misma base de datos (`parcial_db`). Solo necesitas crearla una vez:

```sql
CREATE DATABASE parcial_db;
```

### Ejecutar

```bash
cd msorders
mvn spring-boot:run
```

O ejecuta `Application.java` desde tu IDE.

---

## Endpoints principales

| Método | Endpoint                              | Descripción                          |
|--------|---------------------------------------|--------------------------------------|
| POST   | `/orders`                             | Crear una orden de compra            |
| GET    | `/orders/search?customer=kevin`       | Buscar órdenes por cliente           |

---

## Funcionalidades

- Crear órdenes con múltiples productos.
- Validación de stock vía `ms-products`.
- Consulta de órdenes por cliente.
- Manejo de errores y mensajes claros.

---

## Patrones aplicados

- **Builder Pattern** en entidades y DTOs.
- **Circuit Breaker** con `Resilience4j` para consultas al microservicio `ms-products`.
- **Fallback methods** en caso de fallo de red.
- **Validaciones** con `@Valid`, `@NotBlank`, etc.
- **Excepciones personalizadas**.

---

## Autor

Kevin Benjamin Sosa León
