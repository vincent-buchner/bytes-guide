+++
date = '2025-04-25T18:12:04-05:00'
draft = true
title = 'Before Your Next Project, Use D2'
description = "I recently came across a tool that allows you to dynamically create diagrams to architect out your software called D2. What's cool about D2 is that is highly customizable without missing the mark on properly layout your diagram."
[params]
    image = '/images/architect-with-d2.png'
    author = 'Vincent Buchner'
    updated_at = '2025-04-25T18:12:04-05:00'
+++


## What is D2?
D2 is a declarative diagramming language that allows you to architect and plan your software in a more verbose and "auto-beautified" way. In other words: code to diagram, and it looks pretty sweet! Even though D2 handles a lot of styling, there is no shortage of customizability. You can do everything from your own CSS-like styling, themes, images, layouts, fonts, and more. In this article, I will just give a brief overview on how D2 looks and feels, and at the end I will provide my opinion on why and what you should be applying this for.

<br>

## Getting Started
First, you will need to install D2. I found the simplest way to just be through the terminal with the following command, which is also what the folks at [Terrastruct]("https://terrastruct.com/") recommend as well. They have too options: A dry run to see if there will be no error and then the actual command. Which, personally, I really like and wish more software did.

```sh
# NOTE: This command DOES NOT install it on your machine - just tests to see if able
curl -fsSL https://d2lang.com/install.sh | sh -s -- --dry-run

# This command will install
curl -fsSL https://d2lang.com/install.sh | sh -s --
```

Sweet, so now you have it installed! What I would recommend next, if you're using VS Code, is to install the extension of D2. It allows you to see you diagrams live while you're editing them, which can save you a lot of back and forth. Check out the docs <u>[here](https://d2lang.com/tour/vscode)</u> or just search `d2` in the Extensions tab.

<br>

## Examples and Best Practices

For reference, I will leave a table of contents here that you can use to navigate to any particular section you'd like. I'll go in the order that I think beginners should take when picking up D2, but feel free to do whatever best fits your use case. By the end of this guide you will be able to create most diagrams, but for more information check out the <u>[docs]("https://d2lang.com/")</u>!

- • <u>[Hey Mom!](#hey-mom)</u>
- • <u>[Working With Shapes](#working-with-shapes)</u>
- • <u>[Grouping With Containers]()</u>
- • <u>[Insert Images/Icons]()</u>
- • <u>[Add Text]()</u>
- • <u>[Positioning]()</u>

<br>

### Hey Mom!

Let's kick off our first diagram. Let's say your project manager (mom) gives you the following task:

> "I need you to take the chicken out of the freezer and into the sink."

Instead of actually doing it, we can come up with a comprehensive diagram that would virtual demonstrate how we would do such a task. In D2, we can do that in the following manner.

```sh
# Key Word: tells the diagram what way to orient itself
direction: right

# The freezer is connected to the sink, by the transportation of the chicken
freezer -> sink: chicken
```

The `#` in this block of code are comments, and will not be ran or seen in the diagram. They can be used to explain the code inside the code itself. We specify the direction we'd like the diagram to go at the top of the file (by default it will go from top to bottom). Then we define the key `freezer` and connect it with an arrow to the key `sink`, which we then put a label on the relationship called `chicken`. The result should be something like this: 

<div class="container-fluid flex items-center justify-center">
    <img src="/images/d2/demo-1.svg" alt="Chicken Move Diagram" width="500">
</div>

Perfect! We are now ready to show that to our project manager and get critiques on implementation! Being able to render that means that your install of D2 was successful and you are ready to make more complex diagrams!

<br>

## Working With Shapes
Let us start by learning about different shapes. D2 allows you to represent nodes in different shapes—rectangles, circles, ellipses, and more. You can use one shape to represent another object or concept depending on what you want to achieve with your diagram.

```sh
direction: right

freezer: {
  shape: rect
}
sink: {
  shape: ellipse
}
freezer -> sink: chicken

```

This instructs D2 to draw the freezer as a rectangle and the sink as an ellipse. It's all about simplicity—use shapes deliberately to make diagrams simpler to scan and comprehend at a glance.

<br>

## Grouping With Containers

At times you'll need to group nodes that are related. Containers let you encapsulate nodes inside a visual boundary, such as grouping microservices within a "backend" box.
```sh
direction: right

kitchen {
  label: "Kitchen"
  freezer
  sink
}

```

This forms a box with the label "Kitchen" and the freezer and sink inside it. Containers are also handy for displaying hierarchies, subsystems, or just for bunching together like-related elements of your diagram.

You can even nest containers:
```sh
house: {
  kitchen: {
    freezer
    sink
  }
  garage: {
    toolbox
  }
}

```

<br>

## Insert Images/Icons
D2 does allow for the insertion of icons through the icon key, and even direct image embedding.

```sh
chicken: {
  icon: https://www.freesvgdownload.com/wp-content/uploads/2024/10/rooster-600x600.webp
}

sink: {
  icon: https://www.svgrepo.com/show/490210/sink.svg
}

```


If you'd like to go beyond icons and embed real images:
```sh
fridge: {
  image: https://example.com/fridge.png
}
```

This will replace a node with an image. Watch out for resolution and aspect ratio here—D2 tries to preserve readability, but big images can ruin layouts.

<br>

## Add Text
Every now and then labels on nodes and edges simply aren't sufficient. You may want to give your diagrams a bit more context or explanations.

```sh
note: {
  shape: page
  label: "Remember to thaw the chicken first!"
}

note -> sink
```

You can also have tooltip fields for hover-over hints in interactive renderers:

```sh
sink {
  tooltip: "Wash thoroughly before cooking"
}
```

Tooltips won't be visible in all export formats (e.g., static SVG), but they're highly convenient in HTML-based previews.

<br>

## Wrapping Up
And there you have it—those are the fundamentals! You now have the ability to:

- • Create basic diagrams
- • Customize shapes and icons
- • Collect elements with containers
- • Annotate using text and tooltips

In all practical applications, this is more than adequate to start diagramming complex systems, processes, or even silly "talk to mom" diagrams. You can version them in your git repos, render them via CLI tools, and export as clean SVG or PNG files.

As promised, here is the link to the <u>[D2 docs](https://d2lang.com/tour/intro/)</u> again: they go much deeper into syntax, styling, themes, and integrations.
