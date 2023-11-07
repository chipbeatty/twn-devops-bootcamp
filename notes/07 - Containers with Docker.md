7 - Containers with Docker

A Docker container is a:

- Lightweight
- Standalone
- Executable
- Contains everything needed to run an application

Docker Image:

1. The blue print to create an application
2. Read-only and static
3. Stored in Docker Hub

Docker Container:

1. A running instance of an image
2. Can run on any system consistently without having to make adjustments
3. Can be easily shared on different OS systems

Virtual Machine:

1. uses a hypervisor such as VirtualBox
2. Much more overhead than Docker
3. Less portable than DOcker
4. Slower than Docker

DOcker:

1. Shares the host's OS kernal
2. Can start in seconds
3. Very portable

Here are 15 important Docker commands that are commonly used for managing Docker containers and images:

1. **docker pull**: Pulls a Docker image from a registry to your local machine.

   ```
   docker pull <image_name>
   ```

2. **docker run**: Creates and runs a Docker container from an image.

   ```
   docker run <options> <image_name>
   ```

3. **docker ps**: Lists running containers.

   ```
   docker ps
   ```

4. **docker ps -a**: Lists all containers, including stopped ones.

   ```
   docker ps -a
   ```

5. **docker stop**: Stops a running container.

   ```
   docker stop <container_id>
   ```

6. **docker start**: Starts a stopped container.

   ```
   docker start <container_id>
   ```

7. **docker restart**: Restarts a container.

   ```
   docker restart <container_id>
   ```

8. **docker rm**: Removes a container.

   ```
   docker rm <container_id>
   ```

9. **docker rmi**: Removes an image.

   ```
   docker rmi <image_name>
   ```

10. **docker build**: Builds a Docker image from a Dockerfile.

    ```
    docker build -t <image_name> <path_to_Dockerfile_directory>
    ```

11. **docker exec**: Runs a command inside a running container.

    ```
    docker exec -it <container_id> <command>
    ```

12. **docker logs**: Displays the logs of a container.

    ```
    docker logs <container_id>
    ```

13. **docker inspect**: Provides detailed information about a container or image.

    ```
    docker inspect <container_id or image_name>
    ```

14. **docker network**: Manages Docker networks, including creating and connecting containers to networks.

    ```
    docker network create <network_name>
    ```

15. **docker-compose**: Used to manage multi-container applications with Docker Compose. This command allows you to define and run multi-container applications using a YAML file.
    ```
    docker-compose up -d
    ```

These are fundamental Docker commands that are useful for tasks like managing containers, images, and networks, as well as running and controlling Dockerized applications.

Steps Completed for the Project

1. Pulled the mongo image
2. Pulled the mongo-express image
3. Create Docker network

```
docker network create mongo-network
```

4. Set up port and enviromental variables for MONGODB

```
 docker run -p 27017:27017 -d -e MONGO_INITDB_ROOT_USERNAME=admin -e MONGO_INITDB_ROOT_PASSWORD=password --name mongodb --net mongo-network mongo
```

5. SET UP FOR MONGO-EXPRESS

```
docker run -d -p 8081:8081 -e ME_CONFIG_MONGODB_ADMINUSERNAME=admin -e ME_CONFIG_MONGODB_ADMINPASSWORD=password --net mongo-network --name mongo-express -e ME_CONFIG_MONGODB_SERVER=MONGODB mongo-express
```

How to Create a Docker Image Using a Dockerfile

1. Create a text file named "Dockerfile"
2. Specify the base image

```
FROM ubuntu:20.04
```

3. Use the RUN instruction to execute commands in the container during the image build

```
RUN apt-get update && apt-get install -y <package_name>
```

4. Use the COPY command to copy the application source code into the container

```
COPY . /app
```

5. Use the ENV instruction to set environment variables

```
ENV MY_VARIABLE=value
```

6. Use the EXPOSE instruction to document which ports should be published

```
EXPOSE 80
```

7. Use the CMD instruction to specify the command that should be executed when a container is started from the image

```
CMD ["python", "app.py"]
```

8. Use the docker build command to build the image, and specify a name and optionally a tag for the image

```
docker build -t my-image:latest .
```

9. Run a container from the image using the docker run command

```
docker run -d my-app:latest
```

AWS Elastic Container Registry

1. Make sure AWS CLI is setup as well as aws configure on local machine
2. Setup repo in ECR
3. Tag image
4. Push project to ECR (use commands by pushing View Push Commands button in your ECR container)

Docker Volumes

1. Used for persistance of data
2. Plug host file system to container's virtual file system
3. Data gets automatically replicated

3 Types of Docker Volume

1. Host Volume

- you decide where on the host file system the refernce is made

2. Anonymous Volume

- for each container a folder is generated that gets mounted

3. Named Volumes

- you can reference the volume by name
- use this is production

Docker Best Practices:

1. Do not use latest tag
2. Use leaner OS distro for security reasons
3. Optimize caching image layers
4. Do not re-run when project file changes. Re-run when package.json file changes.
5. Use dockerignore file
6. Use multi-stage builds
7. Don't run container as root user
8. Scan images for vulnerabilities in Docker Hub
