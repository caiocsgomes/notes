## Docker Commands Cheat Sheet


### `docker container run` - Runs a new container from a Docker image.

-  `docker container run -p 5000:3000 IMAGE` maps port 5000 form the host to port 3000 in the container
- `docker container run IMAGE COMMAND` run a command inside a container when starting it
- `docker container run -d IMAGE` run the container in a detached mode, in the background
- `docker container run -it IMAGE COMMAND` run the container with the command and keeps the STDIN and STDOUT in the terminal
- `docker container run --name NAME IMAGE` gives a name to the container

### `docker container start` - Starts a stopped container.

### `docker container stop` - Stops a running container.

### `docker ps` - Lists all running containers.

- `docker ps -a` lists all containers

### `docker image ls` - Lists all images on the local machine.
   
### `docker container inspect` - Shows detailed information about a container or image.
   
### `docker container logs` - Shows the logs of a container.
   
### `docker container exec` - Runs a command in a running container.

 - `docker container exec -it <CONTAINER ID or NAME> COMMAND` executes the command inside the container and returns the STDIN and STDOUT to the terminal, useful for running bash inside it
   
### `docker container rm` - Removes a container.
   
### `docker image rm` - Removes an image.

### `docker image build .` - Builds a new image from a Dockerfile in the current folder

- `docker image build -t NAME:TAG .` gives a NAME and optionally a TAG for the container built 

### `docker image push` - Pushes an image to a remote repository.

### `docker image pull` - Pulls an image from a remote repository.

### `docker container attach` - Attach local standard input, output, and error streams to a running container
