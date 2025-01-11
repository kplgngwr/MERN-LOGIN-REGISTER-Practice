# Login/Register with Authentication

This project is a full-stack application that provides user registration and login functionality with authentication. The frontend is built with React, and the backend is built with Node.js, Express, and MongoDB Atlas.

## Project Structure
```
## Project Structure

The project is divided into two main parts:

1. **Frontend**: Located in the `client` directory, built with React.
2. **Backend**: Located in the `server` directory, built with Node.js, Express, and MongoDB Atlas.

## Prerequisites

Make sure you have the following installed on your machine:

- Node.js
- npm (Node Package Manager)
- MongoDB Atlas account

## Installation

1. **Clone the repository**:
    ```bash
    git clone https://github.com/your-username/register_or_login-page.git
    cd register_or_login-page
    ```

2. **Install dependencies for the backend**:
    ```bash
    cd server
    npm install
    ```

3. **Install dependencies for the frontend**:
    ```bash
    cd ../client
    npm install
    ```

## Configuration

1. **Backend**:
    - Create a `.env` file in the `server` directory and add the following environment variables:
        ```
        PORT=5000
        MONGO_URI=your_mongodb_atlas_connection_string
        JWT_SECRET=your_jwt_secret
        ```

2. **Frontend**:
    - Create a `.env` file in the `client` directory and add the following environment variables:
        ```
        REACT_APP_API_URL=http://localhost:5000
        ```

## MongoDB Atlas Configuration

To connect your application to MongoDB Atlas, follow these steps:

1. **Update MongoDB connection string**:
    - Open the `server/config/db.js` file and update the `MONGO_URI` with your MongoDB Atlas connection string.

    ```javascript
    const mongoose = require('mongoose');

    const connectDB = async () => {
        try {
            const conn = await mongoose.connect(process.env.MONGO_URI, {
                useNewUrlParser: true,
                useUnifiedTopology: true,
                useCreateIndex: true,
            });

            console.log(`MongoDB Connected: ${conn.connection.host}`);
        } catch (error) {
            console.error(`Error: ${error.message}`);
            process.exit(1);
        }
    };

    module.exports = connectDB;
    ```

2. **Environment Variables**:
    - Ensure you have the `MONGO_URI` variable set in your `.env` file located in the `server` directory.

    ```
    PORT=5000
    MONGO_URI=your_mongodb_atlas_connection_string
    JWT_SECRET=your_jwt_secret
    ```

By following these steps, your application will be configured to use MongoDB Atlas for database operations.


## Running the Application

1. **Start the backend server**:
    ```bash
    cd server
    npm start
    ```

2. **Start the frontend development server**:
    ```bash
    cd ../client
    npm start
    ```

3. Open your browser and navigate to `http://localhost:3000` to see the application running.

## Features

- User registration with email and password
- User login with email and password
- Authentication using JWT (JSON Web Tokens)
- Protected routes for authenticated users

## License

This project is licensed under the MIT License.
```