# Overview

This application loads and makes the external configuration available to rest of the applications.

### Guides
The following guides illustrates how to use certain features concretely:

* [Configuration Service](https://cloud.spring.io/spring-cloud-static/spring-cloud.html#_spring_cloud_config)


### Running the application
* Run `gradle build`
* Run `gradle bootRun`

### Build and Run Docker container
* `./gradlew build -x test`
* `docker build -f ./Dockerfile -t config-service:local .`
* `docker run --rm -it -p 8888:8888 -e spring.profiles.active=docker --env MANAGEMENT_PATH=/admin --name config-service config-service:local` 

### Build and Deploy Docker container in K8 manually
* `./gradlew build -x test`
* `docker build -f ./Dockerfile -t {docker_username}/config-service:latest .`     
* `docker push {docker_username}/config-service:latest`
* `kubectl create -f ./deployments/{environment_profile}.yml`

### Endpoints
http://localhost:8888/{service}/{profile}


