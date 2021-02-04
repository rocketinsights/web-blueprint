# General Preferred Practices

Nothing in here should be language, platform or framework specific.

- Setup a build process right away, even if it's as simple as running linting at first! (see below)
- Setup code linting right away as part of your build process! Even better, setup a code formatting tool (like Prettify for Javascript) to _auto correct_ these things on pre-commit hooks so they don't become an issue at all.
- Design for code to be tested. While not everyone agrees on the use of Test Driven Development, all code should be written so that it can be easily tested without manual intervention. If you have to mock or stub a lot, you might be doing something wrong. Mocking and stubbing is like salt: It makes the tests taste better, but too much and you ruin the meal.
- Setup some basic automated tests right away and run them as part of your build
- Run the build on pull request merges, somehow, some way. Fail the build if linting or tests fail. [GitHub Actions](https://github.com/features/actions) are your friend!
- Write a good README.md. There are plenty of resources to help you write a good README:
  - https://bulldogjob.com/news/449-how-to-write-a-good-readme-for-your-github-project
  - https://thoughtbot.com/blog/how-to-write-a-great-readme
  - https://www.makeareadme.com/
  - https://github.com/matiassingers/awesome-readme

## Backend/API Specific Practices

- Document your API's
  - For plain old REST use [OpenAPI](https://www.openapis.org/)
  - For GraphQL use... GraphQL
- Have a naming standard for your API's. Consistently use camelCase or kebab-case, etc.
- Prefer using UTC for _storing_ timestamps where possible. Show timestamps to users depending on preferences.
- Prefer the use of [optimistic locking](https://en.wikipedia.org/wiki/Optimistic_concurrency_control) for persisting data. It will prevent concurrent access issues and generally _stays out of the way_. Build it in from the start, and you'll be on easy street. Do it after you've gone to prod and you're gonna have a bad time.
  - For example, in Node.js, [sequelize has this built in](https://sequelize.org/master/manual/optimistic-locking.html). Many ORM's do.
