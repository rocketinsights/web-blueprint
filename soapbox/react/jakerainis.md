# [Jake's](https://github.com/jakerainis) Soapbox of React Practices

React is really just a view layer and will require additional (most-often third party) tooling to build a full-fledged application. The React ecosystem is constantly evolving, which can make the tool selection process daunting. Sometimes trying a new tool is appropriate and can be done so at the architect's discretion. However, you should prefer a battle-tested solution that won't be fought against.

## General React Practices
- Prefer function components and hooks over class components (more info on [component composition](https://reactjs.org/docs/components-and-props.html#function-and-class-components)).
- Prefer a project scaffold instead of writing a build from scratch. There is no silver bullet here, but common solutions at the time of this writing include:
  - [Create React App](https://reactjs.org/docs/create-a-new-react-app.html) for bundled single page applications on the client-side. 
  - [Next JS](https://nextjs.org/) for hybrid static and SSR applications. 
  - [Gatsby](https://www.gatsbyjs.com/) for statically generated sites. 
- Prefer the use of a linter such as [ESLint](https://eslint.org/) to enforce pattern conventions.
- Prefer using an auto-formatter such as [Prettier](https://prettier.io/) to enforce formatting conventions. 
- Typescript...?
  - Pros: It's a fantastic way to navigate and debug (and oftentimes prevent bugs before they happen) in large codebases and enforces predictability.
  - Cons: Requires a learning curve, particularly for those new to strong typing as well as additional tooling and configuration.
  - If it's not a requirement, consider the team you'll be working with and their preferences. If all are in favor, then prefer using TS as it will aid in project stability and readability as it scales. If it's going to make life harder, then leave it out.
  - Still unsure? Ask [Brandon Aaskov](https://github.com/brandonaaskov) from a safe distance.

## State Management
Before reaching for a tool, consider if your application actually needs to manage complex state. Sometimes tooling gets in the way. You might be able to get away some simple `useState` or `useContext` hooks. Just remember that while [React Contexts](https://reactjs.org/docs/context.html) are great for managing relatively simple state across multiple components (or even globally at times), they can quickly become unwieldy and therefore should not be the de facto state solution.
- If you choose to reach for a library, pick something reputable. [MobX](https://mobx.js.org/README.html) and [Redux](https://redux.js.org/) are common contenders, but there are many solutions out there.
- Sometimes, finite state machines can play an important role in a user flow (for example, a multi-step form wizard). While you can get away without it, a tool like [XState](https://xstate.js.org/docs/) can make life easier both in execution and testability. It also might eliminate the need for a more heavy-handed state management library.

## Testing
- Choose a reputable framework. You can't go wrong with [Jest](https://jestjs.io/) when it comes to React.
- Prefer using [React Testing Library](https://testing-library.com/docs/react-testing-library/intro/) to anything else (even [Enzyme](https://enzymejs.github.io/enzyme/)) when you need to mount a component to make DOM assertions. 
- Prefer a tool like [msw](https://mswjs.io/) when mocking API implementations rather than manipulating your implementation to behave differently in a test environment.
- Prefer the use of reusable factories (check out [Rosie](https://www.npmjs.com/package/rosie)) instead of manually mocking large objects.
- Where possible, seek opportunities to obfuscate complex business logic into functions outside of React components to make testing easier. Sometimes DOM assertions will be unavoidable, but mounting large/complex components can add a considerable amount of time to your test runs while only adding nominal coverage.
- Avoid snapshot testing.

## Styling
So many options, so little time! In general, however you decide to approach styling should allow for scale and reusability. In other words, don't rely on a single overgrown `.css` file. 

Before making any big decisions, reach out to the creatives you'll be working alongside and see what they're cooking up. Sometimes designers choose to pull from a UI library (e.g. [Material UI](http://material-ui.com/)), and it might make sense for you to use that library as your foundation.

When it comes to approach:
- Prefer an approach to styling that promotes scale and reusability:
  - [SASS](https://create-react-app.dev/docs/adding-a-sass-stylesheet/) allows you to dictate your own organizational system via partials.
  - [CSS Modules](https://css-tricks.com/css-modules-part-1-need/) are a solid way to scope styles and can also be organized as you see fit. 
  - CSS-in-JS solutions like [Emotion](https://emotion.sh/docs/introduction) or [styled-components](https://styled-components.com/) are extremely powerful as you can mix in JS logic to conditionally output styles. Just be aware of the caveats when you make your choice (bundle size, caching, dealing with [FOUC](https://en.wikipedia.org/wiki/Flash_of_unstyled_content), etc).
  - [Tailwind](https://tailwindcss.com/) is growing in popularity and offers a comprehensive class decorator approach to styling.
  - [Theme UI](https://theme-ui.com/) is a lightweight provider that offers common (and extendable) componentry along with an easy-to-use object interface.
- Prefer the use of variables for color palettes, font-families, common sizes, and anything else you might often reuse.
- Avoid inline styling. You can also configure your linter (e.g. [ESLint](https://eslint.org/)) to police this.

