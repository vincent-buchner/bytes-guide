+++
date = '2025-04-25T18:06:55-05:00'
draft = false
title = 'Build Incredible Desktop Apps with Your Favorite Frontend Framework and Go'
description = ''
[params]
    image = '/images/wails-project.png'
    author = 'Vincent Buchner'
    updated_at = '2025-04-25T18:06:55-05:00'
+++

If you’ve ever wanted to build a desktop app but hated the idea of learning yet another UI framework, Wails might be exactly what you’re looking for.

I've only recently begun using Wails to build desktop apps with my usual frontend tech stack—React, Tailwind, etc., and I've been amazed at how simple the process is once you have everything set up. You build the frontend like any other web app, and Wails handles the bridge to Go on the backend. It's like building a web app, but it's native on your desktop with full system integrations.



## Why Wails over Electron?

One of the main reasons I’m sticking with Wails instead of something like Electron is speed. Wails apps start up almost instantly because they don’t bundle an entire Chromium browser runtime with each build. Instead, they use the native WebView on your system, which keeps things lightweight and snappy. The final binaries are significantly smaller too; no 300MB monsters just to open a settings page.

And unlike Electron, where memory and CPU usage can balloon if you’re not careful, Wails keeps things tidy. Startup is fast, and memory overhead is minimal. The runtime footprint is closer to what you'd expect from a native app, not a browser-in-a-box.

{{< alert title="Linux quirks when setting up" type="warning" >}}

I did have a couple of issues getting it running on Linux. The most intimidating task was compiling the app—you'll want to make sure you include the `-tags webkit2_41` flag both when building and also when running the dev server. Without it, you'll see some baffling WebKit bindings errors. Just a warning in case you just so happen to be running on a Linux box.

{{< /alert >}}

## Keep your frontend workflow

Another reason I'm sold: you don't have to sacrifice your frontend tools. No Qt or GTK bindings to learn. If you know how to write SPAs or code in Next.js, you'll be comfortable. And since the backend is Go, you get all of the performance benefits and concurrency of it without the need to write boilerplate to have a desktop window up and running.

Wails also exposes a JavaScript bridge that lets you call Go methods from your frontend and vice versa. It's type-safe and ergonomic—you define your Go methods, and Wails generates the JS bindings automatically. This makes interop between the two layers seamless. You’re not stuck wiring up REST endpoints or dealing with raw IPC calls.

Because Go is so performant, you can offload CPU-heavy tasks—like encryption, file system manipulation, or data processing—to the backend, while keeping the frontend reactive and minimal. It’s a really clean separation of concerns that feels natural.

## Built-in tooling that respects your workflow

Wails also does a great job of managing the build lifecycle. When you run `wails dev`, it watches both your Go code and your frontend assets. You can plug in whatever frontend bundler or dev server you want—Vite, Webpack, etc.—and Wails will wait for your assets to be ready before launching the app.

When you're ready to ship, `wails build` packages everything up into a tidy executable for your target platform. You can even cross-compile if you’re building from a Linux or macOS system. The experience is more like working with a full-stack web app than a desktop GUI toolkit.


## A better way to ease into desktop dev

If you'd like to learn about planning a project using Wails, I wrote a separate article detailing how to architect and structure your Wails codebase using D2 diagrams. It covers organizing files, encapsulating concerns between frontend and Go logic, and making your app maintainable when it grows large.

This is one of the most approachable ways I’ve found to break into desktop development without burning out on new tooling. If you’ve been meaning to build a native app, give Wails a shot.

Overall, here’s what stood out to me most:

- **No need to learn a new UI paradigm** – Just use what you know.
- **Tight, simple Go APIs** – No overengineering, no magic.
- **Fast builds and hot reload** – Not perfect, but very usable for iterative development.