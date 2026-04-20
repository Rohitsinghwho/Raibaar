# Backend service for Raibaar

## Packages

The following packages have been installed in this project:

- **express** (^5.2.1) - Fast, unopinionated, minimalist web framework for Node.js
- **mongoose** (^9.4.1) - Elegant MongoDB object modeling for Node.js
- **bcrypt** (^6.0.0) - Password hashing library for secure authentication
- **cookie-parser** (^1.4.7) - Parse HTTP request cookies
- **cors** (^2.8.6) - Enable CORS (Cross-Origin Resource Sharing) support
- **dotenv** (^17.4.2) - Load environment variables from .env files
- **nodemon** (^3.1.14) - Monitor for changes in source and automatically restart the server

## Folder Structure

The project is organized as follows:

```
src/
├── app.js              - Express application configuration
├── server.js           - Server entry point
├── config/             - Configuration files and environment variables
├── controllers/        - Request handlers and business logic
├── models/             - Database schema models (Mongoose)
├── routes/             - API route definitions
├── services/           - Business logic and utilities
└── utils/              - Utility functions and helpers
```

### Folder Descriptions

- **config/** - Contains configuration files for database connections, environment setup, and application settings
- **controllers/** - Houses route handlers that process requests and send responses
- **models/** - Defines MongoDB data schemas using Mongoose
- **routes/** - Contains API endpoint route definitions
- **services/** - Encapsulates business logic separate from route handlers
- **utils/** - Contains reusable utility functions and helper methods
