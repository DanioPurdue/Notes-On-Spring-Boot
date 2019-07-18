
## [Reference](https://www.baeldung.com/spring-bean-annotations)
## `@ComponentScan`
Automatically scan a package for beans if component scanning is enabled.

## `@Component`
By default, the bean instances of this class have the same name as the class name with a lowercase initial. On top of that, we can specify a different name using the optional value argument of this annotation.

## `@Repository`
DAO or Repository classes usually represent the database access layer in an application, and should be annotated with @Repository:
## `@Service`
The business logic of an application usually resides within the service layer – so we’ll use the @Service annotation to indicate that a class belongs to that layer:
## `@Controller`
@Controller is a class level annotation which tells the Spring Framework that this class serves as a controller in Spring MVC:


[`@ConfigurationProperties`](https://www.baeldung.com/configuration-properties-in-spring-boot)
Used on top of class. @ConfigurationProperties works best with hierarchical properties that all have the same prefix. So we add a prefix of mail.
```java
public class ConfigProperties {
 
    private String host;
    private int port;
    private String from;
    private List<String> defaultRecipients;
    private Map<String, String> additionalHeaders;
    private Credentials credentials;
  
    // standard getters and setters
}
```
Configuration property files can support hierarchical structure.
```shell
#Simple properties
mail.hostname=mailer@mail.com
mail.port=9000
mail.from=mailer@mail.com
 
#List properties
mail.defaultRecipients[0]=admin@mail.com
mail.defaultRecipients[1]=owner@mail.com
 
#Map Properties
mail.additionalHeaders.redelivery=true
mail.additionalHeaders.secure=true
 
#Object properties
mail.credentials.username=john
mail.credentials.password=password
mail.credentials.authMethod=SHA1
```
## Using `@ConfigurationProperties` and `@Bean` method.
When we want to bind properties to a third-party component that is outside of our control
```java
public class Item {
    private String name;
    private int size;
 
    // standard getters and setters
}

//where you apply beans
@Configuration
public class ConfigProperties {
 
    @Bean
    @ConfigurationProperties(prefix = "item")
    public Item item() {
        return new Item();
    }
}
```
