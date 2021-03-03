# [Adam's](https://github.com/afraser) Working-with-humans Soapbox

The purpose of this repository is to document our engineering practices, and when you ask an engineer in the trenches of a project to talk about this sort of thing they might start talking about the stack they've chosen. A stack, even at a macro scale, is an implementation detail. The good stuff comes when we ask "why" and then ask it again and again.

The answer always circles back to _people_. 

## Challenges we face as engineers very often require working around issues of trust, process, organizational structure, and culture. 

At Rocket, the majority of our engineers have been around the block a time or two. We've seen most things built _many_ different ways, so our opinions come with a weight of experience. Regardless, we must repeatedly earn the trust of our clients. This is not always done easily, but it is a prerequisite if we wish to exceed expectations.

We often find ourselves on projects with:

- mountains of tech debt
- poor CI/CD 
- high-friction development process
- an inexperienced team
- significant over-engineering
- inconsistent implementation of designs

It is not hyperbole to say that every engineer at Rocket takes great personal pride in the _art_ of building something new, but it's hard to take pride in that art and work _around_ challenges like the ones listed above. We want to do better. We want to level up the team, pay down tech-debt, fix architectural problems at their source. We want out of meetings that are a total waste of time and we want in on the meetings that will help us build a better product.

None of these things can realistically be approached without first building trust. So how do we do that?

## Communicate

Listen, ask questions, give updates, don't miss standup. The beginning of every project should start with a "high-touch" phase. Some (maybe most) clients mistakenly think we have everything we need before we do, make sure you reach out if you don't and request meetings with people who can answer your questions.

## Deliver on promises

This goes without saying, but building trust means working on what you said you're working on and delivering again and again.

## Explain how things made people happy or unhappy

When justifying any decision, it's rarely enough to cite "literature" or "experience" and leave it at that. People need to hear _why_. This is useful when arguing for a particular engineering or design decision, or when considering changes to things like scrum process or meeting format.

## Build it, then show and tell.

New ideas are much more likely to get pulled in if they're already basically done. This is particuarly useful on slow-moving teams.

## Make developers' lives easier.

Automate things. Improve performance. Find pain points and fix them.

## Transcend your team.

Get decision makers on your side and/or find a wolf pack. Communicate with and become best friends with Design, UX, Product Owners, Architecture, DevOps, etc.

## Pay attention to detail.
Don’t get sloppy (slow code, bad naming, missed edge cases, etc.). Delight developers, designers and users. That said, don't let the details derail you from delivering on your promises.

- Think hard about naming. 
- Use sensible abstractions and try to write “idiomatic” code adhering to framework patterns.
- Provide sensible error handling for developers and users.
- Always consider worst-case performance.
- Always have a single source of truth for application state.
- Write unit tests.
- Avoid hacks and “magic numbers”. If you can’t, leave notes in comments for future travellers.
- Employ responsive styles and sensible css transitions.
- Optimize for the intended platform and user: Phone or desktop? Consumer or professional?
- Consider keyboard accessibility and shortcuts.
  - esc key closes modals, click-away dismisses popovers, etc
  - All UI (minimally links, buttons and inputs) should be keyboard accessible
- Consider hover/focus/active states.

## Consider culture when working internationally

This is something I'm still learning but in Erin Meyer's book [The Culture Map](https://erinmeyer.com/books/the-culture-map/) she outlines 8 axes along which people from different countries may differ:

- Communicating: explicit vs. implicit
- Evaluating: direct negative feedback vs. indirect negative feedback
- Persuading: deductive vs. inductive
- Leading: egalitarian vs. hierarchical
- Deciding: consensual vs. top down
- Trusting: task vs. relationship
- Disagreeing: confrontational vs. avoid confrontation
- Scheduling: structured vs. flexible

To get a sense of how these might be applied, this video provides an overiew of how different cultures approach leadership: https://hbr.org/video/embed/5476393165001/how-cultures-across-the-world-approach-leadership
