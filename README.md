# Notes

https://denven.github.io/docker/

# Resources

Introduction: https://zhuanlan.zhihu.com/p/89587030
Docker Practice: https://yeasy.gitbook.io/docker_practice/

## Installation

- Install docker on Ubuntu: https://docs.docker.com/engine/install/ubuntu/
- Install docker compose on Ubuntu: https://docs.docker.com/compose/install/

## Docker Application for web development

- What Developers Need to Know About Docker: https://www.wintellect.com/what-developers-need-to-know-about-docker/
- Docker for Web Developers — All You Need to Know: https://scotch.io/@blizzerand11/docker-for-web-developers-all-you-need-to-know
- Docker for Front-End Developers: https://medium.com/better-programming/docker-for-front-end-developers-c758a44e622f
- Dockerize a React App: https://mherman.org/blog/dockerizing-a-react-app/
- Dockerize a Node App: https://nodejs.org/fr/docs/guides/nodejs-docker-webapp/
- How to create a full stack React/Express/MongoDB app using Docker: https://medium.com/free-code-camp/create-a-fullstack-react-express-mongodb-app-using-docker-c3e3e21c4074

## Docker Tips

- Run docker rootlessly(without sudo) on Ubuntu (https://askubuntu.com/questions/477551/how-can-i-use-docker-without-sudo)

  - `sudo groupadd docker`
  - `sudo gpasswd -a $USER docker`
  - `newgrp docker`

- Docker local files and directories: https://www.freecodecamp.org/news/where-are-docker-images-stored-docker-container-paths-explained/

  - Docker root directory is: `/var/lib/docker`
  - `sudo ls -l /var/lib/docker | grep ^d`

- Get docker container ip address
  - `docker inspect <container-id-or-name> | grep \"IPAddress\": |head -n 1 | cut -d":" -f2`
- SSH to a docker container
  - docker exec -it <container-id-or-name> /bin/bash to get a bash shell in the container.
- `docker attach` vs `docker exec`:

  - `docker exec` executes a new command / create a new process in the container's environment, while `docker attach` just connects the standard input/output/error of the main process(with PID 1) INSIDE the container to corresponding standard input/output/error of your host machine's terminal(the terminal you are using to run the command).
  - `docker exec` will not stop/exit the container when the created process exits, while executing a `exit` command in an attached container by `docker attach` will stop the container.

- Kill or remove all containers

  - `docker kill $(docker ps -q)`
  - `docker rm -f $(docker ps -aq)`

- Docker orchestration tools (commercial): **Container orchestration** is the automatic process of managing or scheduling the work of individual containers for applications based on <span style="color:red">**microservices.**</span> within multiple clusters. The widely deployed container orchestration platforms are based on open-source or commercial versions:
  - Docker swarm
  - Google Kubernetes
  - Apache mesos marathon
  - Redhat Openshift (Commercial)
  - Practices: https://www.cnblogs.com/aspirant/p/11481805.html
