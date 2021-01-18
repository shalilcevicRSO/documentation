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
  
## End points
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
Simulation of microservice fail: 
- Check current microservice health: [http://localhost:8080/v1/places/healthy](http://localhost:8080/v1/places/healthy)
- Make it unhealthy: [http://localhost:8080/v1/places/healthy/break](http://localhost:8080/v1/places/healthy/break)
- Make it healthy: [http://localhost:8080/v1/places/healthy/up](http://localhost:8080/v1/places/healthy/up)



## Metrics Collection
  - [http://localhost:8080/v1/places/allPlacesRequests](http://localhost:8080/v1/places/allPlacesRequests)
  - [http://localhost:8080/v1/places/createNewPlaceMeter](http://localhost:8080/v1/places/createNewPlaceMeter)

## Kubernetes
  Azure Kubernetes Service.
  Cluster name: halalplacecatalog
  
## Ingress Proxy endpoints:
Ingress is available on : [http://20.72.162.155:80/](http://20.72.162.155:80/) endpoint.
Microservices endpoints on ingress are:
- Halal-place-catalog: [http://20.72.162.155:80/halalplacecatalog/v1/places](http://20.72.162.155:80/halalplacecatalog/v1/places)
- Add-halal-place: [http://20.72.162.155:80/addhalalplace/v1/addplace](http://20.72.162.155:80/addhalalplace/v1/addplace)
- Search-halal-place: [http://20.72.162.155:80/searchhalalplace/v1/searchplace](http://20.72.162.155:80/searchhalalplace/v1/searchplace)

## 3rd Party API
3rd Party API is takend from [OpenWeatherMap API](https://openweathermap.org/api). It shows current weather for the city of interest.
It is accessible on the [http://localhost:8080/v1/places/weather/{input city}](http://localhost:8080/v1/places/weather/ljubljana) endpoint.
It is implemented in halal place catalog microservice.

## GraphQL implementation

GraphQL implementation can be found [here](https://github.com/shalilcevicRSO/halal-place-catalog/tree/main/api/src/main/java/com/selma/halal/food/project/graphql).
Its endpoints are:
- [http://localhost:8080/graphql](http://localhost:8080/graphql), or
- [http://localhost:8080/graphiql](http://localhost:8080/graphiql) 

Below are listed some query examples to be run on [http://localhost:8080/graphiql](http://localhost:8080/graphiql) :
```
query getHalalPlaceMetadata {
   halalPlaceMetadata ( halalPlaceMetadataId: 1){
    placeId
    placeName
    city
    country
    streetName
    streetNumber
    zipCode
    placeType
    description
    dateCreated
    uri
  }
}
```
```
query getSearchHalalPlaceMetadata {
   searchHalalPlaceMetadata(city: "Ljubljana", country:"Slovenia") {
    placeId
    placeName
    city
    country
    streetName
    streetNumber
    zipCode
    placeType
    description
    dateCreated
    uri
  }
}
```



## Logging

Maven dependencies logs and cdi-weld are added to pom.xml files, but classs cannot import com.kumuluz.ee.logs.cdi.Log, because it cannot find cdi library.
Unable to implement it.

## Fault Tolerance

The same problem like in Logging. Bean class cannot import fault tolerance from microprofile. Hence I was not able to implement it. Although there is code example how it should be implemented if the library could be imported.





