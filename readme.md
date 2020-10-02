WordPress Docker Deployment
==============================
this repo is created for fun!

#Prepare Environment
in the following setup, we assume that you are working on a Linux Debian environment such as Ubuntu
- Install Docker : [reference](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-18-04)
```
sudo apt update
sudo apt install apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo apt update
sudo apt install docker-ce
```
- Install Docker Compose: [reference](https://www.digitalocean.com/community/tutorials/how-to-install-docker-compose-on-ubuntu-18-04)
```
sudo curl -L https://github.com/docker/compose/releases/download/1.21.2/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
```

# Running WordPress in Containers
this WordPress deployment uses docker-compose to run the official WordPress optimized image (alpine image) served via Nginx webserver container and use MySQL DB container. all of these containers run on the same docker network (thanks for docker bridge networks!).
- copy `.env.example` to `.env` and update it according your secrets
- hit `docker-compose up -d` in your terminal, then once images are being downloaded your WordPress app will run, then open your browser at the following link `http://localhost:8080`
  
hint:
you can change the port `8888` in docker-compose.yml file at line `39` or simply add it in .env! =)
