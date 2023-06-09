# Docker-Flask-Demo  
Build a python-flask app image with Docker and push to Dockerhub using Jenkins CI/CD  

## To run the app on an ubuntu/debian server:  
Install python3, pip3 & flask  
$ git clone https://github.com/Lily-G1/docker-flask-demo/  
$ cd docker-flask-demo  
$ python3 app.py  
View application on localhost/IP:8080

## To containerize the app using Docker:  
Install Docker  
$ cd docker-flask-demo  
$ docker build -t flask-app . (to build image)  
$ docker run -d -p 8080:8080 flask-app (to run container)  
$ docker stop 'container-ID' (to stop container)  

## To containerize the app using Docker & push to Dockerhub using Jenkins:  
See steps on this [blogpost](https://liliangaladima.hashnode.dev/)   
