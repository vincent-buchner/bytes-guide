+++
date = '2025-04-29T16:48:26-05:00'
draft = false
title = 'Feathr: A Physics Based Social Network'
description = ''
[params]
    image = '/images/feathr.png'
    author = 'Vincent Buchner'
    updated_at = '2025-04-29T16:48:26-05:00'
+++

You’ll have to bear with me for this one, there’s a lot going on in this project. It’s probably the most ambitious thing I’ve worked on so far, both in terms of scope and in how deeply it pushed me to grow as a developer. But hey, that’s what makes it worth writing about.

Earlier this year, I was fortunate enough to be on a team of four on a capstone-style project. We were essentially given a lot of liberty with the scope of the project: we could create a mobile app, a game, a research paper - anything we wanted. Naturally, instead of playing it safe, we decided we'd build Feathr.

<br>

## What is Feathr?

Essentially, Feathr is a physics-social network. Yes, you read that correctly: physics-social network. Social network sites are, by and large, location-independent: they show you what they think you might want to see, mediated through a hundred different algorithms. We flipped that around. Rather than bringing the world to the user, Feathr brings the user into the world. And that world, in particular, is a simulated world based on particle physics and flock behavior.

<br>

## A Different Social Network

Here's the big-picture concept:

When a user joins Feathr, they're not merely plopped into a feed. They're plopped into a simulation as a particle. Think of it like a virtual world where you, as a user, are a particle that's randomly tossed into space.

Once you're in the simulation, you're not alone. There are other players as particles. If your particle gets close to another person's, you get to see their posts and threads. The closer you get, the more you can view. It's content visibility depending on how close you get. If someone gets out of range, you can no longer view their posts. It mimics physical interaction in the real world but in a virtual environment.

In order to control movement and interactions, we used the Boids algorithm to simulate flocking behavior: like the kind you'd see in a school of birds or school of fish. Particles will align, avoid collisions, and move toward common directions. When users interact, thus, they naturally create social "flocks," which are dynamic and come and go. It's beautiful, and is quite conceptually solid.

<br>

### Three Platforms, One Ecosystem
We didn't just stop at one platform. We decided to develop three related systems:

<br>

- • A mobile app for a more interactive, on-the-go experience.

- • A web app for broader reach and easier presentation.

- • An independent backend that took care of the simulation, user data, and messaging rules.

<div class="container-fluid flex items-center justify-center">
    <img src="/images/d2/senior-project-architecture.svg" alt="Architecture Diagram for Feathr by Vincent Buchner" width="500">
</div>

<br>

It was a full-stack project: each part had its own complexities. I was primarily working on the backend and the web frontend, so I'll talk more on those.

<br>

## Backend Challenges and Decisions
Our backend was built utilizing Django REST Framework. It handled the actual real-time simulation loop. Oh, and the simulation itself? We wrote our own multithreaded game engine for it: because apparently we hate having free time.

That simulation engine was really the heart of the system. It was continuously executing the source-of-truth simulation, calculating each particle in the system's position and state. It would, every so often, send snapshots to all connected clients. The client would then base its local rendering of the simulation on that snapshot. This real-time solution meant that we needed performance optimizations. One of the biggest challenges was to efficiently compute which particles were "near" each other since that decided visibility. To calculate this naively (i.e., compare each particle with all other particles) would have been a nightmare of time complexity.

So we used KD Trees: a multi-dimensional spatial partitioning data structure that allows for efficient nearest-neighbor queries in multi-dimensional space. Think of a KD Tree as being like a binary search tree, except rather than splitting on one axis, recursively split on alternating axes (e.g., x, then y, then z). This allowed querying nearby particles in logarithmic instead of linear time, which crucial in maintaining performance and scalability.

<br>

## Web Frontend Experience
The web frontend was built with Next.js, TailwindCSS, and shadcn/ui. I can't sing this stack's praises enough—it was fantastic.

Next.js gave us server-side rendering, routing, and a good developer experience. TailwindCSS assisted us in styling quickly, flexibly, and reliably. Shadcn/ui provided us with clean, accessible component abstractions that saved us oodles of time. They collectively helped us create an interface which was responsive, modern, and actually nice to use, without dipping into design hell.

## DevOps and Deployment
We weren't just coding, we were deploying it as well. We had a full CI/CD pipeline, so whenever we pushed code, it ran our test suite and redeployed the project. And speaking of tests: we exceeded well over 85% test coverage in our backend. Not only did this help to catch regressions early, but it also gave us confidence in refactoring some of the more complex simulation logic.

<br>

## Presentation Day
Then, we demoed Feathr at our school's tech symposium. The demo was flawless, the frontend was smooth, and the simulation behaved as anticipated. That said, I still think we completely confused a large part of the audience. Trying to explain how KD Trees, boids, and a social network all play together in under 15 minutes was... ambitious. But it made an impact.

Feathr was hard. It challenged us in ways I wasn't expecting: specifically on the backend with threading, simulation performance, and data serialization. But it also forced me to have to learn and produce something out the door that felt pretty unique.

I'm proud of what we built. And I don't say that easily. Who knows, maybe Feathr has a future beyond the classroom. For now, it is a testament to what can be achieved when you love a crazy idea and dedicate yourself to bringing it into the world.
