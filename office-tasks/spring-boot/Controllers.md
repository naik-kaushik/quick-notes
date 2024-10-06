
>[!IMPORTANT]
>Methods inside a controller class should be public so that they can be accessed and invoked by the spring framework or external http requests.

### What are controllers?

1. By definition, A Controller is a class that implements operations defined by an application’s API. It implements an application’s business logic and acts as a bridge between the HTTP/REST API and domain/database models. 
2. In a nutshell, controllers define what an API call on a particular endpoint must serve.

### Example

- Let's say we have a controller for health check of the `api`. 
- In Spring the controller can be written in following way:


`src/main/java/com.dlogs.smartJournal/controllers/HealthCheck.java`

```java
package com.dlogs.smartJournal.controllers;  
  
import org.springframework.web.bind.annotation.GetMapping;  
import org.springframework.web.bind.annotation.RestController;  
  
@RestController  
public class HealthCheck {  
    @GetMapping("/health-check")  
    public String getApiStatus(){  
        return "OK";  
    }  
}
```