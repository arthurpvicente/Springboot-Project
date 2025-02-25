# Spring Boot API

## Overview

This is a simple CRUD (Create, Read, Update, Delete) API for managing products. It is built using Spring Boot and leverages JPA for database interactions. The project also includes HATEOAS for adding links to the responses.

## Features

- Create a new product
- Retrieve all products
- Retrieve a single product by ID
- Update an existing product by ID
- Delete a product by ID

## Technologies Used

- Java 11
- Spring Boot 2.7.x
- Spring Data JPA
- H2 Database (for development and testing)
- HATEOAS
- Maven
- Jakarta Validation

## Prerequisites

- JDK 11 or higher
- Maven 3.6.0 or higher

## Getting Started

### Clone the repository

```sh
git clone https://github.com/yourusername/spring-boot-product-api.git
cd spring-boot-product-api
```
## Building and Running the Application

### Step 1: Build the Spring Boot Aplication
- Before building he Docker image, you need to package your Spring Boot application into a JAR file. Use Maven to build the JAR file.

```sh
mvn clean package
```

### Step 2: Build and Run the Docker Containers
```sh
docker-compose up --build
```
This command will:

1. Build the Docker image for the Spring Boot application using the Dockerfile.
2. Start the PostgreSQL container.
3. Start the Spring Boot application container.

### Step 3: Access the Application
- Once the containers are up and running, you can access the Spring Boot application at `http://localhost:8080`

## Testing the API with Postman

- To test the API endpoints of the Spring Boot application, you can use Postman. Below are the details for each endpoint:

### Base URL

- The base URL for the API is: `http://localhost:8080`

### Endpoints

1. ***Get All Products***

   - **URL:** `GET /products`
   - **Description:** Retrieves a list of all products.
   - **Response Code:** 200 OK

2. ***Get a Single Product***
    - **URL:** `GET /products/{id}`
    - **Description:** Retrieves a single product by its ID.
    - **Path Parameter:** id (UUID of the product)
    - **Response Code:** 200 OK, 404 Not Found (if product not found)

    **Example Request:**
    ```http
    GET http://localhost:8080/products/{id}
    ```
    Replace `{id}` with the actual UUID of the product you want to retrieve.

3. ***Create a New Product***
    - **URL:** `POST /products`
    - **Description:** Creates a new product
    - **Request Body:** 
    ```json
    {
        "name": "Product Name",
        "value": 89.99
    }
    ```
    - **Response Code:** 201 Created
    
    **Example Request:**
    ```http
    POST http://localhost:8080/products
    ```
4. ***Update an Existing Product***
    - **URL:** `PUT /products/{id}`
    - **Description:** Updates an existing product by its ID.
    - **Path Parameter:** id (UUID of the product)
    - **Request Body:**
    ```json
        {
            "name": "Updated Product Name",
            "value": 89.99
        }
    ```
    - **Response Code:** 200 OK, 404 Not Found (if product not found)
    
    **Example Request:**
    ```http
    PUT http://localhost:8080/products/{id}
    ```
5. ***Delete a Product***
    - **URL:** `DELETE /products/{id}`
    - **Description:** Deletes a product by its ID.
    - **Path Parameter:** id (UUID of the product)
    - **Response Code:** 204 No Content, 404 Not Found (if product not found)
    
    **Example Request:**
    ```http
    DELETE http://localhost:8080/products/{id}
    ```

## Author

This project created by Arthur Vicente.
