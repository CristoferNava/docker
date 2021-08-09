<h1>Basic Commands</h1>

**docker pull**: Get the indicated image from the DockerHub.<br>

**docker run containerName**: Execute the image that contains all the info for the container and with that run the container.<br>

**docker images**: List all the images we have installed in our system.<br>

**docker images | head**: Same as _docker images_ but only show a few lines.<br>

**docker ps**: Show to us the containers that are runing.<br>

**docker ps -a**: Show the containers that ran recently. Most recent first<br>

**docker start idContainer**: Start a container in the background (don't show the logs). Start will start any stopped containers (with the data)<br>

**docker logs containerId**: Show the logs of the given container at the current moment and then return the control.<br>

**docker logs -f containerId** Same as _docker logs_ but it stays listening.<br>

**docker exec -it containerId sh**: _exect_ executes a command in a container that is currently running, the _-it_ is for interactive terminal and _sh_ is for shell.<br>

**docker stop containerId**: Stops the given container.<br>

**docker run -d containerId**: (_-d_ is for detach), run the given container in the background.<br>

<hr>
<br>
<h1>Building Images</h1>

    FROM *base image: image from where we're going to build our image*

    WORKDIR /app *where we are going to store the commands of our container*

    COPY . . *copy all the files of the actual directory to the container dir (/app)*

    RUN *compile, build, or whatever the app does*

    CMD ["command", "argument"] *command that is going to run when we start this container*

**docker build .**: Build the container given a Dockerfile, it returns the numeric ID created for that container.<br>

**docker build -t my-own-name**: Build the container with a giving tag, we can use this tag as an cointainerID equivalent.<br>

**docker run -dp 3000:3000 my-container-name**: Run the container using detach and port, exposing the port 3000 (the first one) of the Docker system to the port 3000 (the second one) of the host (our machine).<br>

**docker login**: Connect to Docker Hub.<br>

**docker tag old-name cristofernava/new-name:v2**: Change the old tag (container name) for the new one indicated.<br>

**docker push cristofernava/new-name:v2**: Upload the image to our profile in Docker Hub.<br>

<hr>
<br>
<h1>Docker Compose</h1>
Compose is a tool for defining and runnig multi-container Docker applications. With Compose, you use a YAML file to configure your application's services.<br>

**vim docker-compose.yaml**: Create a new Docker compose file.<br>

**docker-compose up -d**: _up_ up the services in the the .yaml file.
