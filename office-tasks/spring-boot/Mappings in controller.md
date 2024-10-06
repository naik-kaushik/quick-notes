

### Background

As we know there are five types of HTTP methods in web standards, they are:
1. `GET`
2. `POST`
3. `PUT`
4. `PATCH`
5. `DELETE`

- So for each of these HTTP requests, we have a mapping in Spring which is assigned using Mapping Annotations.
- Also there is one additional annotation : `@RequestMapping` which is used to group different types of mappings for the same endpoint.

## `@GetMapping` 

#### Plain `GET` Request

1. `@GetMapping(<endpoint_here>)` is the typical syntax of `@GetMapping` annotation.

```java
@GetMapping("/health-check")  
    public String getApiStatus(){  
        return "OK";  
    }  
```

2. So in the above code, `@GetMapping("/health-check")` annotation above the function `getApiStatus` signifies that the endpoint `"/health-check"` responds whatever the function `getApiStatus` returns.
#### `GET` Request with path variable

1. Whenever we need to fetch a particular resource, we often perform a `GET` call on endpoints which look somewhat like `<base_uri>/resource/{resource_id}` .
2. Now such calls can be written in controllers using `@GetMapping` along with addition annotation `@PathVariable`

```java
@GetMapping("id/{userId}")  
public User getUserById(@PathVariable String userId){  
    // find and return user based on userId from database
    return user;  
}
```






## `@PostMapping` 

1. `@PostMapping(<endpoint_here>)` works in a similar way as compared to `@GetMapping`.
2. The only additional task that needs to be done in `@PostMapping` is that the payload needs to be parsed (`JSON` to `Object`).
3. Following snippet describes how the `data` or `payload` from the request ( in `JSON`) can be parsed and used at the server level.

```java
@PostMapping("/create-user")  
public boolean createUser(@RequestBody User newUser){
	// handle database insertion logic here
    return true;  
}
```


## `@DeleteMapping`

1. Inorder to delete a resource we use `DELETE` method.

```java
@DeleteMapping("id/{userId}")  
public boolean deleteUserById(@PathVariable String userId){  
    // return isDeleteSuccess ? true : false;  
    return true;  
}
```

## `@PutMapping`

1. Inorder to update a resource we use `PUT` method.

```java
@PutMapping("id/{userId}")  
public boolean updateUserById(@PathVariable String userId){  
    // return isUpdateSuccess ? true : false;  
    return true;  
}
```

