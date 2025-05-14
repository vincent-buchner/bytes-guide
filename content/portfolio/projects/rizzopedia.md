+++
date = '2025-04-10T15:14:26-05:00'
draft = false
title = 'Rizzopedia: Brainrot 🤝 ML'
description = ''
[params]
    image = '/images/rizzopedia.png'
    author = 'Vincent Buchner'
    updated_at = '2025-04-10T15:12:17-05:00'
+++

## Rizzopedia: A Ridiculously Dumb App That Actually Taught Me a Bunch of Things

Rizzopedia was, in all honesty, a dumb project. Not dumb because it didn't work, or because it was useless; more because it was built out of a meme. But that's kind of what made it so fun. It was one of those "I wonder if I can." thing that spirals out of control and turns into a fully deployed web app you never thought anyone would actually use. And then people did.

<br>

### So, what was Rizzopedia?

In essence, it was a web application where you could input any line of text: maybe a cringey pickup line or maybe something less subtle. It would then feed that sentence into a sentiment analysis algorithm that I had deployed. Based on some linguistic properties and some heuristics that were determined from web scrapped pickup lines, it would determine whether or not that sentence had rizz.

{{< alert title="Define Rizz" type="success" >}}

For beginners, "rizz" is Gen Z slang for charisma—particularly in a romantic or flirting situation. When someone says "you've got rizz," they mean you've got charm. So, of course, I thought: what if I were able to create an app that gives people's rizz a real-time judgment.

{{< /alert >}}

<br>

### Building the Backend
I used Django as the framework in this case. I had dabbled with it a bit before but had never started from scratch with something that was actually deployed for other folks to use. The ORM and admin panel of Django enabled me to have a working backend up quickly, and it gave me scaffolding while I developed the things I was most interested in—text analysis.

For the "rizz detection" algorithm, I did not venture out and train a deep neural net or anything of that sort. This was more of a lightweight, rules-based classifier, stealing from straightforward natural language processing libraries such as NLTK and spaCy. I looked at sentiment polarity, subjectivity, keyword frequency, and some weighted custom weights based on certain buzzwords or sentence patterns. If you said "hey girl, are you a magician…" you'd probably get high rizz. If you said "the mitochondria is the powerhouse of the cell," not so much.

I could have used a pretrained model like BERT, or invoked an external sentiment API, but I did not wish to have things be slow, remote, and mystical. And some of the project goal was that I would learn. I was still quite new to machine learning and natural language processing, so this was a chance to experiment with ideas in a very absurd but tangible manner.

<br>

### Frontend and User Experience
For the frontend, it was pretty simple. One input field, a submit button, and a results page that told you if your message had rizz—or didn't. No frills. No distractions. Just a clean UI.

Even with the minimalism, I thought about how the response was framed. If you had rizz, you didn't just get a "Yes." You got an over-the-top affirmation: "Certified Rizz God." If not? "Negative Rizz Detected. Try again." I wanted it to be playful. I mean, if you're making an app on pickup lines, you might as well go all in on the absurdity.

<br>

#### Going Live
I decided to deploy the app and make it available for public use. I set it up on Railway, set up gunicorn and nginx, and sent the site live. I assumed maybe a couple of friends would try it out once, laugh, and never consider it again.

What I did not expect was for word to spread. Within a couple of days, strangers were sharing with me screenshots of their rizz scores. Individuals were submitting jokes, testing each other, and even applying it on lunch breaks as a motivational tool.

<br>

### Lessons Learned
Even though the concept was absurd, the project was a goldmine of learning. It forced me to think front to back—frontend, backend, deployment, user input, UX, and error handling. I could experiment with machine learning-like concepts, get to use Django's full feature set, and see how web apps come together end to end.

It was my first real experience with production bugs, scaling weirdness, and working with anonymous user input. You quickly learn to appreciate all the things you didn't sanitize, all the edge cases you didn't handle, and all the ways your site can be misused (or just used more than you ever expected).

<br>

{{< alert title="Where is it now?" >}}

Rizzopedia is currently down. I took it down since I didn't want to shell out money hosting something that, while fun, had served its purpose. I still have the source code, and I've thought about reviving it: maybe with a login system, leaderboards, or a system for users to save and compare their scores. But it's not something that I'm currently working on. I've shifted on to other projects, and I'm more excited about what I can create next.


{{< /alert >}}

But I'll always regard Rizzopedia with affection. It was stupid. It was crazy. It was enjoyable. And above all, it was effective.

Sometimes, learning best happens not through a well-defined, deeply scholarly project. Sometimes, it happens through creating something absurd and finding out where you end up.
