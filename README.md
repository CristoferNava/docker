<h1>Basic Commands: </h1>

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
