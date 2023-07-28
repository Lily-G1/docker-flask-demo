# Docker-Flask-Demo  
Building a python-flask app image with Docker and pushing to Dockerhub using Jenkins CI/CD  

![docker-push-to-dockerHub](https://github.com/Lily-G1/docker-flask-demo/assets/104821662/1d988e34-b665-4da8-a994-b954f76aaf05)  
Illustration credit: https://linuxhowtoguide.blogspot.com/  

## To run/test the app manually on an ubuntu/debian server:  
- Install python3, pip3 & flask  
- $ git clone https://github.com/Lily-G1/docker-flask-demo/  
- $ cd docker-flask-demo  
- $ python3 app.py  
- View application on localhost/IP:8080

## To containerize the app using Docker:  
- Install Docker  
- $ cd docker-flask-demo  
- $ docker build -t flask-app . (to build image)  
- $ docker run -d -p 8080:8080 flask-app (to run container)  
- $ docker stop 'container-ID' (to stop container)  

## To containerize & push app to Dockerhub with Jenkins:  
- Install Jenkins on same server. See installation guide [here](https://www.jenkins.io/doc/book/installing/linux/#debianubuntu)  
- On the Jenkins U.I, go to Manage Jenkins -> Credentials -> global -> Add Credentials :
  - Kind = ‘username & password’-> Enter your dockerhub account's username & password respectively  
  - Id = ‘dockerhub’  
  - Description = ‘dockerhub_credentials’. Save.  
- Go to dashboard & create new item (pipeline project) -> Advanced Project Options -> Advanced -> Display Name = ‘Docker-Flask-App’  
- Pipeline -> Pipeline SCM (enter github repo details). Save.  
- Go to Manage Jenkins -> Manage Plugins -> Install ‘safe restart’ plugin  
- On the server's command line:  
 - $ sudo usermod -a -G docker Jenkins. Log out & Log back in   (to give Jenkins access to Docker)  
- Restart Jenkins using systemctl on the command line OR via the U.I using 'safe restart'  
- Build project  
- Check Dockerhub to confirm that image was pushed successfully  

## Note:  
- Edit the image name on the Jenkinsfile to your preference  
