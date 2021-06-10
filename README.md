# Contents

- [Contents](#contents)
- [What is this project?](#what-is-this-project)
- [Engineering Principles](#engineering-principles)
- [Before a Client Project](#before-a-client-project)
- [Working with Clients](#working-with-clients)
  - [What has worked for us in the past](#what-has-worked-for-us-in-the-past)
- [Where to start with project processes](#where-to-start-with-project-processes)
- [Where to start with a technical design or architecture](#where-to-start-with-a-technical-design-or-architecture)
  - [Questions to consider](#questions-to-consider)
    - [What deployment platform will you use?](#what-deployment-platform-will-you-use)
    - [Other questions to consider](#other-questions-to-consider)
- [Soapboxes](#soapboxes)
  - [Angular](#angular)
  - [General Software Development Best Practices](#general-software-development-best-practices)
  - [Java](#java)
  - [Node.js](#nodejs)
  - [Python](#python)
  - [React](#react)
  - [Ruby / Rails](#ruby--rails)
  - [Other Non-Technical Topics](#other-non-technical-topics)

# What is this project?

This is a collection of preferred practices for web development at Rocket Insights. It comes from our collective experience working on software projects for many, many clients.

Let’s start by talking about what this project _is not_:

_This is not a list of rules you must follow when working on a development project at Rocket._

You're an adult. And we hired you to be part of Rocket because we think you're a good developer.

_This is not meant to be an end all be all documentation of everything we do and everything we believe._

The world changes, especially the tech world. More importantly, each client and project has its own subtleties and needs. The chances of even _being able to follow one set of rules_ for any given project is pretty much zero.

So, what is this project for then?

It’s to give Rocket developers a launching off point (see what we did there? 😁).

It’s to give Rocket developers ideas of where to start.

It’s to answer the question: “How do we usually do web development at Rocket?”

It's also to share with clients and prospective developer hires so they can get a flavor of how we do things here.

Finally, it's meant to be flexible as technology changes and our practices change over time. It's a living document, meant to be contributed to by everyone at Rocket. See [CONTRIBUTING](CONTRIBUTING.md) for details if you see something that's off or that you think needs to be added.

# Engineering Principles

Let's start with a story:

For many years, [new employees at Nordstrom's department store](https://signalvnoise.com/posts/2632-nordstroms-employee-handbook-mdash-short-and-sweet) were given a copy of the Nordstrom Employee Handbook, it was a single 5-by-8-inch gray index card that read:

```
Welcome to Nordstrom

We’re glad to have you with our Company. Our number one goal is to provide outstanding customer service. Set
both your personal and professional goals high. We have great confidence in your ability to achieve them.

Nordstrom Rules: Rule #1: Use best judgment in all situations. There will be no additional rules.

Please feel free to ask your department manager, store manager, or division general manager any question at any time.
```

_Use best judgment in all situations._ With all due respect to HubSpot’s culture code or Netflix’s ‘Freedom & Responsibility’ manifesto, it was Johan Nordstrom who invented the idea of individual responsibility back in 1887, and he was probably suffering from rickets at the time.

While it’s a stretch to say we have "no additional rules" at Rocket, we try to keep our rules and processes as light as humanly possible.

Here are some other rules of thumb you can follow:

- _"Snap In" to the client"_ - If the client is already using a tool or using a process, always go with what they already have/use, unless they’re explicitly asking for something different
- _"Strong opinions, loosely held"_ - Never be afraid to present a case for doing something the way you think is right, but at the end of the day, it’s the client’s call and you need to be flexible.
- _If in doubt, ask_ - We trust your judgement, but we also trust that when you hit a situation that might ruffle feathers, that you’ll reach out to the right people for input at the client and at Rocket. If you're in doubt as to who to ask or how to go about it, ask the executive sponsor of your project.

# Before a Client Project

What to make sure you know about the project or company before the project starts.

Try to find this out from the client or the exec sponsor.

Clients, this is also a handy list to have to prepare for Rocket starting a web project with you:

- [ ] Are we signing up for an ID with their organization for email/calendar/other access, or using our own ID's?
- [ ] Do they have a QA Department or people available to test the product?
- [ ] Do they have their own DevOps/Sys Admin organization?
- [ ] Do they have a process for on-boarding new engineers that we can adhere to?
- [ ] Are there any tools we can install upfront to cut down ramp-up time?
- [ ] How do they prefer we communicate? For example, Slack, email...
- [ ] If we need to request access to various systems, who should we speak with? Or, what is the process they have in place, if any? If possible get this access _before_ the project starts!
- [ ] Are they doing Agile or other similar process that we need to be aware of and involved in?
- [ ] What is the release process? How often do they deploy to production and how is that pipeline setup?
- [ ] How do they manage secrets and other credentials?
- [ ] What parts of the tech stack are non-negotiable and what parts are up for changing? Is there anything in the stack today they want us to avoid?
- [ ] Are we joining an existing team or forming our own team?
- [ ] How should we let them know about time off or Rocket Holidays? Do they have a calendar they want us to use?

# Working with Clients

You're an adult and we trust you can communicate with other human beings in a kind and respectful way. We like to have fun and [do silly things](https://www.newburyportnews.com/news/local_news/newburyport-companys-effort-haunts-historic-inn-street-building/article_b3731893-88d4-5742-87f1-1f40295fb32e.html). We want to have the kind of energy which makes other engineers work with us and more importantly, _enjoy it_.

Oh, but don't say the "F" word unless the client does first, please 😜

## What has worked for us in the past

Establishing trust with clients can make the difference between getting the job done and exceeding expectations, [Adam F's soapbox on this has good suggestions](soapbox/people/afraser.md) but here's a high-level overview:

- Communicate. A lot.
- Set expectations. Deliver on promises.
- Speak in terms of what makes people happy or unhappy.
- Big ideas are more likely to be entertained if they're already built. Build it, then show & tell.
- Make developers' lives easier through automation etc.
- Transcend your team by communicating with Design, UX, etc.
- Speak in terms of real users and use cases.
- Pay attention to detail. Delight developers, designers and users.
- Know when and how much to push back.
- Be careful talking about the future.

# Where to start with project processes

Our philosophy is "less is more." But you do need some process. At a minimum you should have:

- A daily standup. Slack or asynchronous is fine.
  - What did you do yesterday?
  - What are you doing today?
  - Any blockers?

Sometimes, during the contract process, we talk with the client indications of what process they prefer to use. Check with the projects' executive sponsor and see if that has been done or if we have some more freedom. In those cases, we don’t prescribe whether the team should use Scrum or Kanban, but pick one, and follow it’s core principles to run the project.

Pick a senior member of the team to be responsible for running the ceremonies. Consider making it a shared responsibility.

# Where to start with a technical design or architecture

The answer of where to start with a design for your project will likely come as part of a Statement of Work (SOW) or contract from the client. It will generally indicate that we’re going to implement a project in node/react/rails/java/rust/go/perl/pascal/assembly. We should use that as a basis for where to start. We rarely sign a contract without some general idea of the tech stack we're going to use.

If you're truly not sure, our `#engineering` Slack channel is a good place to pose your project's unique situation and get the Rocket hive mind to help you out.

## Questions to consider

Regardless of your application tech stack, there are some general things we think about when picking a tech stack:

### What deployment platform will you use?

For a smaller client with no plans to hire DevOps support, we recommend deploying to [Heroku](https://heroku.com/) as it has much lower maintenance overhead (in terms of effort, not cost) and also is easier to use. You will sacrifice capability, of course.

For clients who have, or plan to have a DevOps team, we recommend deploying to AWS and taking advantage of their full ecosystem. If the choice is there, we recommend using Docker Containers and Elastic Container Service. Some situations will call for differing AWS technologies, though.

### Other questions to consider

- Is there a lot of content frequently edited? Consider a headless CMS. See [Evaluating your tech stack - Content Management Systems](https://blog.rocketinsights.com/evaluating-your-tech-stack-content-management-systems/)
- Does the frontend need a _really_ simple API? If so, consider the use of something like [Firebase](https://firebase.google.com/) to start off with to create a simple API.
- Are there a lot of visualizations? Should we be considering some kind of off the shelf visualization tool instead of customizing every one of them?
- Do I really need a Single Page App? Is this a _really_ simple app that would benefit from simple Server Side Rendering?

`TODO` add other questions here

# Soapboxes

What's a soapbox? It's place where Rocket Engineers can share their opinions on a particular topic. It's a way for each engineer at Rocket to share their experience with the community. These are vetted through a group pull request process within Rocket.

You can find various topics you're looking for by using github code search in this repo like so:
![Code Search Example](https://user-images.githubusercontent.com/392778/108128277-7cf9d180-707a-11eb-9e64-3d618aeede9b.png)

It is fully acknowledged that each of these is a very personal take on a topic. Some of them might even conflict with each other.

You, dear developer, are an adult and are left to your own devices to take this information and take it
from there to implement, ask further questions, or ignore.

These are not meant to be comprehensive _by any means_. You may even find conflicting ideas in these documents. The idea is to give you a list of things our experienced engineers have found to _consider_ for your project.

## Angular

- [TJ B's Angular Soapbox](soapbox/angular/tjboyle.md)

## General Software Development Best Practices

- [Matt M's General Soapbox](soapbox/general/theothermattm.md)

## Java

- [Matt M's Java Soapbox](soapbox/java/theothermattm.md)

## Node.js

- [Matt M's Node.js Soapbox](soapbox/node.js/theothermattm.md)

## Python

- [Nico C's Python Soapbox](soapbox/python/nicolascarbone.md)

## React

- [Jake R's React.js Soapbox](soapbox/react/jakerainis.md)

## Ruby / Rails

- [Jon P's Rails Soapbox](soapbox/rails/jprincipe.md)

## Other Non-Technical Topics

- [Project handoff guide by Simon](soapbox/general/smonn-project-handoff.md)
- [Adam F. on building trust](soapbox/people/afraser.md)
- [Efficiency as a programmer](soapbox/general/smonn-efficiency.md)
