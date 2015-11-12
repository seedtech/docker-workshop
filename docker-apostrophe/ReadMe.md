## The apostrophe container expects a mongodb container present at aposdb
	
Build the web container

	docker build -t apostrophe-web .

Run the mongo container
    
	docker run --name mongo mongo:latest --smallfiles
	
Link the containers

	docker run -p 3000:3000 --link mongo:aposdb -v $(pwd):/usr/src/app apostrophe-web


Run the web container
	
	docker run --name apostrophe-webserver -p 80:3000 -v /data/logs:/data/logs -d --link mongo:aposdb apostrophe-web
	
Excercise

Try doing this using a docker compose file