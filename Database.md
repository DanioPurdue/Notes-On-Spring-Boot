application.properties
Hibernate
You can use the h2 console to look into the database.
```java
spring.h2.console.enabled=true
spring.h2.console.path=/console
```

```java
@Entity
public class Post {
  @Id //id
  @GeneratedValue
  private Long id;
  
  private String title;
  private String 
  
  //Author
  @ManyToOne //we have many post belongs to one Author
  private Author author; 
  
  
}

@Entity
public class Author {
  @Id
  @GeneratedValue
  private Long id;
  private String firstName;
  private String lastName;
  
  //posts
  @OneToMany( mappedBy = "author" )
  private List<Post> posts;
}
```
##JPA
It allows us to map object to database
