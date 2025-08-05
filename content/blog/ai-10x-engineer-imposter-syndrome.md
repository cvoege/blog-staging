---
title: Curing Your AI 10x Engineer Imposter Syndrome
# title: Reality Checking the AI 10x Engineer
description: You are Kenough.
date: 2025-08-04
tags: AI
---
{% raw %}

A few months ago I went through a bit of a mental slump. I've always been confident of my abilities as an engineer, but I couldn't help but feel like my skills were falling hopelessly behind as I scrolled places like LinkedIn and Twitter. If these sources were to be believed, engineering had moved on from the medieval practice of typing code into an editor. *Real* engineers were now 10-100x more productive than I was. This made me feel bad about myself, and I'm writing this article hoping to help others who are feeling similar anxieties.

I'm a skeptical person so I don't usually fall over myself immediately when I hear a claim like that. I usually roll my eyes in the same way I do when someone tells me a simple herbal remedy cures all disease. But the sheer volume these 10x engineer claims are reaching right now started to hit a nerve. What if I'm *wrong*? Will I miss the bus and become unemployable if I don't learn to use AI right now? After all, there are a lot of fancy words going around that distance the "AI" these people are talking about with the "AI" I was familiar with.

These people were using *✨agentic✨* AI. They were using *✨thinking✨* models that surfed the internet, ran tests, and corrected their own mistakes. Sure I popped into a chat window here and there and asked it to write some code, then promptly discarded most of the output once I got the idea that I needed. But these engineers were letting Claude fully take the wheel and had agents ripping 5 PRs for them while they made morning coffee. Was I becoming a dinosaur, an old man yelling at cloud?

Part of what made me feel so anxious was that it was entirely possible AI changed without me knowing it because I didn't use AI very much. Because I didn't *like* using AI that much. Reviewing code is vastly less enjoyable process than writing it. Had my stubborn desire to *enjoy coding* set me up to be left behind?

## Diving In

Eventually I hit a breaking point and decided I simply had to dive in head first to AI coding. I tried Claude Code, Cursor, Roo Code, and Zed for their agentic coding promises. I started asking AI to write all sorts of code in all sorts of projects. I tried the different models and compared them. I even vibe coded a few things, not editing the code manually once.

And it was... Fine. Despite claims that AI today is improving at a fever pitch, it felt largely the same as before. It's good at writing boilerplate, especially in Javascript, and particularly in React. It's not good at keeping up with the standards and utilities of your codebase. It tends to struggle with languages like Terraform. It still hallucinates libraries leading to significant [security vulnerabilities](https://en.wikipedia.org/wiki/Slopsquatting).

AIs still struggle to absorb the context of a larger codebase, even with a great prompt and `CLAUDE.md` file. If you use a library that isn't StackOverflow's favorite it will butcher it even after an agentic lookup of documentation. Agents occasionally do something neat like fix the tests they broke. Often they just waste time and tokens, going back and forth with themselves not seeming to gain any deeper knowledge each time they fail. Thus, AI's best use case for me remains writing one-off scripts. Especially when I have no interest in learning deeper fundamentals for a single script, like when writing an ESLint rule.

Dark warnings that if I didn't start using AI now I'd be hopelessly behind proved unfounded. Using AI to code is not hard to learn. Obviously? Well, the AI coding community seems split on whether AI makes coding so easy a caveman can do it and that it requires an advanced, dedicated prompt engineer skillset. There are a few things you need to learn but they come quickly. You learn how to split up tasks into smaller pieces so the AI doesn't lose its mind late in the context window. Tools like Claude Code can do a bit of this themselves, even, though not always reliably. And you learn to identify when the AI is too far off and it's time to take the wheel.

A competent engineer will figure this stuff out in less than a week of moderate AI usage. Further, if AI is about to get 2x, 10x, or 100x better at any minute (as everyone keeps saying it will), then any lessons about how to use it now are moot for the future.

Every time I encountered AI working "just okay", it strangely made me more anxious, not less. It meant I couldn't find the spicy secret sauce that made everyone else so productive. I just didn't have what it takes: dinosaur, meet asteroid, thy name is AI. Eventually, a few things shook me out of this slump. One of those was [this article](https://ludic.mataroa.blog/blog/contra-ptaceks-terrible-article-on-ai/) from Ludicity, directly countering the claims of the AI pumpers. I write this article to share more things that helped me get out of the AI 10x engineer imposter syndrome.

## The Math

Let's start by looking at the simple math of 10-100x productivity. 10x productivity means ten times the outcomes, not ten times the lines of code. This means what you used to ship in a quarter you now ship in a week and a half. These numbers should make even the truest AI believer pause. The amount of product ideation, story point negotiation, bugfixing, code review, waiting for deployments, testing, and QA in that go into what was traditionally 3 months of work is now getting done in 7 work days? For that to happen each and every one of these bottlenecks has to also seen have 10x productivity gains.

Any software engineer who has worked on actual code in an actual company knows this isn't possible. You can't compress the back and forth of 3 months of code review into 1.5 weeks. When you code review you:

1. Tag your reviewer
2. Hope they will get to it sooner rather than later (which will be tough because they are apparently code reviewing 10x as much code as before)
3. Context switch to something else while you wait
4. See a notification (perhaps immediately, perhaps 2 hours after your reviewer went offline for the day)
5. Context switch back to the review
6. Read their comments
7. Respond accordingly
8. Rinse and repeat.

This process can be made fairly efficient at a competent company with good standards and communication practices. But you're telling me you made this process **10 times** as efficient to handle 10x the work? This simply can not be done.

The human processes involved in actual corporate software engineering have not changed significantly. Product managers might use ChatGPT to do "research" but they aren't suddenly pumping out ten times as many well vetted, well justified, well estimated stories as they did before. They can not do 10 user interviews all at once. The same goes for Designers and QA testers. Hiring 10x the number of PMs to keep up isn't feasible. Each hire has diminishing returns as network effects and bureaucracy take hold.

Even if we assume people mean only the actual code writing process is now 10-100x faster, we should still be skeptical of how this maths out. When you write code, how much of your time do you truly spend pushing buttons on the keyboard? It's probably less than you think. Much of your prime coding time is actually reading and thinking, often while waiting for compiling, a page refresh, or for tests to run. LLMs do not make `rustc` go faster.

What LLMs produce is often broken, hallucinated, or below codebase standards. The frequency of these errors go up with the size of the codebase. When that happens you have to re-prompt, which could instantly fix the problem or could be a huge waste of time. Or you can go in and fix the code yourself. But then you're back to measly 1x engineer status, perhaps worse if you've gotten so used to vibe coding you [forgot how to code](https://nmn.gl/blog/ai-and-learning). If you're "embracing the vibes" and not even looking at the code produced, you're simply going to hit a productivity wall once the codebase gets large enough. And once you do you'll have to reckon with the complete lack of standards and proper abstractions.

I think sometimes people lose the scale of just how big a 10x improvement is. 10x is the difference between your mini-van and a record setting [supersonic land jet](https://en.wikipedia.org/wiki/ThrustSSC). Imagine trying to drive your 10 minute commute down your city streets in a car that goes 600mph. Will you get to the other side of town in one tenth the time? No, because even a single 60 second stoplight will eat up your entire time budget. F1 cars slow down to mini-van speeds in basic turns. It turns out that most of any activity is not spent going at top speed.

100x productivity means you now do what used to be one year of work in two days. I shouldn't even need to touch the ludicrousness of numbers at that scale.

## So are the AI-posters lying or what?

I think the AI-posters are a mix of the following, in order of least to most malevolent:

* Good-natured folks who are mismeasuring themselves and others
* People heavily invested, personally or financially, in the success of AI (AI startup founders, investors, etc.)
* Bosses outright trying to make their engineers feel precarious so they don't quit, look for other jobs, or ask for raises

### The good-natured engineer with bad math skills

In my experience, AI delivers rare, short bursts of 10-100x productivity. When I have AI write me a custom ESLint rule in a few minutes, which would have taken hours of documentation surfing and tutorials otherwise, that's a genuine order of magnitude time and effort improvement. Moments like this do happen with AI. Many career non-coders have felt the magic in the first few days after spinning an app up with Lovable.

The problem is that burst of 10x productivity does not scale. I don't write more than one ESLint rule per year. This burst of productivity was enabled solely by the fact that I didn't care about this code and wasn't going to work to make it readable for the next engineer. If constantly writing ESLint rules became a core job requirement I'd sink the one-time cost to learn how ESLint internals work. After that, there simply wouldn't be a big difference in the time it takes to vibe code a rule vs. write it myself, especially when you add in the extra time to make my code human readable for when I come back to this file in 6 months.

Eventually every vibe coder reaches the point where the returns start heavily diminishing. Their [site gets hacked](https://pivot-to-ai.com/2025/03/18/guys-im-under-attack-ai-vibe-coding-in-the-wild/) and they need to actually sink the time to learn how security works. The app gets too big for context windows and things start looking and functioning inconsistently. Real frontend engineers who know what they are doing are hired to implement a consistent design system and UX.

There's also a lot of simple biases and blind spots that can cause a productivity illusion. If you leave the depths of big corporate for a startup you will genuinely be shocked at how much more productive each engineer is. It's easy to credit this to AI. Some people really enjoy the technological novelty of AI coding and when you are working in something new you often feel like you're doing more than you ever did. I know the first time I used Python I felt like I was "sipping rocket fuel", but, as with all other technologies, it always comes back down to earth.

I think a lot of the more genuine 10x AI hype is coming from people who are simply in the honeymoon phase or haven't sat down to actually consider what 10x improvement means mathematically. I wouldn't be surprised to learn AI helps many engineers do certain tasks 20-50% faster, but the nature of software bottlenecks mean this doesn't translate to a 20% productivity increase and certainly not a 10x increase.

### Incentives matter

Look, I'm not an AI startup hater. If you want to plug OpenAI's API into your healthcare startup I might raise an eyebrow of concern over the risks, but I'd do the same for any startup desiring to move fast and break things in the medical field. My goal here isn't to say AI startup founders or investors are evil or even dishonest. My point is to say in the droll voice of your high school Econ 101 professor, "Incentives Matter".

If you are running an AI startup and every other AI startup is telling investors they are seeing 10x more productivity thanks to AI, the incentives are plain and simple: you should say the same publicly and privately. If your company is built on the back of AI, you are incentivized to sell AI as a miracle solution in every part of life. If you are an engineer at an AI startup and your boss asks you:

> Hey, you're getting 10x the productivity thanks to AI, just like all the other engineers, right?

You are strongly incentivized to say yes. And when every other engineer also says yes for the same reason, that CEO [isn't lying](https://www.youtube.com/watch?v=vn_PSJsl0LQ), they are just relaying what they heard.

What I'd like to stress to those feeling anxiety like me is that this is nothing new. CEOs are not unbiased sources. Executives have been claiming that everything from Agile to Meyers-Briggs have unlocked limitless productivity. There will always be a new synergistic buzzword on LinkedIn, don't let it get you down. In fact, stop scrolling LinkedIn at all. It's a silly place.

### Outright Malice

When something is said that makes people feel anxious, at least some of the time you should conclude it's because that's what the speaker wanted to happen. Bosses trying to make their engineers feel like their position is precarious is also nothing new. We all remember the narrative that a 3 month coding bootcamp could churn out 4-year-degree quality engineers, so you'd best not get too uppity or you'll be replaced with a bachelor of arts doing a career pivot. Then a few years went by and people realized that bootcamp grads were usually [woefully underprepared](https://www.sandofsky.com/lambda-school/) for actual software engineering since they were not given the proper foundation.

Bootcamps and AI are just examples in a long series of poorly born out threats to commoditize the highly expensive, highly professionalized field of software engineering. They are rhetorical devices designed to imply precarity. Your boss can't actually fire you and replace you with AI, but he can make you *feel* like he *could*, and maybe not ask for that raise.

Some amount of the 10x AI engineer story is likely being told by people who simply want you to feel bad for this purpose. How much of it, I don't know. Despite how highly distrustful we've become of each other in these times, I still believe most people are fundamentally decent, so I'm not inclined to believe it's a high percentage.

## Degrees of separation

One thing I've noticed about all these characters in AI coding hype pieces is there is almost always a degree of separation from the writer to the actual productivity benefits. The poster is a founder, or a manager, or an investor, making grandiose claims about someone else's productivity. There's nothing wrong with secondary sources but if you can't find a primary source, you might start questioning the reliability of the information.

Presentations from actual engineers demonstrating how they achieve more productivity with AI are much more varied and much more muted in their praise. These demos show largely AI as the same technology you and I were familiar with before we got so anxious: a neat text generator that sometimes does magic but often requires you to take the wheel.

AI usage on open source projects, where the productive process can be publicly witnessed, has famously been a [hilarious failure](https://old.reddit.com/r/ExperiencedDevs/comments/1krttqo/my_new_hobby_watching_ai_slowly_drive_microsoft/). I have learned things about how to use AI better from a few youtube videos. [Here's](https://www.youtube.com/watch?v=sQYXZCUvpIc) a good one referenced in that Ludicity article above. I'll spoil it for you though, this engineer has not found the fountain of coding productivity.

## It's okay to be less productive

Even after I got over the idea that there was a secret clade of engineer who was now ten times as productive and strong and tall and sexy as I was, I still felt some anxiety over the fact that I still didn't enjoy using AI very much. Vibe coding is a complete bore once the magic wears off. Reading LLM generated code sucks. Asking it politely to use a not hallucinated library is painful. But what if I was, despite all that, 20% more productive vibe coding than regular coding? Would it be wrong for me to do "normal" coding if a higher output path is available?

No. It's okay to sacrifice some productivity to make work enjoyable. More than okay, it's *essential* in our field. If you force yourself to work in a way you hate, you're just going to burn out. Only so much of coding is writing code, the rest is solving problems, doing system design, reasoning about abstractions, and interfacing with other humans. You are better at all those things when you feel good. It's okay to feel pride in your work and appreciate the craft. Over the long term your codebase will benefit from it.

It doesn't matter if digital music sounds objectively better than vinyl. It doesn't matter if flipping the record is less "productive" than letting the streaming service automatically roll over to the next song in 100x less time. If listening to a 70 year old disk makes you happier, just do it. You'll listen to more music if you do that than you would by forcing yourself to use the more "productive" streaming service. You will spend more time writing code and you'll write better code if you do it the way you like to.

Oh, and this exact argument works in reverse. If you feel good doing AI coding, just do it. If you feel so excited that you code more than ever before, that's awesome. I want everyone to feel that way, regardless of how they get there.

## How to be a good AI leader

Making all your engineers feel constantly anxious about their performance is *bad for your company*. It will make your engineers not want to work for you. This is a recipe for short term thinking that will encourage engineers to max out bad metrics, like lines of code. Code review will get neglected, tech debt will compound, and in the long term the whole company will be footing the bill of those errors.

Unrealistic 10x expectations will result in rushed and thus subpar work without fail. Engineers need to have room to breathe. Room to take a little bit more time to do the thing right. Good codebases and good companies are built on a healthy balance of thinking for today and tomorrow. I'm thankful to work at one of these companies right now, but many aren't so fortunate.

Do not scold engineers for not using enough tokens. Your engineers are highly educated professionals in an extremely competitive field. Software engineers are already infamous for an over-eager cycle of embracing and abandoning new languages and tools. If you are paying these people this much, you should have the trust in them that if a super amazing productivity boost becomes available, they'll *come to you* asking for the pro plan. If you're worried about missing out on all the AI coding gains everyone else seems to be getting, sign up for a LLM team plan, host a training session, and see what comes out of it. That's all you need to do.

## Conclusion

There is no secret herbal medicine that prevents all disease sitting out in the open if you just follow the right Facebook groups. There is no AI coding revolution available if you just start vibing. You are not missing anything. Trust yourself. You are enough.

Oh, and don't scroll LinkedIn. Or Twitter. Ever.

{% endraw %}
