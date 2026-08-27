# AI Engineering Has Changed: The 5 Concepts You Need in 2026

[Watch on YouTube](https://www.youtube.com/watch?v=CoIxe4aGCpg) · 2026-08-28

![The 5 shifts in AI engineering, and how each layer evolved from the previous one](images/five-shifts-ai-engineering.png)

<!-- cheat sheet -->

## In this video

- **Shift 1, prompt engineering**: how to talk to the model, why it became a field, and why the model companies trained the need for it away
- **Shift 2, context engineering**: limited context windows, stateless models, context rot, and the retrieval and memory work that came out of it
- **Shift 3, harness engineering**: the operating system around the model, so file systems, sandboxes, logging, access control, and subagents
- **Shift 4, loop engineering**: the 5 parts of a loop, and a price monitor you can run today with one instruction
- **Shift 5, graph engineering**: parallel branches, merge points, and a separate critic, shown through an article writing pipeline
- **How they connect**: which shifts solved a new problem, which are optimisations inside a layer that already exists, and how to place the next term that shows up

## Resources

### Go deeper on each shift

- Prompt engineering: [Anthropic's prompt engineering overview](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview)
- Context engineering: [Effective context engineering for AI agents](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents) and [Context Rot](https://research.trychroma.com/context-rot)
- Harness engineering: [The importance of agent harness in 2026](https://www.philschmid.de/agent-harness-2026) and [Harness engineering for coding agent users](https://martinfowler.com/articles/harness-engineering.html)
- Loop engineering: [Loop Engineering](https://addyosmani.com/blog/loop-engineering/) and [Own the Outer Loop](https://addyosmani.com/blog/own-the-outer-loop/)
- Graph engineering: [Coordination as an architectural layer for LLM-based multi-agent systems](https://arxiv.org/pdf/2605.03310)

### The prompts from the video

- The price monitor loop and the article writing graph are both in the transcript below, in full, ready to copy.

### LevelUp Labs

- [The AI Builder's Handbook](https://maven.com/aishwarya-kiriti/o/d4b008), free
- [LevelUp Labs](https://levelup-labs.ai/)
- [The Nuanced Perspective (newsletter)](https://thenuancedperspective.substack.com)
- [LevelUp Labs education](https://levelup-labs.ai/education)
- [Awesome Generative AI Guide](https://github.com/aishwaryanr/awesome-generative-ai-guide)
- [My courses on Maven](https://maven.com/aishwarya-kiriti)

## Sources

- Bloomberg, *"AI 'Prompt Engineer' Jobs Pay Up to $335,000"*, 29 March 2023, for the salaries and the hiring wave around prompting. [bloomberg.com](https://www.bloomberg.com/news/articles/2023-03-29/ai-chatgpt-related-prompt-engineer-jobs-pay-up-to-335-000)
- Reuters, *"ChatGPT sets record for fastest-growing user base"*, 2 February 2023, for how fast people met one after the November 2022 launch: an estimated 100 million monthly users within about 2 months. [reuters.com](https://www.reuters.com/technology/chatgpt-sets-record-fastest-growing-user-base-analyst-note-2023-02-01/)
- Wei et al., *"Chain-of-Thought Prompting Elicits Reasoning in Large Language Models"*, 2022. [arxiv.org](https://arxiv.org/abs/2201.11903)
- Wang et al., *"Self-Consistency Improves Chain of Thought Reasoning in Language Models"*, 2022. [arxiv.org](https://arxiv.org/abs/2203.11171)
- Brown et al., *"Language Models are Few-Shot Learners"*, 2020, for few-shot prompting. [arxiv.org](https://arxiv.org/abs/2005.14165)
- Chroma, *"Context Rot: How Increasing Input Tokens Impacts LLM Performance"*, July 2025, for the finding that models do not use their context uniformly and get less reliable as input grows. [research.trychroma.com](https://research.trychroma.com/context-rot)
- Anthropic, *"Harness design for long-running application development"*, for the same-model comparison: one prompt, Opus 4.5 both times, bare against a planner, generator, and evaluator harness. Bare produced a prototype whose core features did not work. The harnessed run produced a working application. [anthropic.com](https://www.anthropic.com/engineering/harness-design-long-running-apps)
- Peter Steinberger, 18 July 2026, the post that put the term graph engineering into circulation: *"Are we still talking loops or did we shift to graphs yet?"* [x.com](https://x.com/steipete/status/2078277297791189132)

## Transcript

The most important skill for AI engineering has shifted about 5 times just in the past few years. All the way from prompt engineering back in 2023, to graph engineering, which was just coined a few months ago.

And if you're a beginner in this space, and you've been wondering what all of these terms are, and why everything keeps changing so quickly, then this is the only video you need to understand all of these concepts, and also in the most non-overwhelming way possible.

Now I think the problem with most content out there is that they make it seem like all of these are unrelated concepts, right? But in reality they're all connected to each other, and each one was literally born from the previous one.

So in this video we'll break down what each of these terms means, why they matter, and we'll also look at real examples for each of the concepts. But the most important bit of this video is that we'll connect them all together, so the next time you see a new term show up you know exactly where it fits, instead of feeling like you'll have to learn everything from scratch, right.

And if you're new here, I am Aishwarya Reganti. I have been an AI researcher for more than a decade now, and I have patents and publications in some of the top AI conferences. Until last year I was an AI scientist and tech lead at AWS, and I was building production systems for large enterprises. And now I run my own startup, LevelUp Labs, and we help companies and teams go AI native.

So let's get started.

### Shift 1, prompt engineering

Shift one is the prompt engineering shift, and it dates pretty much back to the ChatGPT moment, when ChatGPT released in November of 2022.

And what people found was that this was suddenly a very smart chatbot. You could ask it something in plain English, the way you would ask a colleague, and it would come back with something genuinely useful. Write me a job description for this role. Explain this contract clause. Summarise these 4 pages. No setup, no integration, nothing to configure. And a few hundred million people met one within about 2 months.

So people started using this, and they started noticing patterns. Which is that how good an answer you get really depends on how well you communicate with these models.

For instance, if you asked a maths question, or a logical reasoning question, you had to tell the model explicitly that it should answer step by step, and not rush straight to the answer. If you wanted a specific format, for instance a meeting summary laid out a particular way, giving it 2 or 3 examples got you a much better result than describing what you wanted.

So people started finding a bunch of these tricks for communicating with models, and it turned into a field of its own, called prompt engineering. Through 2023 and 2024 there were so many research papers on this, all essentially asking how you best communicate with these models. Some of the popular ones you've probably heard of are chain of thought, few-shot prompting, and self-consistency.

Prompt engineering was also called the hottest job of the year. The salaries were in the news, and people were actually buying and selling prompts in marketplaces.

And when this kept happening, the companies building these models, so OpenAI, Anthropic, Google, all of them, started to think that they should be doing something about it.

Because the whole promise of an AI model is that you can talk to it in human language. But if you have to learn all of these tricks first, if you have to learn prompt engineering before you can use one, then that promise is gone, right? You've rebuilt the exact wall you were trying to remove, and now there's a special language sitting in between people and models.

So they said, why do we not train our models better, so they can recognise the situation themselves. And that's what happened. If you ask a good model to solve something today, it works out its own route. For instance, if it's a maths question, it decides on its own to go step by step. If it's a question about something current, it realises it needs to go and do a web search.

Which made the whole field matter a little less, because now you don't have to become a prompt engineer. You can just talk in natural language, and the models are smart enough to understand you.

And that's when we moved on to the next problem.

Before we get to the next shift, I want you to hold this whole thing in terms of an analogy of a car. 2022 can almost be thought of as the invention of the engine. A very powerful one, with nothing attached to it. And everything that happens after this is the stuff people started bolting on, to get from an engine to a car, and eventually to the kind of cars we have today.

### Shift 2, context engineering

Which brings us to the next shift, which is context engineering.

Now it's early 2024, and a lot of companies had started using these models, because they were good at communicating in the way humans communicate, and they had also got much smarter. But then they realised that to make these models work inside a company, for real use cases, in production, one very important thing was missing. Which is context.

Because these models are trained on general information. They don't know your customers, your company, your knowledge bases, your internal processes, your policies, your pricing.

And this was also the time when agents became really popular. Which are systems that don't just answer, they go and do work. For instance, an agent that reads a support ticket, looks up the customer's order, and drafts a reply. Or one that takes a client brief, pulls your rate card, and puts a quote together. Or one that goes through last week's applications and flags the ones missing documents.

So the whole idea of AI engineering became, can you take an AI model, give it access to your ecosystem, and get it to do work end to end.

And doing that well was hard, because of 3 things.

One, the context window is limited. There's only so much you can give it at a time, so you have to make sure only the right information goes in.

Two, these models are stateless. As soon as a session ends, they forget. So you have to make sure that information is stored somewhere it can be retrieved again.

And three, there's this thing called context rot. Which is that if you give noisy information to an AI system, it tends to mess up quite badly and lose track of what's happening, even when the good information is sitting right there inside the window.

So you had to give it clean context, and the field became all about context engineering. That was the skill in 2024 and 2025, and a lot of new things came out of it. More advanced ways of doing retrieval augmented generation. Agentic memory. Methods for chunking and embeddings. And building evals on top of all of it, so you could actually tell whether it was working.

So if you think of it back in the car analogy, 2024 and 2025 was the time when the engine was given wheels, a transmission, and a frame to hold it together. And now you have a functional car. Something that moves forward and gets work done. It's still a basic and early one, right? But it goes somewhere, which an engine on its own never did.

### Shift 3, harness engineering

Then comes the next shift, which is harness engineering, and this happens a bit into late 2025.

Because by then companies already had context engineered AI systems doing a lot of work, and agents that could handle things end to end. And they started trying to build systems that were more complicated, which needed far more than just providing context.

For instance, if you're doing multi-step work, your agent needs somewhere to write things down as it goes, so it doesn't lose its place halfway through. So people gave it a file system.

Sometimes, to actually finish a task, code has to be executed. For instance, you ask it to reconcile 2 spreadsheets, and the only sensible way to do that is to write a small script and run it, rather than reasoning through 4,000 rows in its head. So it needs somewhere safe to run that, which is a sandbox.

And to work out why it made the decisions it made, you need logging and observability, so you can go back and look.

And to make sure it only touches what it's allowed to touch, and doesn't email a client something nobody has read, you need access control and boundaries.

There's one more, and this one matters at the end of the video, so hold onto it. When a job is too big for a single agent, it spawns smaller subagents to work on pieces in parallel. Each one gets its own clean context, does its bit, and hands back a short summary. So the main agent isn't drowning in everything all of them read.

And people started realising that to build complicated AI systems, it's not just the context. It's everything around it. They had almost ended up building an operating system around the AI model.

So everything apart from the model, the whole operating system you build around it, is called as the harness. And building that well is called as harness engineering.

Which means an agent is the model plus the harness. And notice what that does to the last shift, because the harness includes the context, plus the operating system, plus all the boundaries you put around it. Context engineering didn't go away. It got absorbed into this.

And this is the shift I would spend your time on, because the evidence on it is quite striking. Anthropic ran the same model, with the same prompt, in 2 conditions. Bare, it failed the task. With a harness around it, it finished. Same weights, same words, opposite outcome.

So back in the car analogy, harness engineering is almost like building good quality steering, and a dashboard so you can see your speed, and introducing seat belts, crumple zones, mirrors, lights. All the things you build around the car so it's not just moving, it's moving safely and you can actually rely on it.

And notice how those arrived on real cars. Nobody designed seat belts and crumple zones up front. Each one was added after something kept happening without it. Your harness grows the same way, one failure at a time.

### Shift 4, loop engineering

And that's when the 2 latest shifts come into picture, which are loop engineering and graph engineering.

Because once you're operating inside the harness, once the operating system is already there, people started inventing newer and more optimised ways of working within it. And the first of those is loop engineering.

Now the whole idea of loop engineering is simple. Up to this point you're still the one starting everything. You decide when it runs, you look at what came back, and you decide what happens next. That job you're doing is the loop. And loop engineering is setting up something that does it instead of you.

And people make this sound far more complex than it is. A loop is 5 things.

A trigger, which is whatever starts it. A schedule, or an event, for instance a file landing in a folder.

A goal it can check by itself, so it knows when it's actually finished.

A checker that's separate from the thing doing the work, because anything grading its own output is far too generous with itself.

Somewhere to keep notes between runs, because it forgets otherwise.

And a stop condition with a limit, so that when it can't finish, it stops instead of running all night.

Here's one you can run right now, and it needs nothing set up. Say there's a pair of sneakers you've had your eye on for months. They're sitting at 250 dollars on Amazon, and you're not paying 250. You want to know the second they go under 200. All you need is the product link. Here's the exact prompt.

> /loop 1h
>
> Check this Amazon page: [paste the link]. Find the current price of the sneakers. Append it to a file called price_log.md with the date and time, so I build up a history.
>
> If the price is 200 dollars or less, message me straight away with the price and the link, and stop looping. If it's still above 200, just log it and don't say anything else.
>
> And if the page changes and you can't find a price at all, tell me that and stop, rather than guessing.

And that's a loop. All 5 pieces are sitting in that one instruction.

Every hour is the trigger. Are the sneakers 200 or less is the goal, and notice that's a number, so it's something a machine can settle rather than an opinion. Comparing that number to your 200 is the check, so it isn't the agent deciding whether this feels like a good deal. Price log dot md is the memory between runs, and it creates that itself, so there's nothing for you to prepare, and you end up with the price history, which tells you whether they've been drifting down or holding. And it stops the moment it messages you, so you're not still getting pinged about sneakers you already bought.

That last line matters too, the one about not guessing. Amazon changes their page layout all the time, and the day it does, your loop can't find the price any more. Without that line it just keeps running and quietly tells you nothing. That's your stop condition covering the case where it fails, which is the bit people forget.

And the same shape works for anything you'd otherwise keep checking by hand. A competitor's pricing page, so you know the day they change it. A flight. A job board. Swap the link and swap the number.

Engineers use the exact same shape to watch a deploy. Check if it finished, run the smoke tests, stop when they pass, keep checking every 5 minutes if they don't.

And if you go back to the car analogy, this is almost like introducing self-driving. The operating system is already there, and all the parts are already there. So the question becomes, can we add a bit more on top so this thing drives itself?

### Shift 5, graph engineering

And then the final shift is graph engineering.

Now remember the subagents from the harness. Once you have a lot of those running, and a lot of loops firing, they start getting in each other's way. Two of them doing the same job. One sitting there waiting on another that hasn't finished. Something found in one place that never reaches the place that needed it.

So graph engineering is you setting up the structure at a higher level, so multiple agents coordinate with each other and follow the steps of a larger pipeline. Which agents exist. What each one is responsible for. What has to finish before something else can start. Where work splits to run at the same time. And where a person signs off.

And the reason it's called a graph is that once you draw it, that's literally what it is. Boxes, which are the agents doing a piece of work. And arrows, which are what has to happen before what.

Let me make it concrete with an article writing system, because it's easy to picture.

You start with a brief. That fans out to 3 researchers running at the same time. One going through sources. One pulling the data. One collecting examples. All 3 come back into an outline node, which merges what they found. That goes to a drafter, which writes the thing. And then it goes to a critic, which is a separate agent whose only job is to judge the draft against your bar. If it passes, you're done. If it doesn't, it goes back to the drafter with notes, and round it goes again.

And notice 2 things in that shape. The researchers run in parallel, which is the bit a loop can't do, because a loop is one thing after another. And the critic is a different agent from the drafter, which is that same maker and checker rule from the loop, drawn out where you can see it.

Here's the exact prompt for that one.

> Write me an article on this topic. Do it in stages, and use separate subagents so they each start clean.
>
> First, run 3 researchers in parallel. One finds the primary sources and pulls the key claims. One finds the numbers, and notes where each number came from. One collects real examples I can actually use.
>
> When all 3 come back, merge what they found into a single outline, and flag anything the 3 of them disagree on.
>
> Then draft the article from that outline.
>
> Then hand the draft to a separate critic subagent that has not seen any of the drafting. Its job is to check the draft against 3 things. Every claim is supported by one of the sources. Every number has its source attached. And the piece actually answers the brief.
>
> If it fails any of those, send it back to the drafter with the critic's notes and try again. Do that at most twice, then give me the draft and the critic's final read.

And that's the whole graph, described in one instruction. The 3 researchers are your parallel branch. The outline is where they merge. The critic is a separate node with its own clean context. Send it back to the drafter is the edge that loops. And at most twice is your cap, so it can't sit there arguing with itself all afternoon.

And in the context of cars, this is like setting up a road system. Lanes, traffic lights, right of way. None of it makes any single car better. It's there so that multiple cars can operate around each other without colliding.

### How it all connects

So that's how these concepts come together. And if you look at it, each of them came from people building more and more complicated systems, and then working out tips and tricks to improve them.

Something else will probably come up next month. And what you want to think about as an AI builder is 2 things. What problem did this come from? And what does it control that the last one did not? Which really comes down to asking whether it's an optimisation, or whether it's solving a genuinely new problem.

If it solved a new problem, it's a new layer. If it's a better way of working inside something that already exists, it's an optimisation, and you can pick it up when you need it.

And it's not super hard to build loops or graphs. You can actually work with your agents to build them, as long as you have the high level structure in your head, which is what this video was for.

One thing I would do this week. Take one agent you already use, and work out which of those harness pieces it's missing. Most people find the same one. There's nothing checking the work except them.

If you want to go deeper on the harness, the handbook and the course are linked below. See you in the next one.
