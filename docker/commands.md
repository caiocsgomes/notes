## Docker Commands Cheat Sheet


1. `docker container run` - Runs a new container from a Docker image.

- `docker container run -p 5000:3000` maps port 5000 form the host to port 3000 in the container
- `docker container run CONTAINER COMMAND` run a command inside a container when starting it
- `docker container run -d CONTAINER` run the container in a detached mode, in the background
- `docker container run -it CONTAINER COMMAND` run the container with the command and keeps the STDIN and STDOUT in the terminal

2. `docker container start` - Starts a stopped container.

3. `docker container stop` - Stops a running container.

4. `docker ps` - Lists all running containers.

- `docker ps -a` lists all containers

5. `docker image ls` - Lists all images on the local machine.
   
6. `docker container inspect` - Shows detailed information about a container or image.
   
7. `docker container logs` - Shows the logs of a container.
   
8. `docker container exec` - Runs a command in a running container.

- `docker container exec -it <CONTAINER ID or NAME> COMMAND` executes the command inside the container and returns the STDIN and STDOUT to the terminal, useful for running bash inside it
   
9. `docker container rm` - Removes a container.
   
10. `docker image rm` - Removes an image.

11. `docker image build .` - Builds a new image from a Dockerfile in the current folder

- `docker image build -t NAME:TAG .` gives a NAME and optionally a TAG for the container built 

12. `docker image push` - Pushes an image to a remote repository.

13. `docker image pull` - Pulls an image from a remote repository.

14. `docker container attach` - Attach local standard input, output, and error streams to a running container
