# Setup MongoDB using docker-compose

> Currently we are working on Full-Stack project and we need to use latest MongoDB as a database. Our development team using Window 10 operation system and decided to use docker container for mongo installation. Open command terminal and follow the steps. We are assuming that both docker and docker-compose are installed on the Windows 10 machine.

1. *Step 1.*
	To pull latest image docker registry and type the below command
	
	````
	docker pull mongo:latest
	````
	
	![Docker Images](https://github.com/technetbytes/Docker/blob/main/docker-compose-mongodb/pullimage.JPG "docker pull image")
	
	verify your mongo database image by typing follow command
	````
	docker images
	````
	![MongoDB Images](https://github.com/technetbytes/Docker/blob/main/docker-compose-mongodb/dockerimagelist.JPG "mongodb image")	

2. Step 2. Write docker-compose file

	````
	# docker-compose.yml
	version: '3.1' #format version for this docker compose file
	services:
	  mongo-container:
	    image: mongo:latest
	    environment:
		- MONGO_INITDB_ROOT_USERNAME=saqib
		- MONGO_INITDB_ROOT_PASSWORD=saqib123
	    ports:
	      - "27017:27017"
	    command: mongod
	````

3. Step 3. Now its a time to execute compose file using following command

	````
	docker-compose up or docker-compose up –d command
	````

	To verify image is up and running type this command in the terminal **docker container ls** or **docker ps**
 
	Same thing is also achievable using Docker dashboard Windows client under Container/App listing. Other options are also available as well.
	![MongoDB Images](https://github.com/technetbytes/Docker/blob/main/docker-compose-mongodb/dockercontainer_window.png "mongodb image")	
	
4. Step 4. Time to login in the container using container name, in our case container name is docker_mongo-container_1
	````
	docker exec –it docker_mongo-container_1 bash
	````
Note: - Using ***container_name name*** property in ***docker-compose.yml*** to specify the container name.


	
