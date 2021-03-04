# [Adam's](https://github.com/afraser) Working-with-humans Soapbox

The purpose of this repository is to document our engineering practices, and when you ask an engineer in the trenches of a project to talk about this sort of thing they might start talking about the stack they've chosen. A stack, even at a macro scale, is an implementation detail. The good stuff comes when we ask "why" and then ask it again and again.

The answer always circles back to _people_.

## Challenges we face as engineers very often require working around issues of trust, process, organizational structure, and culture.

At Rocket, the majority of our engineers have been around the block a time or two. We've seen most things built _many_ different ways, so our opinions come with a weight of experience. Regardless, we must repeatedly earn the trust of our clients. This is not always done easily, but it is a prerequisite if we wish to exceed expectations.

Unfortunately, we often find ourselves on projects with:

- Mountains of tech debt
- Poor CI/CD
- High-friction development process
- An inexperienced team
- Significant over-engineering
- Inconsistent implementation of designs

It is not hyperbole to say that every engineer at Rocket takes great personal pride in the _art_ of building something new, but it's hard to take pride in that art and work _around_ challenges like the ones listed above. We want to do better. We want to level up the team, pay down tech-debt, fix architectural problems at their source. We want out of meetings that are a total waste of time and we want in on the meetings that will help us build a better product.

None of these things can realistically be approached without first building trust. So how do we do that?

## Communicate.

Listen, ask questions, give updates, don't miss standup. The beginning of every project should start with a "high-touch" phase. Some (maybe most) clients mistakenly think we have everything we need before we do, make sure you reach out if you don't and request meetings with people who can answer your questions.

Have a low threshold for presenting ideas. You can get a good sense of the team by seeing how these ideas reverberate. Plus, sometimes the response will be "Wait, can we actually do that?"

## Set expectations. Deliver on promises.

This goes without saying, but building trust means working on what you said you're working on and delivering again and again.

## Explain how things made people happy or unhappy.

When justifying any decision, it's rarely enough to cite "literature" or "experience" and leave it at that. People need to hear _why_. Speaking from your own prior experience about what made people (users/developers) happy or unhappy will often convince a hesitant decision maker. This is useful when arguing for a particular engineering or design decision, or when considering changes to things like scrum process or meeting format.

## Build it, then show and tell.

New ideas are much more likely to get pulled in if they're already basically done. This is particuarly useful on slow-moving teams.

## Make developers' lives easier.

Automate things. Improve performance. Find pain points and fix them.

## Transcend your team.

Get decision makers on your side and/or find a wolf pack. Communicate with and become best friends with Design, UX, Product Owners, Architecture, DevOps, etc. Make sure you and your team don't feel siloed. Many companies have virtual walls between different teams. Ideally as you get to know other people you can just approach or message them directly, but sometimes the only line you'll have is email. Use whatever means is available.

## Speak in terms of real users and use cases.

The better you understand who is going to use the product, the better you will understand how it should be built. This is just one case where it pays to know people outside of the engineering team.

## Pay attention to detail.

Delight developers, designers and users. Putting the work in here pays dividends in trust. That said, don't let this derail you from delivering on your promises. And this goes without saying but don’t get sloppy (bad naming, missed edge cases, slow code, etc.).

<details>
  <summary>Examples...</summary>

  - Think hard about naming.
  - Use sensible abstractions and try to write “idiomatic” code adhering to framework patterns.
  - Provide sensible error handling for developers and users.
  - Always consider worst-case performance.
  - Always have a [SSOT](https://en.wikipedia.org/wiki/Single_source_of_truth).
  - Write unit tests.
  - Make it easy for developers to get the application running locally.
  - Avoid hacks and “magic numbers”.
    - If you can’t, leave notes in comments for future travellers.
  - Employ responsive styles and sensible css transitions.
  - Optimize for the intended platform and user: Phone or desktop? Consumer or professional?
  - Consider keyboard accessibility and shortcuts.
    - esc key closes modals, click-away dismisses popovers, etc
    - All UI (minimally links, buttons and inputs) should be keyboard accessible
  - Consider hover/focus/active states.
</details>

## Know when and how much to push back.

> Rocket Engineering: Strong opinions, loosely held. *

\* Some held more loosely than others.

This repository is a testament to those opinions that we hold a little closer to heart. Our engineers might not push back on which linter to use, but most would agree that linting is for the better. Ditto for test frameworks and testing. Our clients expect us to push back on any decision that might lead to poor product quality.

Every team culture is different. Some teams expect a more passionate discourse about new ideas and decisions, others quietly adhere to a status-quo that we might not initially be aware of. Try to be sensitive to this, and always be tactful and respectful.

## Be careful talking about the future.

We should always be considering handoff and future travelers in the codebase, but statements like "you/we will need/want" should never be unsubstantiated. This is another place where communicating with stakeholders, designers, and anyone else upstream is going to help you make better decisions and communicate those decisions.

eg: "The product team is working on features that will require this in V2. If we do this now we'll save ourselves the headache of changing it later."

## Consider international cultural differences.

Communication, leadership, and decision making styles vary across cultures. For example, in some cultures, if you deliver two things that someone requested and they respond with "Thank you so much! I loved Thing 1." This may tacitly imply that they would like you offer a different version of the second thing.

If you're interested in learning more about this, check out [The Culture Map](https://erinmeyer.com/books/the-culture-map/) by Erin Meyer.

You can also check out [this short video](https://hbr.org/video/embed/5476393165001/how-cultures-across-the-world-approach-leadership) for an overiew of how different cultures approach leadership, or listen to this [interview with Erin Meyer](https://armchairexpertpod.com/pods/erin-meyer).
