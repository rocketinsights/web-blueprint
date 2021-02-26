# [TJ's](https://github.com/tj-boyle) Soapbox of Angular Practices

Generally speaking, Angular is relatively hand-holdy when it comes to what tech to use regarding testing, stylization, etc. There are always other options though, and Angular doesn't necessarily use the best one out of the box.

Additionally, it makes sense to at least be aware of some recommended coding styles when it comes to developing an Angular application.

This soapbox is a collection of those thoughts on various subjects for Angular projects.

***

## Testing
Angular comes preinstalled with [Jasmine](https://jasmine.github.io/) set up, but it's somewhat outdated and unreliable when it comes to being able to mock dependencies. A more modern solution that is recommended is [Jest](https://jestjs.io/).

Things to keep in mind:
- Every new feature should have corresponding unit tests to test any and all conditional paths.
- Mock called functions when possible, to ensure you are only testing one function at a time
- Avoid testing large object comparisons, instead opting to test specific attributes exist on both objects
  - This avoids brittle tests and keeps the tests themselves smaller and more readable
- Avoid testing 3rd party libraries. 
  - These libraries, especially in Angular, prove to be difficult to test properly and should really have their tests handled by the contributors of said library. 

***

## Linting
The newest version of Angular has dropped support for [TSLint](https://palantir.github.io/tslint/), in favor of [ESLint](https://eslint.org/) - due to it's ability to lint both JS _and_ TS files. 

Things to keep in mind:
- Dont reinvent the wheel, use an imported linting configuration
- Install relevant linter extension for IDE
- Confirm entire team is configured correctly, to avoid linting mismatch issues

*** 
## Prettifying
For Angular, [Prettier](https://prettier.io/) is the top of the game for auto code cleanup, and with a little work it can mesh nicely with existing linters

Things to keep in mind:
- Don't reinvent the wheel, fall back on the default configurations as much as possible
- Install relevant prettifying extension for IDE
- If using Prettier, make sure it's version locked in `package.json` 
  - Code styles can change drastically even between patch versions, and if two developers have two different versions they're going to be ping-ponging Prettier changes back and forth

***

## Git Hooks
When it comes to making sure that tests pass, the build succeeds, linting and prettifying are run, etc - [Git Hooks](https://git-scm.com/docs/githooks) are the answer. They allow you to hook in to Git processes to ensure various commands are run, with the most often used ones being `pre-commit` and `pre-push`.

For Angular (and really any node project) [Husky](https://github.com/typicode/husky/tree/master) is a great choice for implementing these - as it allows you to configure Git Hooks in code, and automatically installs them on every developers machine, taking away the manual step of making sure they're configured and working correctly. 

***

## Coding Style Guide
Generally speaking, it's good for Angular code to follow the [Angular Coding Style Guide](https://angular.io/guide/styleguide) developed and released by Angular themselves, as well as most of [Microsoft’s Typescript Coding Guidelines](https://github.com/Microsoft/TypeScript/wiki/Coding-guidelines) for Typescript code styling. It's worth noting that Microsoft themselves _strongly_ believes that the coding guidelines they outline should not be prescriptive (probably because they were getting so many opinions and questions about them) - but nonetheless gives the choice to adopt for your own usage as necessary.

The below outlines some additional consistency standards not mentioned in the above guides, and also not captured by Linters or Prettifiers.

Please keep in mind that every developer has opinions, but consistency trumps opinion so it’s important a standard is selected and followed to maintain the health of the repository. <br>
**In other words, that standard doesn't have to be _this_ one, but it should be _some_ one.**

<br>

### Existing Code Pattern - MOST IMPORTANT RULE
When coding, follow the pattern set out by pieces of code doing similar things.
If you’re making a module, look at other modules. A service, look at other services. A component. look at other components.

This rule will help you 99.9% of the time. 
Again, consistency is key so following the existing pattern will likely be your answer to how you should style new code.

If you feel an existing pattern is incorrect bring it up to the team for a discussion, so that the team can move existing code over to follow the new pattern, rather than have multiple standards at once.

<br>

### Import statements
Avoid unpatterned and inconsistent import statements

Import statements should follow the consistent pattern of:
```
<Angular imports>

<3rd party imports>

<Internal open source library imports (currently none)>

<Local imports>
```

<br>

### Private Class Properties
Avoid use of `_` preceding a private property when not necessary, IE when not using getters and setters of the same name, instead opting for a readable variable name

<br>

### Comments
Avoid _overuse_ of comments.

Not every function or piece of code needs a comment - in an ideal world all code should speak for itself, with standards of variable naming and code styling helping to that end. 

Instead opt for using JS Doc style comments where it makes sense - when a piece of code may not be straightforward or make sense at first glance

<br>

### Folder Structure
Avoid flat folder structures.

Instead opt to put nested components and code pieces into similarly nested folders.

This allows for more modularized component orgnization, and makes it easier to quickly find separate parts of the codebase.

IE:
```
webhooks/
--add-webhooks/
----add-webhooks.component.ts
----add-webhooks.component.html
--webhooks.component.html
--webhooks.component.ts
--webhooks.module.ts
```

<br>

### Component Code Ordering
Avoid unpatternened and inconsistent code ordering in components. 

Code within a component could, for example, follow the consistent pattern of:

```
<Class variables excluding getters and setters>

<Constructor>

<Implementation functions such as ngOnInit()>

<Getters and Setters>

<Public functions>

<Private functions>
```

<br>

### Templating
Avoid templating directly in the component declaration using `template`, instead creating an html file specific to the component and load it via `templateUrl`

<br>

### Template variables
Avoid using overly complex variable setting on inputs and outputs in any components used

Instead opt to set the variable in the component code in a Getter or Setter. 