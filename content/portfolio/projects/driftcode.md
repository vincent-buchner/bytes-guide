+++
date = '2025-04-10T15:15:44-05:00'
draft = true
title = 'Driftcode: A TUI Tool for Leetcode Written In Go'
description = ''
[params]
    image = '/images/driftcode.png'
    author = 'Vincent Buchner'
    updated_at = '2025-04-10T15:12:17-05:00'
+++

I'm going to be honest with you: I don't really like Leetcode problems. That might not surprise you, it's not exactly a groundbreaking opinion. In fact, I'd wager that there are more people than not who are not too fond of them either. There's certainly a nice "aha!" moment when you finally solve a problem. But the process? The painful process of trying to work out the question, struggling with edge cases, and wondering about arbitrary time complexity requirements? No thank you.

But what most infuriates me about Leetcode is the way you're meant to practice. Their online editor, while it does work, is not particularly nice unless you're prepared to pay. A lot of basic development tools like debugging functionality, decent syntax coloring, or integration with your text editor of choice come with a cost. And that's always annoyed me. If I'm going to wrestle through these problems, I at least want to do so in a place I'm familiar with.

That's what drove me to build Driftcode.

<br>

## What is Driftcode?
Driftcode is a Terminal User Interface (TUI) tool which allows you to pull Leetcode problems onto your local machine. It's almost as though you're avoiding the Leetcode website altogether and instead building problem files locally—files which you can then edit in your environment, with your tools, and build or run as you see fit. You get your editor of choice: Neovim, VSCode, or even Emacs if that's your thing.

In a sense, Driftcode is my passive-aggressive protest against the way technical interview preparation has been handled. Rather than sitting there and churning out problems in the browser, I thought to myself, I'd rather code something that made the experience worth it. And in that process, ironically enough, I learned more than had I continued to stick with Leetcode practice.

<br>

## Why I Picked Golang
One of this project's largest successes was the fact that I built it using Go (Golang). I had tried playing around with Go before, but never had I committed to fully building something concrete with it.

Go was a great choice. Its libraries are strong out of the box, and the language is so simple to use that it's perfect for building fast, efficient CLIs. I didn't have to wrestle layers of abstraction or setup; I could just dive in. It was productive. Fun, even.

And let’s not ignore the fact that compiling a statically typed, single-binary CLI tool that “just works” across machines is deeply satisfying. I’d honestly love to build more tools in Go going forward.

<br>

## How Driftcode Works
Driftcode depends upon <u>[Alfa Arghya's REST API](https://github.com/alfaarghya/alfa-leetcode-api)</u> in order to acquire problem data to download. That API provides metadata about Leetcode questions: the question title, the difficulty level, the prompt, tags, and so on. Everything you'd otherwise scroll to see on the site. With that information once I have it, Driftcode makes it pretty and deploys it in your local workspace.

To get the tool to be more responsive and allow for fast lookup/filtering, I have also incorporated an SQLite database. That allows you to filter questions by difficulty, tags, or title, and build a local working file automatically without having to make a call to the API every time. It's efficient, quick, and doesn't require internet access once the questions are cached.

I kept the database schema relatively easy, mostly because I didn't want to over-engineer. I only needed to store and index a few fields, and SQLite was the perfect lightweight solution. No extra servers, no messy setup.

<br>

## What I Learned (and What's Next)
This project was very educational. Not only in Golang and calling external APIs, but also in packaging, dependency management, and making tools that actually make my life easier.

It also demonstrated to me that making something useful doesn't necessarily mean making something complicated. Driftcode is relatively simple, yet it gets rid of a real nuisance I had. That alone was worth doing.

I'm not actively engaged on it right now. Like many side projects, it did what it needed to do and has been sitting quietly in my repositories ever since. That being said, I do think there's room for optimization.

If I were to return to work on it, I'd like to:

<br>

- • Introduce a config system whereby users can specify default languages, editors, and output folders.

- • Improve the cache and sync logic with the API.

- • Add code submission and result retrieval (more difficult, since Leetcode does not have a public submission endpoint).

<br>

## Final Thoughts
Leetcode may not be fun. But making tools to avoid it? That's another thing. Driftcode enabled me to regain some control over a process that was maddening and rigid. And in doing that, I picked up more than I thought I would—I enjoyed learning it.

<br>

<u>[Github](https://github.com/vincent-buchner/driftcode)</u>