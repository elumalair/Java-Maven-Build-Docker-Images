# Java-Maven-Build-Docker-Images


Docker File
 
FROM java:8
VOLUME /tmp
ADD myproject-0.0.1-SNAPSHOT.jar app.jar
RUN bash -c 'touch /app.jar'
ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom","-jar","/app.jar"]
Build Docker Images using Maven:


mvn clean package docker:build
List the docker images


docker images
Run the docker with Spring Profiles:


$ docker run -e "SPRING_PROFILES_ACTIVE=dev" -p 8080:8080 -t springio/gs-spring-boot-docker

$ docker run -e "SPRING_PROFILES_ACTIVE=prod" -p 8080:8080 -t springio/gs-spring-boot-docker

List the docker process which are running :


docker ps
Stop the docker container :


docker stop <<containerid>>
Remove the docker container:


docker rm <<containerid>>
