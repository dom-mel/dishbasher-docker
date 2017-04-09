# Dishwasher
## Quick install

You need [docker and docker composer](https://www.docker.com/) to run the quick start.


Just clone & run the docker image - everything will be installed and started for you.
Make sure port 8080, 8081 and 8082 are not in use.
```
git clone https://github.com/dom-mel/dishwasher-docker.git
cd dishwasher-docker
docker-compose up -d
```

You can now access the following services:
* [Simple Dishwasher frontend](http://127.0.0.1:8080/)
* [Dishwasher API documentation](http://127.0.0.1:8081/)
* [Dishwasher API](http://127.0.0.1:8082/)

The setup contains a minimal setup with some dishwashers pre-configured. I.e. [http://127.0.0.1:8082/dishwasher](http://127.0.0.1:8082/dishwasher) 

### usefull commands
* **docker-compose stop**: stops the demo
* **docker-compose exec api sh**: Get a shell inside the APIs container
* **docker-compose exec ui sh**: Get a shell inside the frontend container
 
# See also
* [Source of this project](https://github.com/dom-mel/dishwasher-docker)
* [Source of the API component](https://github.com/dom-mel/dishwasher-api)
* [Source of the UI](https://github.com/dom-mel/dishwasher-ui)