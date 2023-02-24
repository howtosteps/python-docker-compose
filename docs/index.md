# Introduction

This is a starter tutorial on how to use docker-compose. Docker compose builds on Docker and provides the capability to define & run multiple container images. The configuration is read from a single `docker-compose.yaml` file which inturn is dependent on multiple DockerFile(s) and/or image(s) from the image repository.   

Compose works in all environments: production, staging, development, testing, as well as CI workflows. It also has commands for managing the whole lifecycle of your application:

* Start, stop, and rebuild services
* View the status of running services
* Stream the log output of running services
* Run a one-off command on a service

The key features of Compose that make it effective are:

* Have multiple isolated environments on a single host
* Preserves volume data when containers are created
* Only recreate containers that have changed
* Supports variables and moving a composition between environments


## Application components
This application primarily consists of 3 parts - a simple web app file (`app.py`), dockerfile (`Dockerfile`) and the Docker Compose file (`docker-compose.yaml`). This start-up project will demonstrate how to use the compose tool, build container image(s) and then run the container in detached mode. 

## Application structure
```
  |── docs                      # Contains edited nginx configuration file that will be copied to the image
  |    ├── img                  # Contains all images referenced in mkdocs
  |    ├── *.md                 # Other mkdocs .md files
  ├── mkdocs.yml                # YAML for for mkdocs
  ├── .gitattributes
  |
  ├── Dockerfile                # Dockerfile for the web-app
  ├── docker-compose.yaml       # Configuration file for Compose tool
  ├── app.py                    # Simple web-based python program using Flask API
  ├── requirements.txt          # List of packages to be pre-installed in the container
  ├── command-list.md           # Cheat sheet for commands to run while running this simple tutorial
  ├── README.md                 # Standard README.md file
```

## References
 [Docker Compose Overview](https://docs.docker.com/compose/)
