### Stereotype annotation

- `@RestController`: provide hints for Spring that the class plays a specific role. in this case, it's a web `@Controller` for handling incoming web requests.
- `@RequestMapping`: provides routing information.

### Meta annotation

`@SpringBootApplication`: combines `@SpringBootConfiguration`, `@EnableAutoConfiguration` and `@ComponentScan`


```java
package com.example;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RestController;

@RestController
@SpringBootApplication
public class MyApplication {

	@RequestMapping("/")
	String home() {
		return "Hello World!";
	}

	public static void main(String[] args) {
		SpringApplication.run(MyApplication.class, args);
	}

}
```

Reference: https://docs.spring.io/spring-boot/tutorial/first-application/index.html