
>[!IMPORTANT]
>1. `@ComponentScan` scans for the beans in the same package itself. It cannot access anything outside it's package.


#### `@SpringBootApplication` is responsible for performing below tasks :

1. Configuration.
	1. Used with the `@Bean` notation. example `@RestController` uses `@Configuration` annotation.
2. EnableAutoConfiguration.
3. ComponentScan.
	1. Scans for all beans in the given package.
