In this DevOps task, you need to build and deploy a full-stack CRUD application using the MEAN stack (MongoDB, Express, Angular 15, and Node.js). The backend will be developed with Node.js and Express to provide REST APIs, connecting to a MongoDB database. The frontend will be an Angular application utilizing HTTPClient for communication.  

The application will manage a collection of tutorials, where each tutorial includes an ID, title, description, and published status. Users will be able to create, retrieve, update, and delete tutorials. Additionally, a search box will allow users to find tutorials by title.

## Project setup

### Node.js Server

cd backend

npm install

You can update the MongoDB credentials by modifying the `db.config.js` file located in `app/config/`.

Run `node server.js`

### Angular Client

cd frontend

npm install

Run `ng serve --port 8081`

You can modify the `src/app/services/tutorial.service.ts` file to adjust how the frontend interacts with the backend.

Navigate to `http://localhost:8081/`

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
2. fild configuration for the same in .github/workflows/docker-image.yml

### Steps taken for deployment
1. Clone this project to server.
2. Install docker(install older version,(28) as newer doesnt work for watchtower) and nginx.
3. Start docker containers using 'docker compose up' from project directory.
4. Copy nginx.conf file from project directory to /etc/nginx/
5. Restart nginx server 
6. Access frontend from localhost:80 and backend from localhost:80/api. (incase deployed on clode use IP inplace of localhost)



