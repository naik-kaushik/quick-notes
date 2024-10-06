
> [!IMPORTANT]
> `Bean` in this regard is similar to a normal Java object. The class that is stored in IOC / application context is called as `bean`


# Inversion of Control

1. IOC or Inversion of Control is the concept of requesting bean from spring.
2. While using java conventionally, we use `new` keyword to create a new object and then use it into the code.
3. IOC enables us to find a created bean (in the application context) which can then be used to serve our purpose.

# How does IOC knows to store class ?

1. Whenever we add the `@Component` annotation above the class, it tells IOC / Application context to store that class in itself.
2. So basically, adding `@Component` annotation registers the cl