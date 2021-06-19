<h1>Docker commands</h1>
<h3>Simple commands to get started with docker</h3>


<br><br>
***
<h4>1. Launching containers</h4>

***

1. Run a container <br>
`docker run <image>`
<br><br>

2. Run conatiner and drop to shell <br>
`docker run -it <image>` 
<br>Full form <br>
`docker run --interactive --tty <image>`
<br><br>

3. Run a container in background <br>
`docker run -d <image>`
<br><br>

4. Set container restart settings <br>
`docker run --restart (always|no|on-failure[:maxretries]|unless-stopped) <image>`
<br><br>

5. Start an exited container <br>
`docker start <name>`
<br><br>

6. Remove a container when exited <br>
`docker run -rm <image>`
<br><br>


7. Provide container nickname <br>
`docker run --name <name> <image>`
<br>
<br>
***
<h4>2. Accessing containers</h4>

***

1. Run commands inside a contaner <br>
`docker exec <name> <command>` <br>
e.g. `docker exec test_container ps-aux`
<br><br>

2. Log into a shell inside a container to run more complex commands <br>
`docker exec -it <container_name> <shell_name>` 
<br>Example for running bash shell:<br>
`docker exec -it test-container bash`
<br><br>

3. Copying file from the container<br>
`docker cp <container_name>:<path> <to_path>`
<br>Example for copying nginx config from a container:<br>
`docker cp nginx-container:/etc/nginx/conf.d/default.conf .`
<br>
<br>Example for copying to a container:<br>
`docker cp default.config nginx-container:/etc/nginx/conf.d/default.conf`
<br><br>

***
<h4>3. Container management</h4>

***

1. Stop container<br>
`docker stop <name>` <br>
e.g. `docker stop test_container`
<br>

2. Remove container<br>
`docker rm <name>` <br>
e.g. `docker rm test_container`
<br>

3. Remove all stopped containers<br>
`docker container prune`
<br>

4. Rename a container<br>
`docker rename <old_name> <new_name>`<br>

5. Get stats for container like CPU info etc<br>
`docker stats`
<br>
`docker stats <container_name>`
<br>

6. Get detailed info about a container like public ip adress etc<br>
`docker inspect <container_name>`
<br>

7. Save container as an image to used later on<br>
`docker commit <container_name> <image_name>`
<br>

8. Important command to map container port to host server<br>
`docker run -p <host_port>:<container_port> <container_image>`
<br><br>

***
<h4>4. Image management</h4>

***

1. Pull remote image<br>
`docker pull <image-name>` <br>
e.g. `docker pull alpine`
<br>

2. Show all images pulled already<br>
`docker image ls` <br>

3. Remove image<br>
`docker image rm <image-name>` <br>

4. Remove problematic images<br>
`docker image prune` <br>

5. Remove images not linked to a container<br>
`docker image rm <image-name>` <br>

6. View image information<br>
`docker image inspect <image-name>` <br>
<br>
***
<h4>5. Pushing image to docker hub</h4>

***

1. Log in to your Docker account on the CLI.<br>
`docker login --username=<username>` <br>


2. Tag the image with the repo name.<br>
`docker tag <image> <username>/<reponame>` <br>


3. Push the image to Docker Hub.<br>
`docker push <username>/<reponame>` <br>
<br>

