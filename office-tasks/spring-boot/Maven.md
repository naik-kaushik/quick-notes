# What is maven?

> [!IMPORTANT]  
> If `mvn` doesn't works, you can use `mvnw` which is wrapper used by `intellij`.


1. A build tool that is used to build a java application.
2. Used to maintain dependencies, version and stuff (somewhat similar to `npm`).
3. When you want to add a dependency, all you do is go to maven repository and search for required dependency. Let's say we want to add `opencsv`. When we go to [mvnrepository](https://mvnrepository.com/), we get a declaration as follows:

	```xml
	<dependency>
	    <groupId>com.opencsv</groupId>
	    <artifactId>opencsv</artifactId>
	    <version>5.9</version>
	</dependency>
```

	just paste this code into your `pom.xml` and perform maven reload. That dependency will be downloaded and be available in external libraries.
4. It is also used to perform various tasks like:
	1. validation. (`mvn validate`)
	2. unit testing. (`mvn test`)
	3. To build a package. (`mvn package`)
	4. Clean target folder. (`mvn clean`)


