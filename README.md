### Azure VM (Ubuntu)
Project has been deployed on Azure VM (Ubuntu).
Link: http://20.55.250.171:80


### Steps taken for setup
1. Created docker files in frontend and backend to create images
2. Created docker-compose.yml to create run the conatiners along with container and volumn for mongodb as well as watchtower to update and restart the images.
2.1. docker-compose.yml contains following images: mongodb,frontend,backend,watchtower
2.2. Watchtower is used to pull new images from docker hub and reestart with new images, everyday at 4am.
3. created nginx.conf file to configure nginx server.


### Steps for docker image and push process
1. Create github action to build and push new image everytime code is pushed to the github.
2. find configuration for the same in .github/workflows/docker-image.yml
3. Docker images can be found here 
[backend](https://hub.docker.com/repository/docker/yoganand20/backend/general)
[frontend](https://hub.docker.com/repository/docker/yoganand20/frontend/general)


### Steps taken for deployment
1. Clone this project to server.
2. Install docker(install older version,(28) as newer doesnt work for watchtower) and nginx.
3. Start docker containers using `docker compose up` from project directory.
4. Copy nginx.conf file from project directory to /etc/nginx/
5. Restart nginx server `sudo systemctl restart nginx`
6. Access frontend from localhost:80 and backend from localhost:80/api. (incase deployed on clode use IP inplace of localhost)

### Screenshots
1. Image build and uploading to docker hub
![Action to build and push images - 1](<screenshot/Github Action to build and push images - 1.png>)
![Action to build and push images - 2](<screenshot/Github Action to build and push images - 2.png>)
![Action to build and push images - 3](<screenshot/Github Action to build and push images - 3.png>)

2. start docker container on azure
![Docker images deployed on azure](<screenshot/Docker images deployed on azure.png>)

3. Ubuntu VM on Azure
![Ubuntu VM on Azure](<screenshot/Ubuntu VM on Azure.png>)

3. restart nginix and test using curl
![nginx restart and curl test](<screenshot/nginx restart and curl test.png>)

4. Accessing web app from local machine
![Accessing web app from local machine 1](<screenshot/Accessing web app from local machine - 1.png>)
![Accessing web app from local machine 2](<screenshot/Accessing web app from local machine - 2.png>)
![Accessing web app from local machine 3](<screenshot/Accessing web app from local machine - 3.png>)
![Accessing web app from local machine 4](<screenshot/Accessing web app from local machine - 4.png>)

