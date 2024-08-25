
# ContosoPizza Web API

Welcome to the ContosoPizza Web API! This API allows you to manage pizza entities, including creating, reading, updating, and deleting pizza records. It utilizes ASP.NET Core with a simple architecture using controllers, models, and services.

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Prerequisites](#prerequisites)
- [Setup and Installation](#setup-and-installation)
- [Usage](#usage)
- [API Endpoints](#api-endpoints)
- [Code Structure](#code-structure)
- [Running Tests](#running-tests)
- [Contributing](#contributing)
- [License](#license)

## Overview

The ContosoPizza Web API is a minimal ASP.NET Core application designed to manage pizza data. The API follows the MVC pattern with:

- **Controllers** to handle HTTP requests.
- **Models** to represent pizza data.
- **Services** to manage business logic and data.

## Features

- **CRUD Operations**: Create, Read, Update, and Delete pizza records.
- **In-Memory Data Store**: Uses a static list to store pizza data.
- **Swagger Documentation**: API documentation for easy exploration and testing.

## Prerequisites

- [.NET SDK 6.0 or later](https://dotnet.microsoft.com/download/dotnet)
- A code editor like [Visual Studio Code](https://code.visualstudio.com/) or [Visual Studio](https://visualstudio.microsoft.com/)

## Setup and Installation

To get started with the ContosoPizza Web API, follow these steps:

1. **Clone the Repository:**

   ```bash
   git clone https://github.com/mabass2110/ContozoPizzaAPI.v2/tree/master
   ```

2. **Navigate to the Project Directory:**

   ```bash
   cd contoso-pizza-api
   ```

3. **Restore Dependencies:**

   ```bash
   dotnet restore
   ```

4. **Build the Project:**

   ```bash
   dotnet build
   ```

5. **Run the API:**

   ```bash
   dotnet run
   ```

   By default, the API will be available at `http://localhost:5000` and `https://localhost:5001`.

## Usage

Once the API is running, you can interact with it using tools like [curl](https://curl.se/), [Postman](https://www.postman.com/), or directly through your browser for GET requests.

## API Endpoints

### `GET /pizza`

- **Description:** Retrieves a list of all pizzas.
- **Response:**

  ```json
  [
    {
      "id": 1,
      "name": "Classic Italian",
      "isGlutenFree": false
    },
    {
      "id": 2,
      "name": "Veggie",
      "isGlutenFree": true
    }
  ]
  ```

### `GET /pizza/{id}`

- **Description:** Retrieves a single pizza by its `id`.
- **Response:**

  ```json
  {
    "id": 1,
    "name": "Classic Italian",
    "isGlutenFree": false
  }
  ```

### `POST /pizza`

- **Description:** Creates a new pizza.
- **Request Body:**

  ```json
  {
    "name": "New Pizza",
    "isGlutenFree": true
  }
  ```

- **Response:**

  ```json
  {
    "id": 3,
    "name": "New Pizza",
    "isGlutenFree": true
  }
  ```

### `PUT /pizza/{id}`

- **Description:** Updates an existing pizza by its `id`.
- **Request Body:**

  ```json
  {
    "id": 1,
    "name": "Updated Pizza",
    "isGlutenFree": true
  }
  ```

- **Response:**

  `204 No Content`

### `DELETE /pizza/{id}`

- **Description:** Deletes a pizza by its `id`.
- **Response:**

  `204 No Content` if successful, or `404 Not Found` if the pizza does not exist.

## Code Structure

### Controllers

**`PizzaController`**

- Handles HTTP requests related to pizza operations.
- Methods:
  - `GetAll()`: Returns all pizzas.
  - `Get(int id)`: Returns a pizza by its `id`.
  - `Create(Pizza pizza)`: Adds a new pizza.
  - `Update(int id, Pizza pizza)`: Updates an existing pizza.
  - `Delete(int id)`: Deletes a pizza.

### Models

**`Pizza`**

- Represents a pizza entity.
- Properties:
  - `Id`: Unique identifier for the pizza.
  - `Name`: Name of the pizza.
  - `IsGlutenFree`: Indicates if the pizza is gluten-free.

### Services

**`PizzaService`**

- Manages pizza data using an in-memory list.
- Methods:
  - `GetAll()`: Retrieves all pizzas.
  - `Get(int id)`: Retrieves a pizza by `id`.
  - `Add(Pizza pizza)`: Adds a new pizza.
  - `Update(Pizza pizza)`: Updates an existing pizza.
  - `Delete(int id)`: Deletes a pizza.

## Running Tests

To run unit tests, add a test project and use the following command:

```bash
dotnet test
```

## Contributing

We welcome contributions to the ContosoPizza Web API! To contribute:

1. Fork the repository.
2. Create a feature branch (`git checkout -b feature/YourFeature`).
3. Commit your changes (`git commit -am 'Add new feature'`).
4. Push to the branch (`git push origin feature/YourFeature`).
5. Open a Pull Request.

## License

This project is licensed under the [MIT License](LICENSE).

