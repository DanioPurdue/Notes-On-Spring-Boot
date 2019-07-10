![image-20190709000158258](/Users/daniowang/OneDrive/GitHub/Notes-On-Spring-Boot/MVC_picture.png)



```java
@Controller
public class GreetingController { 
  @RequestMapping("/")
  public String home() {
    return "hello spring boot"
  }
}
```

You can have the above request mapping both at the class level and the method level.

@RestController

@SpringBootApplication is the short hand for three other anotations



## Static Content

Certain folders. like static folders

## WebJars

It used to manange client side dependcies.

## Thymeleaf

Standard Dialects.

Standard expression syntax. Message Expression. Link URL expression.