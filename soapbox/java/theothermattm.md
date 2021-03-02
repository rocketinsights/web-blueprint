# [Matt's](https://github.com/theothermattm) Soapbox of Java Practices

- Use [Spring Boot](https://spring.io/projects/spring-boot) and [Spring Initializr](https://start.spring.io/) to start your project.
  - Spring Boot is everywhere and most java devs tend to know it. If not, it's well documented and easy-ish for others to pick up.
- Use [Lomboc](https://projectlombok.org/) if possible. It will avoid a ton of boilerplate!
- Prefer the use of a controller layer dedicated to manipulating any HTTP-type objects. Do _not_ let those bleed into any sort of meaningful logic. Separate those out into different `Service` classes in a separate package.
- Separate persistence logic into `Repository` classes in their own package.
- [Mockito](https://site.mockito.org/) is great for being able to unit test your code. Avoid overusing it - If you have a really complicated mock setup, consider refactoring your classes to make them do less things ([Single Responsibility Principle](https://en.wikipedia.org/wiki/Single-responsibility_principle) principle), or consider instead just writing an integration test to test things together (see below).
- Use [H2](http://h2database.com/) in memory database to create API integration tests against a "real" database. These tests will provide the most bang for the buck and are [pretty easy to setup with Spring Boot](https://www.baeldung.com/spring-boot-testing).
