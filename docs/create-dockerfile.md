# Create DockerFile
We will now create a DockerFile that builds a Docker image. The image contains all the dependencies the Python application requires, including Python itself.

In the project directory, create a file named `DockerFile`
```
FROM python:3.7-alpine
WORKDIR /code
ENV FLASK_APP app.py
ENV FLASK_RUN_HOST 0.0.0.0
COPY requirements.txt requirements.txt 
RUN pip install -r requirements.txt
COPY . .
CMD ["flask","run"]

```
This tells Docker to:

* Build an image starting with the Python 3.7 image.
* Set the working directory to /code.
* Set environment variables used by the flask command.
* Copy requirements.txt and install the Python dependencies.
* Copy the current directory . in the project to the workdir . in the image.
* Set the default command for the container to flask run.
