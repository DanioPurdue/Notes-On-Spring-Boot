`@Component`
Intro on component: https://www.baeldung.com/spring-component-repository-service

you can use `@value()` to annotate a particular member.
However, if you want to annotate the entire class you should. use `@ConfigurationProperties(prefix="myconfig")` on top of the class.

## Profiles
change your configuration based teh development properties this decides the active environment you are in.
```java
spring.profiles.active=development,testing
```
application-development.properties
```java
msg=Hello from development properteis
```

You can also have different development environment in one block.
```java
enviroments:
  development:
    url:http//dev.bar.com
    name: Developer Setup
  production:
    url: http://foo.bar.com
    name: production setup
```

### Profile example
It only pick up functions based on certian profile
```java
@Configuration
public class DataSourceConfig {
  @Bean(name = "datasource")
  @Profile("development")
  DataSource development() {
     return new DataSource("my-development-url", 999);
  }
  
  @Bean(name = "datasource")
  @Profile("production")
  DataSource production() {
    return new DataSource("my-production-url",999);
  }
}
```

### Auto configuration


