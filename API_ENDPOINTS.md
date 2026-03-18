# API Endpoints Documentation

## Authentication

### Login
- **Endpoint:** `/api/auth/login`
- **Method:** POST
- **Request Body:**
  ```json
  {
    "username": "string",
    "password": "string"
  }
  ```
- **Response:**
  - **200 OK**
    ```json
    {
      "token": "string",
      "expiresIn": "number"
    }
    ```
  - **401 Unauthorized**
    ```json
    {
      "error": "Invalid credentials"
    }
    ```

## Packages

### Get All Packages
- **Endpoint:** `/api/packages`
- **Method:** GET
- **Response:**
  - **200 OK**: 
    ```json
    [
      {
        "id": "string",
        "name": "string",
        "description": "string",
        "price": "number"
      }
    ]
    ```

### Create Package
- **Endpoint:** `/api/packages`
- **Method:** POST
- **Request Body:**
  ```json
  {
    "name": "string",
    "description": "string",
    "price": "number"
  }
  ```
- **Response:**
  - **201 Created**
    ```json
    {
      "id": "string"
    }
    ```

## Orders

### Create Order
- **Endpoint:** `/api/orders`
- **Method:** POST
- **Request Body:**
  ```json
  {
    "packageId": "string",
    "quantity": "number"
  }
  ```
- **Response:**
  - **201 Created**
    ```json
    {
      "orderId": "string",
      "status": "string"
    }
    ```

## Wallets

### Get Wallet Balance
- **Endpoint:** `/api/wallet/balance`
- **Method:** GET
- **Response:**
  - **200 OK**
    ```json
    {
      "balance": "number"
    }
    ```

### Add Funds
- **Endpoint:** `/api/wallet/add`
- **Method:** POST
- **Request Body:**
  ```json
  {
    "amount": "number"
  }
  ```
- **Response:**
  - **200 OK**
    ```json
    {
      "message": "Funds added successfully"
    }
    ```

## QR Code Management

### Generate QR Code
- **Endpoint:** `/api/qr/generate`
- **Method:** POST
- **Request Body:**
  ```json
  {
    "data": "string"
  }
  ```
- **Response:**
  - **200 OK**
    ```json
    {
      "qrCodeUrl": "string"
    }
    ```
