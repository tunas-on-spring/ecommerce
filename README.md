# eCommerce Shop - Spring Boot

## Introduction

The **eCommerce Shop** project is an e-commerce system built with **Spring Boot**, featuring a modular architecture to manage products, orders, carts, payments, and notifications. The system is designed for scalability and seamless integration with external services.

## Technologies Used

- **Spring Boot** (v3.x) - Core framework
- **Spring Data JPA** - ORM and database interaction
- **Spring Security** - Authentication & authorization
- **Spring Cloud** - Microservices support (if applicable)
- **AWS SDK v2** - Image storage management
- **PostgreSQL** - Main database
- **Redis** - Caching
- **RabbitMQ/Kafka** - Asynchronous event processing
- **Flyway** - Database migration management
- **LocalStack** - Local AWS service emulation for development

## System Architecture

The project follows a **multi-module** architecture with key modules:

- `common`: Contains shared interfaces, DTOs, and utilities
- `product-service`: Manages products, categories, and inventory
- `order-service`: Handles orders, payments, and shipping
- `notification-service`: Manages emails and notifications
- `user-service`: Handles authentication and user management

## Installation & Running the Application

### 1. System Requirements

- **JDK 17**
- **Maven 3.8+**
- **Docker**
- **PostgreSQL 15+**
- **Redis**
- **LocalStack (for AWS emulation)**

### 2. Environment Configuration

Create a `.env` file in the [docker](docker) directory:

```
DB_URL=jdbc:postgresql://localhost:5432/ecommerce
DB_USERNAME=admin
DB_PASSWORD=secret
REDIS_HOST=localhost
REDIS_PORT=6379
AWS_ACCESS_KEY_ID=test
AWS_SECRET_ACCESS_KEY=test
AWS_REGION=us-east-1
AWS_ENDPOINT_URL=http://localhost:4566
```

### 3. Running the Application

#### Option 1: Run with Maven

```sh
mvn clean install
mvn spring-boot:run
```

#### Option 2: Run with Docker Compose (if configured)

```sh
docker-compose up --build
```

### 4. Running LocalStack (AWS Emulation)

If you are using **LocalStack** for AWS services (S3, SNS, SQS, etc.), start it using:

```sh
docker run --rm -it -p 4566:4566 localstack/localstack
```

### 5. Database Migration

This project uses **Flyway** for database migration. Migrations are automatically applied on application startup. To manually run Flyway migrations, use:

```sh
mvn flyway:migrate
```

## API Documentation

This project uses **Swagger** for API documentation. Once the application is running, you can access the API documentation at:

```
http://localhost:8080/swagger-ui.html
```

## Contribution

Contributions are welcome! Please fork the repository, create a pull request, and provide a clear description of your changes.

## License

This project is released under the **MIT License**. See the `LICENSE` file for more details.

---
## Contact

**[Mail](mailto:tuantohoang115@example.com)**

