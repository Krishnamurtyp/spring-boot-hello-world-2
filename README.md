# A Spring Boot Hello World Project with RESTful Web Services.

## Introduction to RESTful Web Services (03-Dec-2021)
1. Navigate to https://start.spring.io
2. Generate workspace by selecting **Spring Web** and **Spring Actuator** as starter dependencies.
3. Download workspace and import in Eclipse using _Existing Maven Project_ option.
4. In Spring's approach of creating RESTful web services, HTTP requests are handled by controller. This component is identified by **@RestController** annotation.
5. Build a web service that will accept HTTP GET requests at http://localhost:8080/hello
6. The **@GetMapping** annotation ensures that HTTP GET requests to **/hello** are mapped to **sayHello()** method in HelloWorldRestController.java.
7. There are companion annotations for other HTTP verbs (e.g. **@PostMapping** for POST). There is also a **@RequestMapping** annotation that they all derive from, and can serve as a synonym (e.g. **@RequestMapping(method = GET).**
8. **@RequestParam** - 
9. The implementation of method body creates and returns a new String object.
10. The key difference between a traditional MVC controller and the RESTful web service controller is the way that the HTTP response body is created. Rather than relying on a view technology to perform server-side rendering of the response object to HTML, this RESTful web service controller populates and return a custom response object, as per return type of handler method. This object will be written directly to HTTP response as JSON.
11. This code uses **@RestController** annotation, which marks the class as a controller where every method returns a domain object instead of view. It is shorthand for including both **@Controller** and **@ResponseBody.**
12. The custom response object / domain object must be converted to JSON. Thanks to Spring's HTTP message converter support, the domain object / custom response object, you need not do this conversion manually. Because **Jackson 2** is on the classpath, Spring's **MappingJackson2HttpMessageConverter** is automatically chosen to convert the domain object isntance to JSON.
13. The **@SpringBootApplication** is a convenience annotation that adds all of the following:
    * **@Configuration**: Tags the class as a source of bean definitions for the application context.
    * **@EnableAutoConfiguration**: Tells Spring Boot to start adding beans based on classpath settings, other beans, and various property settings. For example, if **spring-mvc** is on the classpath, this annotation flags the application as a web application and activates key behaviours, such as setting up **DispatcherServlet**.
    * **@ComponentScan**: Tells Spring to look for other components, configurations and services in the base package, letting it find the controllers.

14. The **main()** method uses Spring Boot's **SpringApplication.run()** method to launch an application. Did you notice that there was not a single line of XML? There is not **web.xml** file, either. This web application is 100% pure Java and you did not have to deal with configuring any plumbing or infrastructure.

15. **Building an executable JAR**
    You can run the application from the command line with Gradle or Maven. You can also build a single executable JAR file that contains all the necessary dependencies, classes, and resources and run that. Building an executable jar makes it easy to ship, version, and deploy the service as an application throughout the development lifecycle, across different environments, and so forth.
    
    If you use Gradle, you can run the application using **./gradlew bootRun**. Alternatively, you can build the JAR file by using **./gradlew build** and then run the JAR file as follows:
    **java -jar build/libs/gs-rest-service-0.1.0.jar**
    
    If you use Maven, you can run the application by using **./mvnw spring-boot:run**. Alternatively, you can build the JAR file with **./mvnw clean package** and then run the JAR file as follows:
    **java -jar target/gs-rest-service-0.1.0.jar**
    
----
