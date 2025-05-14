+++
date = '2025-04-25T18:13:40-05:00'
draft = true
title = 'Can Zed Replace Your Code Editor?'
description = "Zed is the next-gen text editor built in Rust. It has all your key features like AI integration and community extensions. And, it's like, really fast."
[params]
    image = '/images/zed-editor.png'
    author = 'Vincent Buchner'
    updated_at = '2025-04-25T18:13:40-05:00'
+++

## First Impressions

I’ve been using **Zed** for a couple weeks now, and I’ll admit, it’s impressive.

Zed is a new text editor built in **Rust**, created by the folks who helped build Atom and later worked on VS Code. That lineage shows. It feels like someone took the good parts of those tools, cut the bloat, and added some modern power-user features. If you’ve been bouncing between **VS Code** and **Neovim**, Zed might just land right in the middle: fast, minimal, but smart.

<br>

#### Performance

**It’s fast.** Not _"kinda fast,"_ but really fast. Booting practically takes no time, changing files is seamless, and it plays heavy projects like it's not even trying. That’s because of being compiled in **Rust** and using **GPU-accelerated rendering**, something Zed refers to as _"native performance"_, and this time, it isn't exaggeration.

<br>

#### Collaboration Features

Zed also has a unique way of working together. It has built-in **multiplayer editing**, like Google Docs or Tuple, but for code. You can have others join your session, live edit, and even voice chat, **no plugins needed**. For distributed teams or pair programming, this could be a giant thing.

<br>

#### AI and Plugins

And yes, Zed has **AI integration** now. You can use AI to refactor code, describe snippets, or help you write functions. It’s not core-flow, so it’s optional, which I like. It’s not trying to replace your brain, it’s augmenting it. There’s also a **growing plugin system**, but it’s still early. Zed doesn’t yet have the massive ecosystem of VS Code, but that’s by design. The team is intentionally curating extensions for now, which keeps things **stable and lightweight**.

<br>

#### Vim Mode

Now, one thing that’s important to me is **Vim support**. Zed does have a **Vim mode**, and it’s sufficient for the basics. Motions, operators, and navigation are all there out of the box, but it’s not 1-to-1 with full Vim yet. For me, it’s enough to stay productive, though I still find myself falling back to Neovim when I need those deeper, custom motions or macros.

<br>

## What's Missing

That said, there are a few blockers keeping me from going all-in on Zed.

**No debugger.** This is a big one. I write a bunch of errors, it’s just the way it is, and having the ability to step through a program with an embedded debugger is a massive time-saver. At present, Zed does not have one. I still have to switch over to VS Code or run things manually in a terminal when they fail.

**No Windows support.** Zed is macOS and Linux only for now. That’s not a dealbreaker for me personally, I don’t use Windows as my primary OS anymore, but I do like having the ability to use my editor across all my machines. Until Zed releases on Windows, it’s not a full replacement.

<br>

{{< alert title="The Roadmap" >}}

These features I just mentioned are part of the Zed Roadmap, which is constantly updating. As Zed is a fairly new editor, keep an eye out for the new changes coming!

Check it out here: zed.dev/roadmap

{{< /alert >}}

<br>

## Final Thoughts

So no, Zed hasn’t supplanted my rig completely. But it **has caused me to re-examine** what I want from a text editor. It’s the first in a while that really feels _new_, not just another Electron shell with a different UI.

I’ve started using Zed for all my blog writing, scripting, and even some light React work. It hasn’t fully replaced my other editors, but it’s the first one in a long time that made me pause and think, _“This could.”_

So if you’re editor-curious and want something **fast**, **functional**, and just a little **futuristic**, give Zed a try.
