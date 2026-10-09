# Inventory Management System

A REST API for managing inventory, products, categories, suppliers, and stock movements. Built with Java and Spring Boot, this project provides authentication, product management, stock tracking, and low-stock alerts.

## Features

- User registration and login with JWT authentication
- Product CRUD operations
- Category and supplier management
- Product search, filtering, pagination, and sorting
- Stock movement tracking
- Low-stock alerts
- Stock movement history
- REST API documentation with Swagger UI
- Unit testing with JUnit 5 and Mockito
- Docker and Docker Compose support

## Tech Stack

| Component | Technology |
|---|---|
| Language | Java 21 |
| Framework | Spring Boot 3 |
| Database | PostgreSQL |
| Security | Spring Security, JWT |
| ORM | Spring Data JPA |
| API Documentation | SpringDoc OpenAPI, Swagger UI |
| Testing | JUnit 5, Mockito, H2 |
| Build Tool | Maven |
| Containerization | Docker, Docker Compose |

## Getting Started

### Prerequisites

- Java 21
- Maven
- PostgreSQL
- Docker (optional)

### Clone the Repository

```bash
git clone https://github.com/RudraSingh17/inventory-management-system.git
cd inventory-management-system
```

### Run with Docker

```bash
docker-compose up --build
```

### Run Locally

Configure your PostgreSQL database and set the environment variables:

```bash
export DATABASE_URL=jdbc:postgresql://localhost:5432/inventory
export DB_USER=postgres
export DB_PASSWORD=your_password
export JWT_SECRET=your_base64_encoded_secret
```

Start the application:

```bash
mvn spring-boot:run
```

### Run Tests

```bash
mvn test
```

## API Endpoints

| Method | Endpoint | Description |
|---|---|---|
| POST | `/api/auth/register` | Register a user |
| POST | `/api/auth/login` | Login and receive a JWT |
| GET | `/api/products` | List products |
| POST | `/api/products` | Create a product |
| GET | `/api/products/{id}` | Get a product by ID |
| PUT | `/api/products/{id}` | Update a product |
| DELETE | `/api/products/{id}` | Delete a product |
| GET | `/api/products/low-stock` | Retrieve low-stock products |
| POST | `/api/products/{id}/stock` | Record a stock movement |
| GET | `/api/products/{id}/stock` | View stock movement history |
| GET/POST/PUT/DELETE | `/api/categories` | Manage categories |
| GET/POST/PUT/DELETE | `/api/suppliers` | Manage suppliers |

## Authentication

Protected endpoints require a valid JWT token in the request header:

```http
Authorization: Bearer YOUR_JWT_TOKEN
```

## Stock Movement Types

- `RESTOCK` — Increase stock
- `SALE` — Decrease stock
- `ADJUSTMENT` — Set stock to a specified quantity
- `RETURN` — Increase stock for returned items

Each stock movement records the quantity before and after the operation.

## API Documentation

After starting the application, access Swagger UI:

http://localhost:8080/swagger-ui.html

## Repository

https://github.com/RudraSingh17/inventory-management-system

## Connect with Me

**Rudra Pratap Singh**

- GitHub: https://github.com/RudraSingh17
- LinkedIn: https://www.linkedin.com/in/rudra-pratap-singh-b930a9262/

## License

Check the applicable license and permissions before redistributing or modifying third-party code.
