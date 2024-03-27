
# Online Restaurant Service REST API

This is a REST API for a hypothetical online restaurant service. It allows users to perform CRUD operations on products, place orders, and view orders.

## Use Case

1. **Create, Read, Update, Delete Product**: Users can perform CRUD operations on products. Each product has a name, price, and description.
2. **Place Order for a Product**: Users can place orders for products, specifying the product and quantity.
3. **List All Orders**: Users can view all orders placed.

## Environment Variables

To run the server, create a `.env` file in the project directory with the following format:

```
MONGODB_URL=mongodb://localhost:27017/restaurant_db
PORT=3000
JWT_SECRET=your_secret_key
```

- `MONGODB_URL`: The URL of your MongoDB database.
- `PORT`: The port number for the server to listen on.
- `JWT_SECRET`: Secret key used for signing JWT tokens.

## Running the Server

1. Install dependencies:

   ```bash
   npm install
   ```

2. Start MongoDB server:

   ```bash
   mongod
   ```

3. Start the server:

   ```bash
   node server.js
   ```

## API Endpoints

- **POST /register**: Register a new user.
- **POST /login**: Login with username and password to get JWT token.
- **POST /products**: Create a new product.
- **GET /products**: Get all products.
- **PUT /products/:id**: Update a product by ID.
- **DELETE /products/:id**: Delete a product by ID.
- **POST /orders**: Place a new order.
- **GET /orders**: Get all orders.

## Sample Requests

- **Register User**:

   ```bash
   curl -X POST -H "Content-Type: application/json" -d '{"username":"your_username", "password":"your_password"}' http://localhost:3000/register
   ```

- **Login**:

   ```bash
   curl -X POST -H "Content-Type: application/json" -d '{"username":"your_username", "password":"your_password"}' http://localhost:3000/login
   ```

- **Create Product**:

   ```bash
   curl -X POST -H "Authorization: Bearer <your_token>" -H "Content-Type: application/json" -d '{"name":"Product Name", "price":10, "description":"Product Description"}' http://localhost:3000/products
   ```

- **List Products**:

   ```bash
   curl http://localhost:3000/products
   ```

- **Place Order**:

   ```bash
   curl -X POST -H "Authorization: Bearer <your_token>" -H "Content-Type: application/json" -d '{"product":"<product_id>", "quantity":1}' http://localhost:3000/orders
   ```

- **List Orders**:

   ```bash
   curl -H "Authorization: Bearer <your_token>" http://localhost:3000/orders
   ```

Replace `<your_username>`, `<your_password>`, `<your_token>`, and `<product_id>` with appropriate values.
```

