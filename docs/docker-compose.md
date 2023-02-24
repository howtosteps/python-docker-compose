# Configure services 
Create a file called `docker-compose.yml` in your project directory and paste the following:

```
version: '3'
services:
  web:
    build: .
    ports:
      - 5000:5000
    volumes:
      - .:/code
    environment:
      - FLASK_ENV=development
  redis:
    image: redis:alpine
```
This tells Compose tool to : 

* Define 2 services - web and redis

    * **Web service** - Use an image that’s built from the Dockerfile in the current directory. It then binds the container and the host machine to the exposed port:5000. This example service uses the default port for the Flask web server: 5000.

    * **Redis service** - Use public Redis image pulled from the Docker Hub registry.

* Set the version to 3