![[docker.excalidraw]]
1. A **containerization** tool.
> Containerization is just a feature of linux kernel. 
> A **container** is just: 
> A process (or set of processes) running on the host OS in isolation.
## Commands: 
```powershell
docker container ls 
docker image ls 
docker start <image_name> 
docker run -it ubuntu 

```

# Dockerfile: 
 > Instructions to build image for a container
```Dockerfile

```

# Docker-Compose: 
> A tool to run multicontainer application 
2. Port Mapping
3. Environment Variables 
4. Docker volumes 
5. Docker Networking
6. Efficient Caching 
# .dockerignore
```
docker network inspect 
```

#  Multi Stage builds
> The image does not all the build tools 
```Dockerfile
FROM ubuntu as build 


FROM ubuntu as runner 
```