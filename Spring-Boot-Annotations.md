
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
