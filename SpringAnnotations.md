Spring Boot Annotations That You Must Know

- @SpringBootApplication - Combines @Configuration, @EnableAutoConfiguration, and @ComponentScan.

- @EnableAutoConfiguration - Automatically configures the Spring application based on the classpath and other beans.

- @SpringBootConfiguration - Indicates that a class provides Spring Boot-specific configurations.

- @ComponentScan - Specifies the packages that the Spring framework should scan for components, configurations, and services.

- @RestController, @Controller - Annotations for web controllers, with @RestController combining @Controller and @ResponseBody.

- @RequestMapping, @GetMapping, @PostMapping, @PutMapping, @DeleteMapping, @PatchMapping - Maps web requests to Spring controller methods.

- @ResponseBody - Indicates that the return type should be written straight to the HTTP response body.

- @PathVariable, @RequestParam - Bind method parameters to URL variables and request parameters respectively.

- @CrossOrigin - Enables cross-origin requests for specific handler classes or handler methods.

- @Component, @Service, @Repository - Indicate that a class is a Spring-managed component, service, or repository.

- @Autowired - Marks a constructor, field, setter method, or config method for autowiring.

- @Qualifier - Designates which bean to autowire when there is more than one candidate.

- @Primary - Indicates that a bean should be given preference when autowiring if multiple candidates exist.

- @Bean - Indicates that a method produces a bean to be managed by the Spring container.

- @Value - Injects values into configuration parameters.

- @ConfigurationProperties - Binds and validates external configurations to a configuration object.

- @PropertySource - Specifies a location of properties to be added to Spring's environment.

- @Profile - Indicates that a component is eligible for registration when certain profiles are active.

- @Conditional - Conditionally include or exclude parts of configuration based on certain conditions.

- @Scheduled - Marks a method to be run at periodic intervals.

- @SpringBootTest, @DataJpaTest, @WebMvcTest, @JsonTest, @WebFluxTest - Used for different types of tests in Spring Boot, from integration testing to specific layers testing.
