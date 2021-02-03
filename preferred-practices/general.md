# General Preferred Practices

Nothing in here should be language, platform or framework specific.

- Setup a build process right away, even if it's as simple as running linting at first! (see below)
- Setup code linting right away as part of your build process!
- Design for code to be tested. While not everyone agrees on Test Driven Development, all code should be written so that it can be easily tested without manual intervention. If you have to mock or stub a lot, you might be doing something wrong. Mocking and stubbing is like salt: Makes the tests tastes better, but too much and you ruin the meal.
- Setup some basic automated tests right away and run them as part of your build
- Document your API's
  - For plain old REST use [OpenAPI](https://www.openapis.org/)
  - For GraphQL use... GraphQL
- Have a naming standard for your API's. Consistently use camelCase or kebab-case, etc.
