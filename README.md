# Read Me First
The following was discovered as part of building this project:

* The JVM level was changed from '1.8' to '17', review the [JDK Version Range](https://github.com/spring-projects/spring-framework/wiki/Spring-Framework-Versions#jdk-version-range) on the wiki for more details.
* The original package name 'com.example.demo-config-server' is invalid and this project uses 'com.example.democonfigserver' instead.   

# Getting Started   

How to run the config server:   
mvn clean spring-boot:run   

OR   

java -jar target/demo-config-server-0.0.1-SNAPSHOT.jar   

# How to add another service config to this server   
1. add a folder with service name to main/root folder of the git repo used in  spring.cloud.config.server.git.uri property      
2. add env properties files with {serviceName}-{env}.properties 
3. git add, commit and push the files to remote repo   
4. invoke curl -X POST http://serviceHost:port/actuator/refresh on the service that uses this cloud config server  
	sample client for reference: [demoservice](https://github.com/shyamjava/demoservice/tree/develop)  





### Reference Documentation
For further reference, please consider the following sections:

* [Official Apache Maven documentation](https://maven.apache.org/guides/index.html)
* [Spring Boot Maven Plugin Reference Guide](https://docs.spring.io/spring-boot/docs/3.1.0/maven-plugin/reference/html/)
* [Create an OCI image](https://docs.spring.io/spring-boot/docs/3.1.0/maven-plugin/reference/html/#build-image)
* [Config Server](https://docs.spring.io/spring-cloud-config/docs/current/reference/html/#_spring_cloud_config_server)
* [Spring Boot Actuator](https://docs.spring.io/spring-boot/docs/3.1.0/reference/htmlsingle/#actuator)

### Guides
The following guides illustrate how to use some features concretely:

* [Centralized Configuration](https://spring.io/guides/gs/centralized-configuration/)
* [Building a RESTful Web Service with Spring Boot Actuator](https://spring.io/guides/gs/actuator-service/)

