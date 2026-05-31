---
title: "The Role of a Product Manager in the AI Era"
excerpt: "Two years ago I made six predictions about how the PM role would change. I got some right. But the one I missed completely might be the most important one of all."
date: 2026-04-26
categories:
  - Product Management
  - AI
tags:
  - product management
  - artificial intelligence
  - product manager role
  - AI era
show_date: true
author_profile: true
published: true
header:
  overlay_image: /assets/images/header/ai_pm_era.jpg
  overlay_filter: 0.7
  teaser: /assets/images/header/ai_pm_era.jpg
  og_image: /assets/images/header/ai_pm_era.jpg
toc: true
toc_label: "The Evolving PM"
toc_sticky: true
permalink: /role_of_pm_in_ai_era/

---

In 2024, I wrote a piece [6 ways the role of a product manager is going to change in the next decade](/6_ways_pm_role_will_change/) for Scotia Digital's Future Fest Craft Magazine with six predictions about how the PM role would change over the next decade. Two years later, most of them have already happened. That tells you something — I was too conservative on the timeline. Predicting the next ten years now feels like a category error. The window I'd actually defend is twelve to twenty-four months, and even that might be generous.

Looking back at that piece, plus my [2022 post on the role of a PM](/The-Role-of-a-Product-Manager/), I got several things right. But the most important shift I missed wasn't a skill or a tool. It was a shift in where the constraint sits.

## The bottleneck moved

The traditional 6:1 ratio of engineers to PMs assumed engineering was the expensive, scarce thing. Six people building, one person figuring out what to build. That assumption has cracked.

Andrew Ng claims his teams now build in a weekend what used to take six engineers three months.[^1] I'd take the specific numbers with salt — it's a hot take, not data — but the directional point is hard to argue with. The constraint has moved. The question is no longer *can we build this?* It's *what exactly should we build, and should we build it at all?*

Some AI-native teams have flipped the ratio entirely, running closer to two PMs per engineer. I'm skeptical of that as a stable equilibrium. What I think is actually happening is closer to what Cat Wu describes: the roles aren't shifting in headcount, they're collapsing into the same person.[^2] An engineer with strong product sense can move without a PM. A PM with strong building skills can ship code. The interesting question isn't the ratio — it's whether enough product judgment exists in the room.

So when I say "product management has become the bottleneck," I don't mean the job title. I mean the function: deciding what's worth building when building is no longer the limiting factor. That function used to be split across PM, design, and engineering through a series of handoffs. The handoffs were the slow part. Now the slow part is the decision itself.

This is the lens I'd hold onto for the rest of the piece: every shift below is downstream of this one.

## What my 2024 predictions got right — and where they were too small

**What was directionally right.** AI-assisted PM work has come true faster than I described — synthesizing research, drafting PRDs, writing competitive analyses in minutes is the present baseline, not a future state. The push for AI fluency has accelerated past my framing of "baseline ML concepts." Today's bar is evaluation design, model failure-mode awareness, and direct work with agentic systems. And the focus on customer-centricity holds. When anyone can ship a product in a weekend, deep user empathy and problem understanding is one of the few remaining moats.

**What was too small.** I predicted "the rise of the product visionary" - PMs who anticipate trends and translate them into compelling roadmaps. Not wrong, but too abstract. Visionaries operating on six-to-twelve-month cycles are too slow for what's emerging. The actual skill is more operational: **product taste**. Knowing what's good before users tell you, evaluating fast, deciding faster.

I also under-described how much the role boundaries would dissolve. I called out cross-functional collaboration; what's actually happening is structural. LinkedIn replaced its Associate PM program with a "Product Builder" program that trains people across product, design, *and* engineering simultaneously. That's not adjacent to the role. It's a redefinition of who gets hired into it.

And I missed the bottleneck shift entirely.

## What's getting disrupted

**The information-mover PM is in trouble.** Nikhyl Singhal's framework of "information movers vs. builders" is the one I keep returning to.[^3] The information mover synthesizes research into a doc, moves slides between teams, aligns stakeholders, writes the PRD. Useful work, but increasingly automatable. AI can do the information movement — not as well as a skilled PM, but well enough, fast enough, that synthesis-as-edge is gone.

The uncomfortable implication: a meaningful share of "successful" PM careers were built on coordination skills that aren't differentiating anymore. I've watched this play out in my own org - the PMs who struggled when AI entered their workflow were the ones whose primary value was moving information cleanly between teams. The ones who thrived had a point of view about what to build and could defend it.

**The iteration cycle has collapsed.** Cat Wu puts the compression in one sentence: "What used to take six months now can take one day." That doesn't just change how teams operate — it breaks the premise of annual roadmapping and the PM as long-horizon-thinker. Jenny Wen describes the same compression on the design side: "Vision used to be six months out. Now it's three to six weeks."[^4]

The 12 months roadmap is quietly becoming a liability. It implies a level of certainty about what will matter in more than three months that nothing about the current environment supports. Some teams started to replace roadmaps with operating principles — clear enough to guide daily decisions, loose enough to update weekly.

## What the role is becoming

### The PM as judgment engine

The scarce resource in product development is no longer execution speed. AI provides that. It's the quality and speed of decisions made under uncertainty.

Andrew Ng says his teams are "increasingly relying on gut" for decisions that used to require weeks of A/B testing — he calls A/B testing one of the slowest strategies in his portfolio. When you can prototype in a day, waiting a week for statistical significance is a competitive disadvantage, not a discipline.

This is what the role is converging on: someone who can make high-quality decisions quickly, on incomplete data, and be right often enough to matter. It's the part of the job that was always the point but was usually buried under coordination work. Now the coordination is gone and there's nowhere to hide.

### The PM as taste-maker

I'm going to put a stake in the ground on what taste actually means, because the term gets thrown around without definition.

**Product taste is the ability to look at a candidate solution and predict - accurately, quickly, before users see it - whether it will work.** It's pattern recognition built from many small, fast cycles of *I think this will land → ship → see what happened.* It's the muscle that lets you reject nine of ten AI-generated options in five minutes and explain why the tenth wins. It's not vision. Vision points at a horizon. Taste evaluates an artifact in front of you, now.

You build taste the way Aakash Gupta describes: by evaluating a high volume of prototypes, fast, with stakes attached.[^5] A PM who reviews fifteen prototypes a week develops taste faster than a PM who reviews one spec a month. Speed creates compounding judgment — every cycle is a feedback loop, and the loops compound.

The risk worth naming: taste built without user contact becomes preference dressed up as judgment. Real taste stays calibrated against real users. Without that calibration, you're not exercising taste; you're exercising opinion.

### The PM as responsible AI owner

This is the part of the role I find most under-discussed and most consequential.

When your product ships AI-powered recommendations, automated decisions, or generative outputs, the PM owns the failure modes. Not legal. Not the ethics committee. The PM who shipped it. That includes understanding where models hallucinate, how bias enters training data, what transparency means for your specific users, and when to pump the brakes on a feature that technically works but shouldn't ship.

Marty Cagan recently wrote that "most product managers will be expected to understand how the enabling AI technology works, what the range of risks involved are, and the work required to mitigate them."[^6] That's the right framing. The reality I've seen is messier — most PMs aren't there yet, and the gap between "ships AI features" and "owns AI failure modes" is where a lot of bad product decisions are quietly being made.

This responsibility wasn't in any PM job description in 2022. It's in most of them now.

## What this means for the profession

I want to be direct about implications.

If most of your time goes to documentation, status updates, planning facilitation, and synthesizing information for other people to act on — that's a role under pressure. Not in five years. Now.

If you're early in your career, the traditional junior PM apprenticeship is narrowing. The entry-level tasks that used to count as learning the craft are automating. LinkedIn's APM-to-Product-Builder shift is the institutional signal. What earns a seat at the table now is proof of taste and judgment, not proof of process compliance.

If you're wondering what to do instead: build things. Use the tools available — prototype something, ship a small product end to end, evaluate fifteen things this week instead of one. The old APM value was learning process through repetition. The new value is developing judgment, and you develop judgment by making hundreds of small product decisions, not by facilitating someone else's.

Ant Murphy's 2026 survey of PMs found that 59% rank strategy and business acumen as the most important skills for the next two-to-three years.[^7] Not communication. Not execution. Not collaboration. Strategy. The profession knows what's coming.

## Back to the bottleneck

If the bottleneck has moved to judgment, the implication for any PM reading this is simple. The job is no longer to coordinate the work of building. The job is to make the decisions that determine whether the building was worth doing.

That sounds obvious until you look at how most PM time is actually spent. Most PMs I know — including, on bad weeks, me — still spend the majority of their hours on synthesis, alignment, and status. The work that maps to the new bottleneck — evaluating prototypes, sharpening point of view, owning failure modes — gets squeezed into whatever time is left. The shift the role demands isn't a new skill stack. It's a reallocation of where the hours go.

For PMs who lead with judgment, taste, and curiosity about what users actually need, this is the most exciting time the role has ever offered. The coordination overhead is lifting. What remains is the part that was always supposed to be the point.

"The builders — the people who actually think, who create, who have opinions," Singhal says, "there's a renaissance coming for them."

I believe him. I'm building for it.

---

*The harder question I'd love your take on: which of the five specialization renames feels most wrong to you, and what would you call it instead?*

[^1]: Andrew Ng on the PM bottleneck: see [Hackernoon coverage](https://hackernoon.com/andrew-ng-product-team-ratios-evolving-to-just-one-software-developer-for-every-two-product-manager). *(Note: replace with primary source if you can locate Ng's original talk or post.)*
[^2]: Cat Wu, ["How Anthropic's product team moves faster than anyone else," Lenny's Podcast](https://www.lennysnewsletter.com/p/how-anthropics-product-team-moves)
[^3]: Nikhyl Singhal, ["Why half of product managers are in trouble," Lenny's Podcast](https://www.lennysnewsletter.com/p/why-half-of-product-managers-are-in-trouble)
[^4]: Jenny Wen, ["The design process is dead. Here's what's replacing it," Lenny's Podcast](https://www.lennysnewsletter.com/p/the-design-process-is-dead)
[^5]: Aakash Gupta, ["There's a New PM Skill. It's Called Taste at Speed"](https://www.news.aakashg.com/p/taste-at-speed)
[^6]: Marty Cagan, ["AI Product Management 2 Years In"](https://www.svpg.com/ai-product-management-2-years-in/), Silicon Valley Product Group
[^7]: Ant Murphy, ["How Product is Changing in 2026"](https://antmurphy.medium.com/how-product-is-changing-in-2026-78a08f150aca)