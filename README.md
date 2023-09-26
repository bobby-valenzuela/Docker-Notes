# Docker Compose

<br>

Composing uses a configuration file (docker-compose.yml) use the Dockerfiles in your specified projects to...
- Build new images
- Configure any port-binding
- Configure any volumes
- Create/Run containers

<br>

## Creating A Docker compose file
A “docker-compose.yaml” file, is a configuration file that allows us to manage several containers that can communicate with each other. It’s responsible for creating Docker images based on any Dockerfile(s) placed in their respective project folders. This should be in the very root folder. Not root of our project (where source code lives) but at the very root of our Docker working directory.
 
<br>

![image](https://github.com/bobby-valenzuela/Docker-Notes/assets/70870649/be113bdc-6701-472e-b2fe-fa7fba852a6b)

<br>

## Cleaning up existing data [optional]
Optional step before running Docker compose is to clean up any existing images, containers, and volumes.  
This can be done with:
```
docker system prune
```

<br>

## Composing
In the parent path of your docker projects (i.e., the path within which directly lies your docker-compose.yml file)...
```sh
docker-compose up
```
Note: You can also explicitly specify your config file using the "-f" option.

<br>

## Stop running "Compositions"
If you want to stop all containers that were spun up by docker-compose, simply run...
```sh
docker-compose down
```
That will stop and delete any running containers that were initiated by a `docker-compose` command. THe images created and volumes will still exist.

<br>

## Stop running "Compositions" and delete the created images + volumes
```sh
docker-compose down --rmi all -v
```
- `--rmi all` - handles removing images
- `-v` - handles removing volumes
