Jenkins pipeline Tutorial
Goals
* Install Docker on your machine
* Run Jenkins in Docker Container and 
* Create a multibranch pipline
* Trigger jenkins build of this Spring-boot-app

Run Jenkins in Docker
Once the docker is installed, pull Jenkins from dockerhub via 

- docker run -p 8080:8080 -p 50000:50000 -d -v jenkins_home:/var/jenkins_home jenkins/jenkins:lts

Go to localhost:8080 and login with one time password generated in console. 

Configure jenkins with Git credentials
Install Maven Plugin in Jenkins

Other way of doing this Jenkinsfile

node {
stage(’SCM Checkout’){
	git ‘https://github.com/nirozjung/docker-test’
 }

stage(‘Compile-Package’){
// Get maven home path
def mvnHome = tool name: ‘maven-3.6.3', type: 'maven'
sh “${mvnHome}/bin/mvn package”
 }
}

End of Life 
remove all
- docker system prune
- docker system prune --volumes
- docker container ls -a (list all containers)
- docker container prune
- docker volume prune
