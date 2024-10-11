# Challenge
## Overview  
This repository contains a full-stack application composed of an API and a Client, both of which can be easily deployed using Docker and Docker Compose. The API is built using PHP Laravel, and the Client is a Nuxt.js application. The app also uses MySQL as the database and Nginx as a reverse proxy.

## Prerequisites

Before you begin, make sure you have the following installed on your machine:

- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)

## Getting Started

Follow these instructions to get the application up and running on your local machine using Docker Compose.

### Step 1: Clone the Repository

```bash
git clone https://github.com/Maram-Hassan/challenge.git
cd Challenge
```

### Step 2: Set up Environment Variables

Create a `.env` file in the root directory and configure the following environment variables for the MySQL database. Example:

```bash
# .env file

# MySQL environment variables
DB_HOST=db
DB_DATABASE=your_db_name
DB_USERNAME=your_db_user
DB_PASSWORD=your_db_password

# API environment variables
APP_ENV=local
APP_DEBUG=true
APP_KEY=base64:generated_app_key

# Client environment variables
VITE_API_URL=http://api:8000
```

Make sure to replace the placeholders with actual values for the database and API.

### Step 3: Build and Run the Containers

You can now build and run the containers using Docker Compose.

```bash
docker-compose up --build
```

This command will:

- Build the Docker images for the API, Client, and Nginx.
- Set up the MySQL database.
- Start all containers defined in the `docker-compose.yml` file.

### Step 4: Access the Application

Once the containers are running, you can access the different parts of the application using the following URLs:

- **API**: http://localhost:8000
- **Client**: http://localhost:3000
- **Nginx**: http://localhost

### Step 5: Stopping the Application

To stop the application and remove the containers, you can run:

```bash
docker-compose down
```

This will stop and remove the containers, but the data will persist since it's stored in Docker volumes.

## Directory Structure

```
.
├── api        # Laravel API
├── client     # Nuxt.js Client
├── docker-compose.yml    # Docker Compose file
├── nginx.conf            # Nginx configuration
└── ssl                   # SSL certificate for Nginx
```

## Docker Compose Configuration

Here’s a breakdown of the services defined in the `docker-compose.yml`:

- **db**: MySQL database service.
- **api**: Laravel API service running on port `8000`.
- **client**: Nuxt.js client service running on port `3000`.
- **nginx**: Nginx proxy service forwarding requests to the API and Client.

## Troubleshooting

- If you encounter issues with the database connection, ensure that the `DB_HOST` in the `.env` file is set to `db`, which is the service name of the MySQL container in Docker Compose.
- Make sure the `.env` file in the API folder contains the correct values for database credentials.
- Run `docker-compose logs` to view detailed logs for each container in case of errors.

##Images
  ##Accessing the Website via HTTP 
  ![Screenshot from 2024-10-10 10-06-46](https://github.com/user-attachments/assets/efcb1867-909e-44b8-a416-3cbed5d553f6)
  ##Accessing the Website via HTTPS
  ![Screenshot from 2024-10-10 10-06-40](https://github.com/user-attachments/assets/aa5c7c38-2416-481b-bb74-583ddf5c42d1)
  ##Docker Containers Running Status
  ![Screenshot from 2024-10-11 11-19-49](https://github.com/user-attachments/assets/16c0122c-2ac2-491a-92a5-e60a5a582418)
  ##Docker Images Uploaded to Docker Hub
  ![Screenshot from 2024-10-11 12-30-03](https://github.com/user-attachments/assets/a05878f7-a98a-4e13-9bf8-848f5cd7f6a5)


  
