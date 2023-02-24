#reference URL
https://morioh.com/p/1e80d49f8d3e

# From your project directory, start up your application by running docker-compose up
# '-d' flag for detached mode
docker-compose up -d

# Browse to the web-app
http://localhost:5000/ 

# check inside the container
docker ps
docker exec -it <container-id> /bin/sh

# Shutdown the docker 
docker-compose down

# bring down the volumes
docker-compose down --volumes