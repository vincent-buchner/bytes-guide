+++
date = '2025-04-10T15:14:18-05:00'
draft = true
title = 'Rate My Caf: The Full Stack Dumpster Fire That Almost Got Me Expelled'
description = ''
[params]
    image = '/images/rate-my-caf.png'
    author = 'Vincent Buchner'
    updated_at = '2025-04-10T15:12:17-05:00'
+++

Rate My Caf was my first real attempt at a "full stack" app. And I'm using "full stack" in quotes because, in hindsight, it was one of the most elegantly insecure, messy, and bug-ridden apps I've ever made. But for all its sloppiness, it taught me a lot: and nearly got me booted from the college.

The idea was simple: I wanted to build a site where students could review the cafeteria food in real time. If you've ever eaten at a college cafeteria, you know the experience can be... inconsistent. Some days you walk in and it's like Thanksgiving came early. Other days, you're looking at what seems to be microwaved rubber posing as lasagna. It was a crapshoot every time. I figured, "Why not let students warn each other?"

So I built a little website. It was simply a dashboard where students could rate and review the food being served that day. No login, no hassle. You just came in, left your feedback, and boom: it was on the website. Other students could open the page and get a quick snapshot of what people were saying: "Pizza's good today," "Don't eat the tofu scramble," "Dessert is fire." That kind of thing.

<br>

### The Stack (and the Hacky Workarounds)

I built the frontend in React. I was still pretty new to web dev at the time, so I cobbled together parts from tutorials and Stack Overflow responses, patched in some styling with some good ol' Bootstrap styling, and hoped for the best. But the real twist—the backend—was operated exclusively with. Google Sheets.

That's right, Google Sheets was my database.

You can laugh, but for a small app like this, Sheets wasn't a bad choice. I used a Google Apps Script webhook to handle submissions, appending each review to the sheet and incrementing an aggregate score in real time. I even put in some basic filters to prevent spam or repeat entries. It was hacky, sure, but it worked. Above all, it enabled me to deliver something without needing to spin up a Postgres instance or set up an entire backend.

<br>

### The Plot Twist: I Got Blocked

Things got weird after students started using the site. Word spread fast. Students had rated meals using Rate My Caf within a few days, and the dashboard was being shared. I was stoked! I felt I'd made something that people actually found useful.

Then, one day, it broke.

I couldn't get to the site anymore. Neither could anyone else. At first, I thought I'd gone and broken something, but after a little digging, I found out it had been blocked by the college network.

Sh*t.

I called the campus IT department to ask what was going on. They put me on hold. When they came back, they said someone from dining services needed to speak with me. Specifically, the *head* of dining services.

By now, I thought I was cooked. I wore a suit to the meeting, half expecting to be told that I'd violated some obscure rule and was going to be expelled. I even packed my backpack like I'd need to be off campus that day. Overdramatic, I know, but I was losing it.

<br>

### The Meeting

Surprisingly, the meeting was relaxed! The director of dining services wasn't angry. In fact, he was pretty interested in the whole project. He didn't mind if the site was live, but he had two requests: First, the data needed to be accessible to them so they could analyze it. Second, he wanted the site to be a bit more "official": less meme-y and more like a real useful tool that might actually be used to improve food service.

Fair enough.

We had a wonderful conversation about transparency, student feedback, and the fact that the dining staff was genuinely interested in improving. They saw my project not as an attack, but as a chance to engage students in a more direct conversation about campus food. It wasn't what I expected, but I welcomed it and was actually a bit flattered.

<br>

### Lessons and Legacy

I never did resurrect Rate My Caf in its original form. With the buggy React codebase and the fragile Google Sheets setup, it was barely limping along. But I had parted on good terms with the dining staff, and they would occasionally reach out to me with questions or ideas. Even though the app itself is no longer running, the relationships I formed through that project were more important than any working codebase.

Technically, it was a nightmare. I learned about dependency hell, race conditions, and validation the hard way. But from a *growth* perspective, Rate My Caf was precious. It taught me the merit of building something small and focused for a real community. It taught me to expect the unexpected: like getting called into a meeting with campus administrators over a food rating app. And above all, it taught me that shipping something, albeit imperfectly, is usually more valuable than waiting to get it perfect.

<br>

### What's Next?

Will I ever revive it? Maybe. If I did, I'd definitely use a more robust stack—probably Django or FastAPI on the backend and maybe Supabase or Postgres for the database. I'd also add user accounts, moderation features, and some data visualizations. And of course, I'd take security way more seriously this time.

But for now, Rate My Caf lives on in my memory (and in some screenshots that I saved). It was a crazy, caffeine-fueled, bug-ridden experiment and I loved every minute of it.

