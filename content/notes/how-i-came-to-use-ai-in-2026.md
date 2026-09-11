---
title: "How I came to use AI in 2026"
date: 2026-09-12
description: "How my approach to building software with AI has changed over the past year"
---

This time last year (2025), I was still writing all my code by hand. I was very sceptical of AI. I didn't believe it was capable of writing good code.

Today (September 2026), I use a $100 ChatGPT Pro subscription for all my personal projects, and I have a [Hermes][hermes] agent as a personal assistant running on a Mac mini in my living room.

## Giving AI a chance

How did I get here? It started around November or December last year when I asked my friend [Martin][martin] how he was using AI. He told me he was using the [opencode][opencode] CLI, so I gave it a try using, I think, _grok code fast_ at the time because it was free and pretty good.

[hermes]: https://hermes-agent.nousresearch.com
[martin]: https://x.com/martinrue
[opencode]: https://opencode.ai

I tinkered on side projects over the Christmas break, making use of opencode. Then _grok code fast_ stopped being free. Martin told me he was now using the OpenAI Codex desktop app. So I signed up for a $20 Codex subscription to see how it was.

I wondered how much usage I would get out of the $20 plan. I expected to hit the limits pretty quickly. I was in the middle of building [swm][swm], which is my "window manager" for macOS. I originally made [Stark][stark], but wanted to move to a cleaner implementation, like Yabai.

It wasn't until I used GPT 5 point something to help get the initial version of swm finished and tweak features in [skbd][skbd] that AI **clicked** for me. It wasn't that it was writing tons of code for me, or that AI was going to replace my job. It was letting me move quickly on projects or ideas that I would probably have kept putting off.

Once I got deep into finishing the first version of swm and debugging issues, I quickly hit the $20 plan's five-hour usage limits. That's what prompted me to upgrade to the $100 plan.

[swm]: https://github.com/starkwm/swm
[stark]: https://github.com/starkwm/stark
[skbd]: https://github.com/starkwm/skbd

## Building things I’d kept putting off

{{< figure src="/images/notes/how-i-came-to-use-ai-in-2026/chatgpt.webp" alt="My ChatGPT Pro profile showing usage statistics and daily token activity." caption="My ChatGPT usage as of September 2026." >}}

Since then I've used it to help build a companion iPad/iPhone app for the solo RPG [Four Against Darkness][4ad], with party management, dungeon mapping, dice rolling, and session notes.

More recently I was getting slightly irrationally annoyed at how much memory Spotlight was using, and I wasn't a big fan of Raycast for the same reasons. I ended up building an opinionated app launcher for myself, which resulted in [Conjuror][conjuror]. This was an experiment in building something with prompts and barely looking at the code, including using AI to debug problems and tweak the UI.

[4ad]: https://boardgamegeek.com/boardgame/197097/four-against-darkness
[conjuror]: https://conjuror.app

## My day-to-day setup

I use the Claude app for work and the ChatGPT app for personal projects. I also use the `codex` and `pi` CLIs. I love `pi` for the same reason I love using `neovim`. It's minimal, and you add on top only the things you need.

When I want to build a feature for a side project, I ask my agent to investigate whether it's feasible and suggest how best to implement it. If the plan looks overcomplicated, I work with the agent to simplify it before starting implementation. Once it's built, I manually test it to see if it works as expected, then go back and forth with the agent to fix bugs and tweak the behaviour. Once I'm happy with how it works, I review the code to make sure it's maintainable and follows the language's conventions.

{{< figure src="/images/notes/how-i-came-to-use-ai-in-2026/pi.webp" alt="Minimal Pi agent setup" caption="My minimal Pi agent setup." >}}

When needing a CLI agent, I typically switch between `codex` and `pi` depending on how much work I plan to do, or if I want to make use of some of the ChatGPT plugins I have installed. For my personal projects, I mostly use the ChatGPT app to manage multiple sessions at once. With these tools, I can keep my side projects moving and try out ideas for apps or websites without committing a ton of time to them.

I did give prompt dictation a try, and use it on and off. I currently use the [Handy][handy] app, and I like it because of how minimal it is, while also letting me pick a small speech recognition model over the 700MB+ ones.

[handy]: https://handy.computer

Another big change in my typical workflow is using [herdr][herdr] instead of `tmux`. I also ported my [tm][tm] project, which is a `tmux` session manager, into a new [tendr][tendr] project for `herdr`. Aptly named "tendr", because you "tend to your herd" 🤦🏻‍♂️. I made these projects because I have work projects that need a number of processes spun up to develop and test them.

[herdr]: https://herdr.dev
[tm]: https://github.com/tombell/tm
[tendr]: https://github.com/tombell/tendr

## Building with a personal assistant

{{< figure src="/images/notes/how-i-came-to-use-ai-in-2026/hermes.webp" alt="Hermes in Discord giving a morning weather report" caption="My Hermes agent giving me a morning weather report." >}}

Somewhere during the spring or early summer, I ended up setting up Hermes as my personal assistant in a private Discord server. I was in the same boat as most other people wondering, "What would I even use it for?" All I knew was I had it hooked up to an opencode go subscription using Deepseek V4 Flash, because I didn't know how many tokens it would even consume.

It was the weekend of the Monaco F1 Grand Prix. I asked my Hermes agent to look into whether we could build a live timing dashboard. It went off and figured out how it could build such a thing. It found the OpenF1 project, which is an API that offers live timings and historical data, but you had to pay €9/mo for it. I didn't really fancy paying that much a month for the project. Hermes said we could host the OpenF1 server ourselves locally because it was an open-source project.

The experience of "live debugging" the dashboard during the race weekend sessions, from free practice to qualifying to the actual race, was fun. Small issues kept cropping up, and I kept prompting Hermes to figure out a fix for them, and then refreshing the dashboard in the browser to see the improvements.

The small details that got implemented during sessions:

- Properly showing drivers who had retired from sessions
- Animating overtakes in the live list of drivers
- Showing and playing radio broadcasts from the different drivers and engineers
- Displaying live maps using location data of the cars

Just having that "oh, can it show this?" idea, and asking Hermes to build it was addictive. It even ended up building a historical race weekend viewer for past races and years.

## Saving time beyond coding

While building these things with Hermes was fun, I now use it mostly as a personal assistant to save me time.

Daily reports I get from Hermes include:

- Top 5 Hacker News and Lobsters posts it thinks I will find interesting
- A weather report for the day ahead in Manchester

One of the bigger time savers has been getting Hermes to help automate digging for new music on Beatport for DJing. It hasn't replaced listening to tracks and deciding which ones to purchase, but it gathers the last seven days’ new releases in the genres I like most, then sorts them into four different playlists on Beatport. The tracks are scored based on tracks I have previously purchased, using factors like artist, label, and genre.

- **Must Buy** - tracks scoring very high
- **Check Out** - tracks with average scores
- **Probably Not** - tracks that scored low
- **Other New Releases** - tracks that didn't score

That gives me focused lists and helps me decide where to spend my time evaluating tracks I might play when DJing. Hermes is hooked up to use GPT 5.6 Luna right now, which means it uses very few tokens, so I barely notice it using any of my weekly limits.

I've also had it create a skill for looking up trains between any two UK stations at a given time. This saves me time not having to use annoying web pages checking or unchecking silly options. I also built an iOS app to export my Health app data to a web backend that Hermes can query and monitor.

## For now, at least

The tools will probably change again in four to six months. What's changed for me is that I'm actually building things I used to keep putting off.
