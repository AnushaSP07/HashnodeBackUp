## Annotations of Spring Frameworks!

# **Hey Reader !!!**

In this post let's learn some of the annotations used in Spring and Spring-Boot Frameworks !!!

### The contents of the blog include:

1. Class level annotations
2. Property and method level annotations
3. Transaction based annotations
4. Entity based annotations


### **Class level annotations**


### @SpringBootApplication
    - This is the entry point of spring application and is the class level annotation, the class contains this annotation and the main method.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660150945342/Udh1M_QmW.png align="left")
-	@ SpringBootApplication is equivalent to using @Configuration, @EnableAutoConfiguration, and @ComponentScan with their default attributes. 
-	@EnableAutoConfiguration: enable Spring Boot’s auto-configuration mechanism
-	@ComponentScan: enable @Component scan on the package where the application is located (see the best practices)
-	@Configuration: allow to register extra beans in the context or import additional configuration classes

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660150969744/2dsq8cI_9.png align="left")

**@ComponentScan** – Spring boot automatically scans all the components included in the project using the above annotation. This is a class level annotation.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660151069952/5vFX7mimu.png align="left")

### @RestController 
-  it is a class level annotation, it returns the object. And object data is directly written in HTTP response as JSON or XML. Used for crating RESTful controller.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660151139393/O_uZJtsrr.png align="left")

### @Controller
-  It is a class level annotation, it makes the class human readable by making the model object to view or template.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660151162698/4E-jIVchP.png align="left")

### @Autowired 
-  Spring provides annotation based auto-wiring by providing @autowired annotation. 
-  It is used to autowire spring bean on setter methods, instance variables and   
   constructors. 
- When we use @Autowired annotation, the spring container auto-wires the bean by 
   matching data-type.
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660151191448/-HUQwWVi-.png align="left")

### @Component 
- It indicates that an annotated class is a component. Such classes are considered as candidates for auto-direction when using annotation based configuration and classpath scanning.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660151479279/pRB_EI43y.png align="left")

### @Qualifier
- It is a property level annotation, when you create more than one bean of the same type and want to wire only one of them with a property. 
- In such case you can use @Qualifier along with @autowired to remove the confusion by specifying which exact bean will be wired. 

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660151524098/F1But2mN8.png align="left")

### @Service 
- is used with classes that provide some business functionalities. 
- Spring context will autodetect these classes when annotation-based configuration and classpath scanning is used. 

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660151571535/ZytTtB9tx.png align="left")

### @PropertySource 
- used to provide properties file to Spring Environment. 
- It represents a set of property pairs from a particular source

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660151597437/tiqagk5DH.png align="left")

### @CrossOrigin  
- It enables cross-origin resource sharing only for this specific method.  
- By default, its allows all origins, all headers, and the HTTP methods specified in the 
  @RequestMapping annotation. 
- Also, a maxAge of 30 minutes is used. You can customize this behavior by specifying the value.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660151657584/e-bv9HWO9.png align="left")

### @Scope 
- As with Spring-managed components in general, the default and most common scope 
   for autodetected components is singleton. 
- To change this default behavior, use @Scope spring annotation.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660151697226/QGPcGPfpj.png align="left")

### @SessionAttributes 
- This will list the names of model attributes which should be transparently stored in the session, serving as form-backing beans between subsequent requests.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660151734387/OGXlGiBU-.png align="left")

## **Method level or Property level annotations**

### @RequestMapping 
- RequestMapping annotation is used to map web requests onto specific handler classes 
   and/or handler methods. 
- @RequestMapping can be applied to the controller class as well as methods.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660151815793/9KjIYZvDv.png align="left")

### @ExceptionHandler
- It allows us to handle specified types of exceptions through one single method. 

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660151852505/OpYVYnpuZ.png align="left")

### @Bean 
- Indicates that a method produces a bean to be managed by the Spring container. 
- This is one of the most used and important spring annotation. 
- @Bean annotation also can be used with parameters like name, initMethod and 
   destroyMethod.
        •	name – allows you give name for bean
        •	initMethod – allows you to choose method which will be invoked on context     
                                  register
        •	destroyMethod – allows you to choose method which will be invoked on context 
                                         shutdown

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660151921747/iSl969fr7.png align="left")

@PreDestroy and @PostConstruct are alternative way for bean initMethod and destroyMethod. It can be used when the bean class is defined by us. For example;


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660151938689/in4EQCEu4.png align="left")

### @Path
- The @Path annotation’s value is a relative URI path indicating where the Java class will 
   be hosted: for example, /helloworld. 
- You can also embed variables in the URIs to make a URI path template. 
   For example, you could ask for the name of a user and pass it to the application as a 
   variable in the URI: /helloworld/{username}.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660152027776/eTlv1dSLn.png align="left")

### @GetMapping
- The @GET annotation is a request method designator and corresponds to the similarly 
   named HTTP method. 
- The Java method annotated with this request method designator will process HTTP GET 
   requests.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660152330413/O60RLwp1n.png align="left")

### @PostMapping
 - The @POST annotation is a request method designator and corresponds to the similarly 
    named HTTP method. 
-  The Java method annotated with this request method designator will process HTTP 
    POST requests.

### @PutMapping
- The @PUT annotation is a request method designator and corresponds to the similarly 
   named HTTP method. 
- The Java method annotated with this request method designator will process HTTP PUT 
   requests.

### @DeleteMapping
 - The @DELETE annotation is a request method designator and corresponds to the 
   similarly named HTTP method. 
- The Java method annotated with this request method designator will process HTTP 
   DELETE requests. 

### @Head 
- The @HEAD annotation is a request method designator and corresponds to the similarly 
   named HTTP method. 
- The Java method annotated with this request method designator will process HTTP 
   HEAD requests. 

### @PathParam 
- The @PathParam annotation is a type of parameter that you can extract for use in your 
   resource class. 
- URI path parameters are extracted from the request URI, and the parameter names 
  correspond to the URI path template variable names specified in the @Path class-level 
  annotation.

### @QueryParam
- The @QueryParam annotation is a type of parameter that you can extract for use in your 
   resource class. 
- Query parameters are extracted from the request URI query parameters.

### @Consumes  
- The @Consumes annotation is used to specify the MIME media types of representations a resource can consume that were sent by the client.

### @Produces   
- The @Produces annotation is used to specify the MIME media types of representations a resource can produce and send back to the client: for example, "text/plain".

## **Spring Transaction Management Annotations**

### @Transactional   
- The @Transactional annotation is the metadata that specifies the semantics of the 
   transactions on a method. We have two ways to rollback a transaction: declarative and 
   programmatic.
- In the declarative approach, we annotate the methods with the @Transactional 
   annotation. 
- The @Transactional annotation makes use of the attributes rollbackFor or 
   rollbackForClassName to rollback the transactions, and the attributes noRollbackFor or 
   noRollbackForClassName to avoid rollback on listed exceptions.
- The default rollback behavior in the declarative approach will rollback on runtime 
   exceptions.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660152777011/EY_9SdonQ.png align="left")

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660152782499/wBm9ByPb_.png align="left")

## **Spring entity validation annotations:**

### @Entity
- It specifies that the class is an entity and is mapped to a database table.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660152977086/XKb-tW9Pi.png align="left")

### @NotEmpty 
- to say that a list field must not empty.
### @NotNull 
- to say that a field must not be null.
### @NotBlank 
- to say that a string field must not be the empty string (i.e. it must have at least one character).
### @Min and @Max  
to say that a numerical field is only valid when it’s value is above or below a certain value.
### @Pattern
- to say that a string field is only valid when it matches a certain regular expression.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660153158594/wDk93bMLh.png align="left")

### @Validated 
 - is a class-level annotation that we can use to tell Spring to validate parameters that are passed into a method of the annotated class. 

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660153186685/VFFTK9UeG.png align="left")

### @Valid  
- annotation on method parameters and fields to tell Spring that we want a method parameter or field to be validated.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660153212601/-rqo_pemT.png align="left")


*Thank you for reading, Please like the article, It will encourage me to write more such articles. Do share your valuable suggestions, I appreciate your honest feedback!!*
