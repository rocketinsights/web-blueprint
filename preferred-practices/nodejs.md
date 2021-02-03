# Node.js Preferred Practices

Also see [Javascript preferred practices](javascript.md).

- Use an [LTS](https://nodejs.org/en/about/releases/) version of node, not simply just "the latest version"
- Prefer the use of a logging library rather than the console. Even if using a logging framework over the console seems like overkill at first, its not hard to setup, and having the ability to dial logging levels up and down and output logs to different formats easily will benefit the project over time. We have had good luck with [winston](https://github.com/winstonjs/winston)
- Prefer [Express.js](http://expressjs.com/) over other newer or less widely used frameworks. We want to strive for familiarity when other developers take over a codebase. This is one of the few exceptions to the "no specific tools" rule we have in this document.
- Don't roll your own auth. Prefer the use of a well-supported library like [Passport](http://www.passportjs.org/) for authentication related stuff.
- Don't roll your own configuration management. Prefer a library like [dotenv-safe](https://github.com/rolodato/dotenv-safe) for managing secrets and configurations. We've found that dotenv-safe is a great way to do this, while making sure that the app _fails fast_ upon startup if a required configuration is not available.
- Don't roll your own request validation. Use a validation framework (like [joi](https://github.com/sideway/joi) or something similar)!
- Prefer the use of a controller layer dedicated to manipulating req/res and the next() callback. Do _not_ let those bleed into any sort of meaningful logic. Separate those out into different modules (`Service`s)
- When possible and useful, prefer separating persistence logic into its own layer. (`Repository`s)
- ORM's - Most of us use ORM's for database access. But, we can't seem to come to a consensus on the best ORM to use for node these days. Our current opinion is that most of them suck. Here's some thoughts based on our experience:
  - [Sequelize](https://sequelize.org/) is the big kahuna in this space, but its kinda hard to use and its features are limited
  - [TypeORM](https://typeorm.io/#/) is good if you're using TypeScript, and is very full featured, but we've found it's difficult and picky to setup and while it does a lot of things, it doesn't do many things _particularly well_.
  - `TODO` what else?
- Prefer handling errors in one place: middleware. Throw error objects in code and let middleware catch them and translate them into a standard format for HTTP status codes.
- _Have automated tests using a well known framework_. Many at Rocket prefer [Jest](https://jestjs.io/). Even if it's better, don't use an obscure one. We want to make sure that we're handing over things that are easy to maintain for clients.
- Consider using one of our boilerplates as a starting point which take many of these preferred practices into account and have already been laid out for you:
  - [node-express-rest-boilerplate](https://github.com/rocketinsights/node-express-rest-boilerplate) express based with different database flavors
  - [blazing edge api-skeleton](https://github.com/blazing-edge-labs/api-skeleton) - Koa based, not express based, but solid concepts and setup here.
