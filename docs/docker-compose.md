# Define services a in Docker Compose File 
Create a file called `docker-compose.yml` in your project directory and paste the following:

```
FROM python:3.7-alpine
WORKDIR /code
ENV FLASK_APP app.py
ENV FLASK_RUN_HOST 0.0.0.0
# RUN apk add --no-cache gcc musl-dev linux headers
COPY requirements.txt requirements.txt 
RUN pip install -r requirements.txt
COPY . .
CMD ["flask","run"]
```

This Compose file defines two services: web and redis 

## Web service
The web service uses an image that’s built from the Dockerfile in the current directory. It then binds the container and the host machine to the exposed port, 5000. This example service uses the default port for the Flask web server, 5000.

## Redis service
The redis service uses a public Redis image pulled from the Docker Hub registry.