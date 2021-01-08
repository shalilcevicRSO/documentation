# Cloud computing project - How to find halal food?
## Description
How to find halal food is an application based on cloud-native architecture. Application is designed to help muslims all over the world to find a place where they can buy halal food, such as restaurants, supermarkets, hotels or butcher shops.

## Its usage?
  - Finding halal restaurants and supermarkets.
  - Uploading new ones.
  - Adding images and videos.
  - Adding comments and likes.

## Microservices
  - halal-place-catalog
  - add-halal-place
  - search-halal-place
  - image-catalog
    - It is not implemented yet.
  - upload-image
    - It is not implemented yet.
  - image-processing
    - It is not implemented yet.
  - videos-catalog
    - It is not implemented yet.
  - upload-videos
    - It is not implemented yet.
  - add-comments
    - It is not implemented yet.
  - add-likes
    - It is not implemented yet.
    
  
  
  Microservices repositories are available on: [https://github.com/shalilcevicRSO](https://github.com/shalilcevicRSO).
  
  Application architecture can be seen in [Architecture.md file](https://github.com/shalilcevicRSO/documentation/blob/main/Architecture.md).
  
  ### End points
    - [http://20.72.146.70:8080/v1/places](http://20.72.146.70:8080/v1/places)
    - [http://20.62.241.21:8080/v1/searchplace](http://20.62.241.21:8080/v1/searchplace)
    - [http://20.62.144.160:8080/v1/addplace](http://20.62.144.160:8080/v1/addplace)
  
  

## Docker images
Docker configuration is written in Dockerfile, which can be found in the repository of every implemented microservice.
Docker image are provided on: [https://hub.docker.com/repository/docker/selmah/rso-project](https://hub.docker.com/repository/docker/selmah/rso-project)


## Travis - CI/CD

CI/CD cycle is performed by Travis CI. It can accessed by next link: [https://www.travis-ci.com/github/shalilcevicRSO](https://www.travis-ci.com/github/shalilcevicRSO)

## Configuration

For the configuration for now it is used only config file for each microservice.

## Health Checks
- Simulation of microservice fail: [http://20.62.225.160:8080/v1/demo/break](http://20.62.225.160:8080/v1/demo/break)



## Metrics Collection
  - [http://localhost:8080/v1/places/allPlacesRequests](http://localhost:8080/v1/places/allPlacesRequests)
  - [http://localhost:8080/v1/places/createNewPlaceMeter](http://localhost:8080/v1/places/createNewPlaceMeter)

## Kubernetes
  Azure Kubernetes Service.
  Cluster name: halalplacecatalog

## Logging

Not implemented yet.

## Fault Tolerance

Not implemented yet.

## 3rd party APIs

Not implemented yet.

## Communication protocols

Not implemented yet.

## UI implementation

Implementation available locally.

