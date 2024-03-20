# Docker compose:

Running 3 services in docker compose:

- node.js express backend
- react.js frontend
- mongoDB database

To run the services, you need to have docker installed on your machine.

Different docker-compose files are available:
- docker-compose.dev.yml: to run the services in development mode:
  
  - Here we are using volumes to mount the source code of the services on the local machine to the containers, so any changes in the source code will be reflected in the containers. For example mount the frontend source code to the frontend container:
  ```yml
    volumes:
      - ./frontend:/app
  ```
  
- docker-compose.dev.networks:
  - Here we are using a custom networks to connect the services together, so they can communicate with each other using the service name as the hostname. For example, the frontend service can communicate with the backend service using the hostname "backend".

- docker-compose.production.yml:
  - We are not using volumes in this file, so the source code will not be mounted to the containers, and the containers will use the image that is built from the source code.
  - We are using optimized images for the services, for example, the frontend service is using the nginx image to serve the static files - Dockerfile.prod uses multi-stage build to build the optimized image for the frontend service:

- docker-compose.testing:
  - We are running tests inside the conatiner (in this case only for the frontend service)