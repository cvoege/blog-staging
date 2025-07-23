---
title: AI 10x Engineer Imposter Syndrome
description: You are Kenough.
date: 2025-07-22
tags: AI
---
{% raw %}

A few months ago I went through a bit of a mental slump. I've always been confident of my abilities as an engineer, but I couldn't help but feel like my skills were falling hopelessly behind as I scrolled places like LinkedIn and Twitter. If these sources were to be believed, engineering had moved on from my medieval practice of typing code into my editor. *Real* engineers were now 10-100x more productive than I was. This made me feel bad about myself, and I'm writing this article hoping to help others who are feeling similar anxieties.

I'm a skeptical person so I don't usually fall over myself immediately when I hear a claim like that. I usually roll my eyes in the same way I do when someone tells me a simple herbal remedy cures all disaese. But the sheer volume these 10x engineer claims are reaching right now started to hit a nerve. What if I'm *wrong*? What if all these people telling me that if I don't start using AI right now I'll miss the bus and be unemployable are right? After all, there were a lot of fancy words going around that distanced the "AI" these people were talking about with the "AI" I was familiar with.

These people weren't simply using ChatGPT, they were using *✨agentic✨* AI. They were using *✨thinking✨* models that used the internet, ran tests, and corrected their own mistakes. Sure I popped into ChatGPT here and there and asked it to write some code, then promptly discarded most of the output once I got the idea that I needed. But these engineers were letting Claude fully take the wheel and had agents ripping 5 PRs for them while they made morning coffee. Was I becoming a dinosaur, an old man yelling at cloud?

Part of what made me feel so anxious was that it was entirely possible AI changed without me knowing it because I didn't use AI very much. Because I didn't *like* using AI that much. Reviewing code is vastly less enjoyable process than writing it. Writing code involves thinking about lofty concepts and abstractions. Reviewing code involves trying to decide if it's worth it to ask the developer to make an abstraction and deal with the ensuing back and forth or just leave it. Had my stubborn desire to *enjoy coding* set me up for failure? Was I an AI skeptic not because the technology was riddled with problems but because it would be inconvenient for me if AI was everything everyone said it was?

## Diving In

Eventually I hit a breaking point and decided I simply had to dive in head first to AI coding. I downed Cursor, Roo Code, and Zed for their agentic coding promises. I started asking AI to write all sorts of code in all sorts of projects. I tried the different models and compared them. I even vibe coded a few things, not editing the code manually once.

And it was... Fine. Despite claims that AI today is 10x as good as AI 1 year ago (which was, apparently, 10x as good as AI was in 2023, which was 10x as good as it was in 2022, meaning today's AI is 1000x better than GPT 3.0), AI mostly seemed good at the same thing its always been good at and bad at the same things it's always been bad at. It's good at writing boilerplate, particularly in Javascript, and especially in React. It's not good at keeping up with the standards and utilities of your codebase and it's really bad at common but lower volume languages like Terraform. In particular AI's best use case was still writing one off scripts. Especially when you need to reach for tools you have no interest in learning for a single script, like when writing a one off ESLint rule for your specific needs.

Dark warnings that if I didn't start using AI now I'd be hopelessly behind quickly proved to be questionable. Using AI to code is not hard, so it's not hard to learn. There are a few things you need to learn but they come quickly. You learn how to split up tasks into smaller pieces so the AI doesn't lose its mind half way through the context window. And you learn to identify when the AI is too far off and it's not worth it to waste more time re-prompting. A competent engineer will figure this stuff out in less than a week of moderate AI usage. Further, if AI is about to get 2x, 10x, or 100x better at any minute (as everyone keeps saying it will), then learning how to use AI now doesn't matter because all these problems will just be solved.

Every time I encountered AI working "just okay", it strangely made me more anxious, not less. It meant I just couldn't figure it out, I couldn't find the spicy secret sauce that made everyone else so productive. I just didn't have what it takes: dinosaur, meet asteroid, thy name is AI. Eventually, a few things shook me out of this slump and helped realized that the whole AI super productivity craze was somewhere between hot air and outright scam. One of those was [this article](https://ludic.mataroa.blog/blog/contra-ptaceks-terrible-article-on-ai/) from Ludicity, directly countering the claims of the AI pumpers. I write this article to share more things that helped me get out of the AI 10x engineer imposter syndrome.

## The Math

Let's start by looking at the simple math of 10-100x productivity. 10x productivity means ten times the outcomes, not ten times the lines of code. This means what you used to ship in a quarter you now ship in a week and a half. These numbers should make even the truest AI believer pause. The amount of product ideation, story point negotiation, bugfixing, code review, waiting for deployments, testing, and QA in that go into what was traditionally 3 months of work is now getting done in 1.3 weeks. Each and every one of these bottlenecks has either also seen 10x productivity gains or is hiring 10x the people to do them.

Any software engineer who has worked on actual code in an actual company knows this isn't possible. You can't compress the back and forth of 3 months of code review into 1.5 weeks. When you code review you tag someone, hope they will get to it sooner rather than later (which will be tough because they are code reviewing 10 times as much code as before), context switch to something else while you wait, see the notification, context switch back to the review, read their comments, respond accordingly, rinse, and repeat. Yes this process can be made fairly efficient. But it can't be made efficient enough to support a sudden 10x increase in PR volume due to AI turning coders into supercoders.

The human processes involved in actual corporate software engineering have not changed significantly. Product managers might use ChatGPT to do "research" but they aren't suddenly pumping out ten times as many well vetted, well justified, well estimated stories as they did before. The same goes for Designers and QA testers. Hiring 10x the number of Product Managers to keep up isn't feasible. A human being can't keep up with that many PMs all writing stories. Each hire has diminishing returns as network effects and bureaucracy take hold. And we all know companies aren't hiring 10x the number of QA engineers and Product Managers. Companies are laying off QA and PMs in droves.

Even if we're charitable and assume people mean just writing code is now 10-100x faster, we should immediately be skeptical. Any engineer who has worked in an actual company knows that actual code writing is only so much of their job. All the human interactions with the product team, the design team, the QA team, waiting on pipelines, context switching between different tasks and different meetings significantly cut down on actual coding time. When we do code, what AIs produce is often broken, hallucinated, or sub par, and requires tedious review and retry procedure.

I think sometimes people lose the scale of just how big a 10x improvement is. 10x is the difference between your mini-van and a supersonic jet. Imagine trying to drive down your city streets in a car that goes 600mph. Will you get to the other side of town in one tenth the time? No, because even a single 60 second stoplight will eat up your entire time budget. You couldn't stay in control of even a 300mph vehicle on even the slightest curve on the highway.

100x productivity means you now do what used to be one year of work in two days. I shouldn't even need to touch the ludicrousness of numbers at that scale.


## So are the AI-posters lying or what?

I think the AI-posters are a mix of the following, in order of least to most malevolent:

* Good-natured folks who are mismeasuring themselves and others
* People heavily invested in the success of AI (AI startup founders, investors, etc.) seeking to direct AI hype towards them
* Bosses outright trying to scare their engineers with tales of junior engineer with Claude Code who could take their job at any moment, so they don't quit, look for other jobs, or ask for raises

Lets briefly look at these profiles, besides the one that describes me

### The good-natured engineer with bad math skills

In my experience, AI delivers rare, very short bursts of 10-100x productivity. When I have AI write me a custom ESLint rule in a few minutes, which would have taken hours of documentation surfing and tutorials, that's a genuine order of magnitude improvement in time. Moments like this do happen with AI. Many career non-coders have felt genuine magic in the first few days after spinning an app up with Lovable. They feel the 10x-∞x improvement in productivity vs not being able to do something at all.

The problem is the 10x productivity on that ESLint rule does not scale. I don't write more than one or two ESLint rules per year. This burst of productivity was enabled solely by the fact that I didn't care about this code and wasn't going to work to make it readable for the next engineer. If I started writing, maintaining 10 ESLint rules per month, I'd simply have to sink one-time cost to learn how ESLint internals work. After that, there simply wouldn't be a big difference in the time it takes to vibe code a new one vs. write it myself. And if I was writing that many rules I'd put in the extra time to carefully review and performance test each one so that it meets standards.

Eventually every vibe coder reaches the point where the returns start heavily diminishing. Their [site gets hacked](https://pivot-to-ai.com/2025/03/18/guys-im-under-attack-ai-vibe-coding-in-the-wild/) and they need to actually sink the time to learn how security works. The app gets too big for context windows and things start looking clumsy and loading slowly. Real frontend engineers who know what they are doing are hired to implement a consistent design system and fix performance.

There's also a lot of simple biases and blind spots that can cause a productivity illusion. If you leave the depths of big corporate to found a startup you will genuinely be shocked at how much more productive each engineer is than the ones at your old company. Believing AI to be the source of this productivity is an understandable mistake.

I think a lot of the more genuine 10x AI hype is coming from people are simply in the honeymoon phase or haven't sat down to actually consider what 10x improvement means mathematically. I wouldn't be surprised to learn AI helps engineers do many tasks 20-50% faster, but the nature of software bottlenecks mean this doesn't translate to a 20% productivity increase and certainly not a 10x increase.

### Incentives matter

Look, I'm not an AI startup hater. If you want to plug OpenAI's API into your healthcare startup I might raise an eyebrow of concern over the risks, but no more than I'd raise an eyebrow for any company claiming to disrupt the medical field. My goal here isn't to say AI startup founders are bad people. My point is to say in the droll voice of your high school Econ 101 professor, "Incentives Matter".

If you are running an AI startup and every other AI startup is telling investors they are seeing 10x more productivity than all the dinosaurs, the incentives are plain and simple. You should say the same publicly and privately. If your company is built on the back of AI, you are incentivized to sell AI as a miracle solution in every part of life, including your startups productivity. If you are an engineer at an AI startup and your boss asks you, "hey, you're getting 10x the productivity thanks to AI, just like all the other engineers, right?", you are strongly incentivized to say yes. And when every engineer says also says yes for the same reason, that CEO isn't lying, they legitimately believe it.

What I'd like to stress to those feeling anxiety like me is that this is nothing new. You shouldn't trust what any CEO says their company is doing. They are not unbiased sources. Executives have been claiming that everything from Agile to Meyers-Briggs have unlocked productivity that they have never seen before. Some of them are out of touch. Some of them are lying. Many are somewhere in the middle. There will always be a new buzzword on LinkedIn, don't let it get you down. In fact, stop scrolling LinkedIn at all. It's a silly place.

### Outright Malevolence

When something is said that makes people feel anxious, at least some of the time you should conclude it's because that's what the speaker wanted to happen. Bosses trying to make their engineers feel like their position is precarious is also nothing new. We all remember when a simple 3 month coding bootcamp could churn out a 4-year-degree quality engineer, so you'd best not get too uppity or you'll be replaced with a bachelor of arts doing a career pivot. Then a few years went by and people realized that bootcamp grads were usually [woefully underprepared](https://www.sandofsky.com/lambda-school/) for actual software engineering since they lacked the proper foundation.

I think that to some extent AI is the new coding bootcamp. A rhetorical device to enforce precarity. Your boss can't actually fire you and replace you with AI, but he can make you feel like he could. Some amount of the 10x AI engineer story is being told by people who simply want you to feel bad for this purpose. How much of it, I don't know. Despite how highly distrustful we've become of eachother in these times, I still believe most people are fundamentally decent. But if someone keeps repeating something over and over again that makes you feel precarious, anxious, and like an imposter, they might just be doing it on purpose. Don't let them.

## Degrees of separation

One thing I've noticed about all these characters in these AI coding hype pieces is there is always a degree of separation from the writer to the actual productivity benefits. The poster is a founder, or a manager, or an investor making grandiose claims about productivity. Who's productivity? Not them, some *other people*. You shouldn't take these claims with any more seriousness than your neighbor saying they knew a guy who worked at Area 51.

Presentations from actual engineers demonstrating how they achieve more productivity with AI are much more varied and much more muted in their praise. These demos show AI technology as you and I were familiar with before we got so anxious: a neat text generator that sometimes does magic but often requires you to take the wheel to get things right. AI usage on open source projects, where the process can be publicly witnessed, has famously been a [hilarious failure](https://old.reddit.com/r/ExperiencedDevs/comments/1krttqo/my_new_hobby_watching_ai_slowly_drive_microsoft/). I've learned things about how to use AI better from a few youtube videos. [Here's](https://www.youtube.com/watch?v=sQYXZCUvpIc) a good one referenced in that Ludicity article above. But I'll tell you right now, this engineer has not found the fountain of coding productivity.

## It's okay to be less productive

Even after I got over the idea that there was a secret clade of engineer who was now ten times as productive and strong and tall as I was, I still felt some anxiety over the fact that I still didn't enjoy using AI very much. Vibe coding is a complete bore once the magic wears off. Reading LLM generated code sucks. Asking it politely to use a not hallucinated library is painful. But what if I was 20% more productive vibe coding than regular coding? Would it be wrong for me to do "normal" coding if a higher output path is available?

It's okay to sacrifice some productivity to make work enjoyable. More than okay, it's *essential* in our field. Your brain works better when you're happy and have a healthy confidence in yourself. Only so much of coding is writing code, the rest is solving problems, doing system design, reasoning about abstractions, and interfacing with other humans. You are better at all those things when you feel good. It's okay to feel pride in your work and appreciate the craft. Over the long term your codebase will benefit from it.

It doesn't matter if digital music sounds objectively better than vinyl. It doesn't matter if flipping the record requires you to get up, when you could just let Spotify automatically roll over to the next song in 100x less time. If listening to a 70 year old disk makes you happier, just do it. You'll listen to more music if you do that than you would by forcing yourself to use the more "productive" Spotify.

## How to be a good AI CEO

Making all your engineers feel constantly anxious about their performance is *bad for your company*. This is a recipe for short term thinking that will encourage engineers to max out bad metrics, like lines of code. Code review will get neglected, tech debt will compound, and in the long term the whole company will be footing the bill of those errors.

Engineers need to have room to breathe. Room to take a little bit more time to do the thing right. Good codebases and good companies are built on a healthy balance of thinking for today and tomorrow. I'm thankful to work at one of these companies right now, but many aren't so fortunate.

Do not mandate AI thresholds on your engineers and scold those who do not use enough tokens. Your engineers are highly educated professionals in an extremely competitive field. Software engineering is already known for a often over-eager cycle of embracing and abandoning new languages and tools. If you are paying these people this much you should have the trust in them that if a super amazing productivity boost is available to them, they'll *come to you* asking for compute spend. Sign an enterprise Anthropic contract, host a training session, and see what comes out of it. That's all you need to do to make your engineers more productive with Ai.

## Conclusion

There is no secret herbal medicine that prevents all disease if you just did the research. There are no life-altering benefits to standing while you work instead of sitting if you just got off your ass. And there is no AI coding revolution you are missing out on. You are not missing anything. Trust yourself. You are enough.

Oh, and don't scroll LinkedIn. Or Twitter. Ever.

{% endraw %}
