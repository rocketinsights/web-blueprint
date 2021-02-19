# [Jake's](https://github.com/jakerainis) Soapbox of React Practices

React is really just a view layer, and will require additional (most-often third party) tooling to build a full-fledged application. The React ecosystem is constantly evolving, which can make the tool selection process daunting. Sometimes trying a new tool is appropriate and should be done so at the architect's discretion. However, you should prefer a solution that won't be fought against and ideally one that is battle-tested. If they have a proven solution that has been previously used, consider using that setup as a jump-off to speed up development. 

## General React Practices
- Prefer Functional components and hooks over Class components.
- Prefer a project scaffold instead of writing a build from scratch. There is no silver bullet here, but common solutions at the time of this writing include:
  - [Create React App](https://reactjs.org/docs/create-a-new-react-app.html) for bundled single page applications on the client-side. 
  - [Next JS](https://nextjs.org/) for hybrid static and SSR applications. 
  - [Gatsby](https://www.gatsbyjs.com/) for statically generated sites. 
- Prefer the use of a linter such as [ESLint](https://eslint.org/) to enforce pattern conventions.
- Prefer using an auto-formatter such as [Prettier](https://prettier.io/) to enforce formatting conventions. 
- Prefer [React Router](https://reactrouter.com/) until something better comes along.
- Typescript...?
  - Pros: It's a fantastic way to navigate and debug (or prevent bugs before they happen) in large codebases and enforces predictability.
  - Cons: Requires a learning curve, particularly for those new to strong typing as well as additional tooling and configuration.
  - If it's not a requirement, consider the team you'll be working with and their preferences. If all are in favor, then prefer using TS as it will aid in project stability and readability as it scales. If it's going to make life harder, then leave it out.
  - Still unsure? Ask [Brandon Aaskov](https://github.com/brandonaaskov) from a safe distance.

## State Management
What a timeless topic! Dan Abramov has probably tweeted once or twice since the time of this writing, so when it comes to tooling specifics, just pick your poison (if applicable). [MobX](https://mobx.js.org/README.html) and [Redux](https://redux.js.org/) are common contenders. However, here are some considerations to ponder beforehand:
- Does your application actually have a need to manage complex state? Sometimes tooling gets in the way. If you're unsure, don't reach for it until you need it. In some applications, you might be able to get away some simple `useState` hooks or `Contexts`.
- [React Contexts](https://reactjs.org/docs/context.html) are great for managing relatively simple state across multiple components (or even globally at times), but they can become unwieldy and therefore should not be the de facto state solution.
- Sometimes, finite state machines can play an important role in a user flow (for example, a multi-step form wizard). While you can get away without it, a tool like [XState](https://xstate.js.org/docs/) can make life easier both in execution and testability. 

## Testing
- Choose a reputable framework. You can't go wrong with [Jest](https://jestjs.io/) when it comes to React.
- Prefer using [React Testing Library](https://testing-library.com/docs/react-testing-library/intro/) to anything else (even [Enzyme](https://enzymejs.github.io/enzyme/)) when you need to mount a component to make DOM assertions. 
- Prefer a tool like [msw](https://mswjs.io/) when mocking API implementations rather than manipulating your implementation to behave differently in a test environment.
- Prefer the use of reusable factories instead of manually mocking large objects. You can't go wrong with [Rosie](https://www.npmjs.com/package/rosie).
- Seek opportunities (where possible) to obfuscate complex business logic into functions outside of React components to make testing easier. Sometimes DOM assertions will be unavoidable, but mounting large/complex components can add a considerable amount of time to your test runs while only adding nominal coverage.
- Avoid snapshot testing.

## Styling
So many options, so little time. 
- Prefer a CSS-in-JS tool that allows for logic within the CSS and promotes usability.
- Prefer the use of variables for color palettes, font-families, common sizes, and anything else you might often reuse.
- Avoid inline styling (tip: use a lint rule to police this).
