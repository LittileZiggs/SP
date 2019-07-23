# SP
	a server prototype combine spring boot 2 and dubbo

## Framework:
	spring boot 2.1 + dubbo + mybatis + RocketMQ + zookeeper 

## Modules:
	There are 5 modules in total.  
	sp-api: service interfaces  
	sp-common: frequently used util classes and constants in RPC  
	sp-dao: mybatis mappers, models and plugins  
	sp-service: dubbo provider, implementation of service interfaces, RocketMQ util  
	sp-web: dubbo consumer, controllers for http restful  

## distribution environment:  
	see the application*.yml in sp-web and sp-service for reference.  
	1.dev(default): used for developing and testing  
	2.prod: used for production  
	If you want to make a package for production environment, you should launch the project through following command:
	```
                  nohup java -jar sp-service-1.0.0-SNAPSHOT.jar --spring.profiles.active=prod &  
                  nohup java -jar sp-web-1.0.0-SNAPSHOT.jar --spring.profiles.active=prod &  
        ```

## How to launch:   
	1.switch to the root directory of the project SP/, run    
           ```
	   mvn -U clean install -DskipTests  
	   ```
	2.switch to sp-service/target, enter the following text in the command line  
	   ```
                   nohup java -jar sp-service-1.0.0-SNAPSHOT.jar &  
           ```
	3.switch to sp-web/target, enter the following text in the command line  
	   ```
                   nohup java -jar sp-web-1.0.0-SNAPSHOT.jar &  
           ```
	4. then you can send http restful request from restlet or postman.  
