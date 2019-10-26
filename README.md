go springboot restful web service project

See https://spring.io/guides/gs/rest-service/

create hello world rest service with spring

# Restful Web Service project

## Restful web service definition
> Representational state transfer (REST) is a software architectural style that defines a set of constraints to be used for creating Web services. ... In a RESTful Web service, requests made to a resource's URI will elicit a response with a payload formatted in HTML, XML, JSON, or some other format. (from wikipedia)

## Project goal
* accept http get requests:
`http://localhost:8080/greeting`
* respond with json greeting 
`{"id":1,"content":"Hello, World!"}`

## tools
* emacs
* openjdk 1.8
* maven and/or gradle
* import to intellij

## source files
* source dir - `src/main/java/hello`
* [build.gradle](build.gradle) - gradle build script 
* [pom.xml](pom.xml) - maven build script
* [template files](src/main/resources/templates) 
* [home.html](src/main/resources/templates/home.html) - home page with link to /hello
* [hello.html](src/main/resources/templates/hello.html) - protected page
* [MvcConfig.java](src/main/java/hello/MvcConfig.java) 
  - config Spring MVC (implements WebMvcConfigurer)
  - config view controllers for /home, /, /hello, /login
  - view controllers reference view for home.html, hello.html, login.html
* Application.java - spring boot application class
  - configured by spring 
  
  
## build with gradle
* `gradle -version` # check version
* `gradle clean build` # build application
* `gradle bootRun` # run application
   * or `java -jar build/libs/*.jar` to execute
   * check that localhost:8080 is available

## build with maven
* `mvn validate` ## validate pom
* `mvn -version` ## get maven version
* `mvn clean package`   ## clean & package
* `mvn spring-boot:run` ## run application with spring boot 



## test with :
```
curl localhost:8080/greeting ## returns {"id":1,"content":"Hello, World!"}
curl localhost:8080/greeting?name=someone ## returns {"id":3,"content":"Hello, someone!"}
``` 

## import with intellij
* specify as gradle project 
* specify build.gradle as the build script
* update the gradle configuration to build and run the service
* add gradle wrapper to git
* commit files to git and push to github
