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

<hr>
<br>
<h1>Kubernetes Terminology</h1>

**Kubernetes cluster**: A collections of nodes + a master to manage them.<br>

**Node**: A virtual machine that will run our containers.<br>

**Pod**: More or less a running container. Technically, a pod can run multiple containers (we don't do this).<br>

**Deployment**: Monitors a set of pods, make sure they are running and restarts them if they crash.<br>

**Service**: Provides an easy-to-remember URL to access a running container.<br>

<hr>
<br>
<h1>Kubernetes Config Files</h1>

- Tells Kubernetes about the different Deployments, Pods, and Services (referred to as 'Objects') that we want to create.<br>
- Written in YAML syntax.<br>
- Always store files with your projects source code, they are documentation!<br>
- We can craete Objects without config files - **DO NOT DO THIS**. Config files provide a precise definition of what your cluster is running.<br>
- Kubernetes docs will tell you to run direct commands to create objects - only do this for testing purposes.<br>
- Blog posts will tell you to run direct commands to create objects - close the blog post!<br>

<h2>Basic Commands</h2>

**kubectl get pods**: Print out information about all of the running pods.<br>
**kubectl exec -it [pod_name] [cmd]**: Execute the given command in a running pod.<br>
**kubectl logs [pod_name]**: Print out logs from the given pod.<br>
**kubectl delete pod [pod_name]**: Deletes the given pod.<br>
**kubectl apply -f [config file name]**: Tells Kubernetes to process the config.<br>
**kubectl describe pod [pod_name]**: Print out some informatio about the running pod.<br>
**kubectl get deployments**: List all the running deployments.<br>
**kubectl describe deployment [depl name]**: Print out details about a specific deployment.<br>
**kubectl apply -f [config file name]**: Crate a deployment out of a config file.<br>
**kubectl delete deployment [depl_name]**: Delete a deployment.<br>
**kubectl rollout restart deployment [depl_name]**: Update a deploy.<br>

<h3>Services</h3>
Services provide networking between pods.<br>
Types of services:<br>

- **Cluster IP**: Set up an easy-to-remember URL to access a pod. Only exposes pods in the cluster.<br>
- **Node Port**: Makes a pod accessible from outside the cluster. Usually only used for dev purposes.<br>
- **Load Balancer**: Makes a pod accessible from outside the cluster. This is the right way to expose a pod to the outside world.<br>
- **External Name**: Redirects an in-cluster request to a CNAME url... don't worry about this one.<br>

<br>
<h3>Building an alias</h3>

**code ~/.zshrc**: To open the config file.<br>
**source ~/.zshrc**: To restart the terminal.<br>

<h3>Change the /etc/hosts</h3>
For Nginx Ingress we need to set a host, so we have to change the hosts of our computer in order to access to our app and no the given domain in the web.
Just open the file **code /etc/hosts** and add at the end of the file **127.0.0.1 posts.com**

**code ~/.zshrc**: To open the config file.<br>
**source ~/.zshrc**: To restart the terminal.<br>
