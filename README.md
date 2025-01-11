# Login/Register with Authentication

This project is a full-stack application that provides user registration and login functionality with authentication. The frontend is built with React, and the backend is built with Node.js, Express, and MongoDB Atlas.

## Project Structure

The project is divided into two main parts:

1. **Frontend**: Located in the `frontend` directory, built with React.
2. **Backend**: Located in the `backend` directory, built with Node.js, Express, and MongoDB Atlas.

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
    cd backend
    npm install
    ```

3. **Install dependencies for the frontend**:
    ```bash
    cd frontend
    npm install
    ```

## MongoDB Atlas Configuration

To connect your application to MongoDB Atlas, follow these steps:

1. **Update MongoDB connection string**:
    - Open the `backend/config/db.js` file and update the `MONGO_URI` with your MongoDB Atlas connection string.

    ```javascript
    const { MongoClient, ServerApiVersion } = require('mongodb');
    const uri = "<Your_MONGO_URI>";

    // Create a MongoClient with a MongoClientOptions object to set the Stable API version
    const client = new MongoClient(uri, {
    serverApi: {
        version: ServerApiVersion.v1,
        strict: true,
          deprecationErrors: true,
    }
    });

    const connectDB = async () => {
    try {
        // Connect the client to the server (optional starting in v4.7)
        await client.connect();
        // Send a ping to confirm a successful connection
        await client.db("admin").command({ ping: 1 });
        console.log("Pinged your deployment. You successfully connected to MongoDB!");
    } catch (err) {
        console.error(err.message);
        process.exit(1);
    }
    };

    module.exports = { connectDB, client };
    ```
By following these steps, your application will be configured to use MongoDB Atlas for database operations.


## Running the Application

1. **Start the backend server**:
    ```bash
    cd backend
    node server.js
    ```

2. **Start the frontend development server**:
    ```bash
    cd frontend
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