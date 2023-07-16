# Project Documentation: judge0 API Clone

****Overview****

The judge0 API Clone is a clone of the Judge0 API, which provides an online code execution and evaluation platform. It allows users to submit code snippets, specify the programming language, provide input data, and receive the execution results.

The project aims to replicate the core functionality of the Judge0 API, including code submission, code execution in a sandboxed environment, and storage of code submissions and execution results in a database.

****Features****

The judge0 API Clone includes the following features:

1. User Registration and Authentication:
   - Users can register and create an account.
   - User authentication is implemented using JSON Web Tokens (JWT) for secure access to API endpoints.

2. Code Submission:
   - Users can submit code snippets along with the programming language and optional input data.
   - Code submissions are stored in a MongoDB database.

3. Code Execution:
   - Code submissions are executed in a sandboxed environment using Docker containers.
   - Execution results are captured, including standard output and error messages.
   - Syntax errors and other execution errors are handled appropriately.

4. Retrieving Code Submissions:
   - Users can retrieve the details of a code submission by its ID.
   - The stored code, programming language, input data, and execution results are returned.

5. Real-time Notifications:
   - Users receive real-time notifications about the progress and completion of their code execution.
   - Notifications are sent using Socket.IO, allowing for bi-directional communication between the server and the client.

****Technologies Used****

The judge0 API Clone is built using the following technologies:

- Node.js: The server-side runtime environment for executing JavaScript code.
- Express.js: A web framework for building RESTful APIs in Node.js.
- MongoDB: A NoSQL database for storing code submissions and execution results.
- Docker: Used to create a sandboxed environment for executing code submissions. ( **937544224472.dkr.ecr.ap-south-1.amazonaws.com/sandbox-image:latest -> This is docker image, which was developed as part of the project, has now been deployed on AWS ECR (Elastic Container Registry). It serves as a sandbox environment for running code securely.**)
- JWT (JSON Web Tokens): Used for user authentication and authorization.
- Socket.IO: A library for real-time, bidirectional communication between the server and the client.
- Other libraries and packages: bcrypt for password hashing, dotenv for managing environment variables, and more.

****Installation and Setup****

To set up the judge0 API Clone project, follow these steps:

1. Clone the project repository from GitHub.
2. Install Node.js and npm on your system if not already installed.
3. Install Docker on your system if not already installed.
4. Install the project dependencies by running `npm install` in the project directory.
5. Set up a MongoDB database and configure the connection string in the project's `.env` file.
6. Configure other environment variables as needed, such as the JWT secret, server port, etc., in the `.env` file.
7. Open **Docker Desktop** installed on your system and leave it to run in background.
8. Start the server by running `node server.js`.

****API Endpoints****

The judge0 API Clone provides the following API endpoints:

- `POST /api/register`: User registration endpoint for creating a new user account. (Send username and password as body of request)
- `POST /api/login`: User login endpoint for obtaining a JWT token for authentication. (Send username and password as body of request)
- `POST /api/code`: Endpoint for submitting code snippets and executing them in a sandboxed environment. Make sure to add JWT token in Authorisation request header before sending request. Send code, language (java,python,cpp,c,javascript) and input (if required in code) as body of request
- `GET /api/code/:id`: Endpoint for retrieving the details of a code submission by its ID.

****Conclusion****

The judge0 API Clone project provides a simplified version of the Judge0 API, allowing users to submit and execute code snippets in a sandboxed environment. By following the project documentation, you can set up and run your own instance of the judge0 API Clone and leverage its features for code execution and evaluation. 
