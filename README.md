# Microservices Demo

## Overview

This project demonstrates a microservices architecture with various services interacting through message broker and HTTP requests. The microservices covered in this tutorial include Shopping, Customer, and Products services.

## Prerequisites

- Node.js (v14.x or later)
- Docker
- Kubernetes (optional)
- Postman (for API testing)

## Services

### Shopping Service

The Shopping Service handles operations related to shopping cart and orders.

- **Base URL**: `{{SHOPPING_BASE}}`
- **Endpoints**:
  - `GET /shopping/cart`: Retrieve the current shopping cart.
  - `POST /shopping/order`: Create a new order.
  - `GET /shopping/orders`: Retrieve all orders.

### Customer Service

The Customer Service manages customer-related functionalities, including signup, login, profile management, and wishlist.

- **Base URL**: `{{CUSTOMER_BASE}}`
- **Endpoints**:
  - `POST /customer/signup`: Signup a new customer.
  - `POST /customer/login`: Customer login.
  - `GET /customer/profile`: Retrieve customer profile.
  - `GET /customer/shoping-details`: Get customer shopping details.
  - `POST /customer/address`: Add a new address for the customer.
  - `GET /customer/wishlist`: Retrieve customer wishlist.

### Products Service

The Products Service handles product management, including creating, viewing, and categorizing products.

- **Base URL**: `{{PRODUCTS_BASE}}`
- **Endpoints**:
  - `POST /product/create`: Create a new product.
  - `POST /ids`: Retrieve selected products by IDs.
  - `GET /category/:category`: Get products by category.
  - `GET /`: View all products.
  - `GET /:id`: Get product details by ID.
  - `PUT /wishlist`: Add a product to the wishlist.
  - `PUT /cart`: Add a product to the cart.
  - `DELETE /cart/:id`: Delete a product from the cart.
  - `DELETE /wishlist/:id`: Remove a product from the wishlist.

## Authentication

The services use Bearer token authentication. Include the token in the `Authorization` header of your requests:

```
Authorization: Bearer <your-token>
```

## Setup

### Step 1: Clone the Repository

```bash
git clone git@github.com:rishi-simform/microservices-demo.git
cd microservices-demo
```

### Step 2: Install Dependencies

Navigate to each service directory and install the dependencies:

```bash
cd shopping-service
npm install

cd ../customer-service
npm install

cd ../products-service
npm install
```

### Step 3: Environment Variables

Create a `.env` file in each service directory with the following variables:

#### shopping-service/.env

```
PORT=3001
DB_URL=<database-url>
```

#### customer-service/.env

```
PORT=3002
DB_URL=<database-url>
```

#### products-service/.env

```
PORT=3003
DB_URL=<database-url>
```

### Step 4: Run the Services

You can run each service independently:

```bash
cd shopping-service
npm start

cd ../customer-service
npm start

cd ../products-service
npm start
```

Alternatively, use Docker Compose to run all services together:

```bash
docker-compose up
```
