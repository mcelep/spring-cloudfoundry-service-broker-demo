This project is a demo implementation of [Cloud Foundry Service Broker API](https://docs.cloudfoundry.org/services/api.html)  based on  [Spring Cloud Foundry Service Broker](https://github.com/spring-cloud/spring-cloud-cloudfoundry-service-broker)

The application can be built by: ```gradle clean build```

For running the app, use command: ```java -jar build/libs/spring-cloud-cloudfoundry-service-broker-demo-0.0.1-SNAPSHOT.jar ```

After running the app, hitting the 'catalog' endpoint should create a [json](src/main/resources/demo-service-definition.json) response. Example call:```curl -u user:changeMe localhost:8080/v2/catalog```

A space based service broker can be added via: ```cf csb sb1 user changeMe http://url.to.sb --space-scoped```

Http Endpoints(except swagger, see the _WebSecurityConfig_ class for details) are protected by Basic authentication, see the _application.properties_ for the configuration of username/password. 

For more details about managing service brokers, [click here.](https://docs.cloudfoundry.org/services/managing-service-brokers.html)

Swagger documentation can be reached on localhost:8080/swagger-ui.html.