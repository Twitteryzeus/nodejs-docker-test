## Nodejs-Docker-Test

### Challenge Overview

**Objective:** Create a simple web application stack using Docker that includes a Node.js backend, a MongoDB database, and a frontend served through an Nginx server. The backend should connect to the MongoDB database and provide a REST API that allows users to retrieve a list of items stored in the database. The Nginx server will serve the static files for the frontend and also act as a reverse proxy to the backend service.

### Requirements:

1. **Dockerfile for Node.js Backend:**
   - Base image: Node.js (specify a version you're comfortable with, e.g., 14-alpine).
   - The backend should connect to MongoDB and provide a simple REST API to fetch items from a collection named `items`.
   - Expose the appropriate port (e.g., 3000).

2. **Dockerfile for MongoDB:**
   - Use the official MongoDB image.
   - Ensure that MongoDB is set up to store data in a volume, so data persists across container restarts.

3. **Dockerfile for Nginx:**
   - Base image: nginx:alpine.
   - Configure Nginx to serve static files from a directory (this will represent your Angular frontend). Place a simple `index.html` file in the directory for testing purposes.
   - Configure Nginx to proxy requests to `/api` to the Node.js backend service.

4. **docker-compose.yml:**
   - Define services for the backend, MongoDB, and Nginx.
   - Set up the necessary networks and volumes for communication and data persistence.
   - Use environment variables where appropriate for configuration.

### Desired Output:

- When navigating to the Nginx server's IP address or domain, the browser should display the `index.html` page.
- Accessing `<nginx-server-ip>/api/items` should display the list of items fetched from the MongoDB database through the Node.js backend.

### Constraints and Guidelines:

- All services should be defined within a single `docker-compose.yml` file.
- The application should be easy to start with a single `docker-compose up` command.
- Ensure your MongoDB database is secured and not exposed publicly.
- Provide a README.md file with instructions on how to build and run the application, including how to populate the MongoDB database with sample data.