+++
date = '2025-06-15T13:12:06-05:00'
draft = false
title = 'How I Think You Should Learn Vim (Without Losing Your Mind)'
description = 'Or teach your AI how to...'
[params]
    image = '/images/learn-vim.png'
    author = 'Vincent Buchner'
    updated_at = '2025-06-15T13:12:06-05:00'
+++

This post is primarily about the approach that I think you should take if you want to learn Vim.

And actually, I should be clearer and speak in terms of Vim keybinds. Vim keybindings allow you to work on your code without ever having to pick up the mouse. When they're second nature, utilizing them will be as natural as having an extra pair of hands: precise, effective, and fast. While most developers in the modern era rely on AI to code or autocomplete (which is great), I still feel that Vim keybindings are one of the most effective things you can learn as a programmer.

Now, just to put this out there, I'm not a Vim-only fanatic. I do have Neovim set up and it's great, but my default is VSCode with the Vim extension. I've found this setup much more user-friendly, especially for large projects. For tiny scripts or one-off changes, I'll use Neovim. But for most projects, I use VSCode.

Neovim is responsive and feels incredibly powerful, but it's daunting to set up. It's time and effort that simply leave you at the point where you're ready to start your actual project. I find myself idealizing Neovim, setting it up, getting bored before I even write any code, and switching back to VSCode. Wash, rinse, repeat.But anyway, on to the actual keybinds and learning Vim properly.

## Getting Started with the Basics
Let's talk about the basics—the things that are absolutely vital in understanding how Vim works before we get into plugins and fancy macros.

### Modes
Vim is unlike most editors. It has modes. You'll be spending most of your time switching between these:

- ◾ Normal mode: Where you navigate around and edit text.
- ◾ Insert mode: Where you type in text (like you're used to).
- ◾ Visual mode: For selection of text.
- ◾ Command mode: Where you save, quit, or search.

`ESC` quits anything. `i` goes into insert mode. `v` enters visual mode. `:` enters command mode.

### Movement around
`h, j, k, l`: left, down, up, right. Weird at first, but it does get the better of you.

`w`: move forward by word.

`b`: move back by word.
`gg`: move to file top.

`G`: move to bottom.

### Copying and Pasting
In Vim terms:
- `yy`: yank (copy) a line.
- `p`: paste after the cursor.
- `P`: paste before the cursor.
- `dd`: delete (cut) a line.
- `u`: undo.
- `Ctrl + r`: redo.

In the editor vs in the system clipboard:

Use `"+y` to yank to system clipboard.
Use `"+p` to paste from system clipboard.

### Re-centering
Super underrated: `zz` will center the line you’re on. Helpful when scrolling through long files.

#### Some of My Custom Keybinds
Custom keybindings are what really make Vim feel like yours. A few I've used all the time:

`Shift + J / K`: I remapped those to scroll up and down 5 lines at a time. Makes navigating faster.

`Leader key`: I've bound my `<leader>` key to the spacebar. Much nicer on the fingers than the default. With the leader key, I can set up keybinds like `<leader>ff` to find files, `<leader>w` to save, or `<leader>q` to quit.

This is where your productivity really starts to add up. Small gains in keystrokes add up fast.

### More Advanced: Macros and Recording
This is where Vim gets really magical.

Press `q` and any letter (say q) to start recording.

Do a series of actions.

Press `q` again to end recording.

Now every time you type `@q`, all those steps repeat. 

Example: you have to delete a line, go next, and paste there. You can record once and run 20 times through your file in one command. Highly useful when cleaning up messy data files or similar refactors.

### Starting Out: My Real Recommendation
If you're new to Vim, don't start with Neovim. You'll be intimidated. You'll end up spending more time configuring your editor than learning how to use it.

Start with VSCode + Vim extension. It gives you most of the keybinds and lets you learn muscle memory within a familiar framework.

After you get comfortable, try to migrate to Neovim with something like LazyVim. It's a starter pre-configured with lots of handy tools so you don't have to write your entire setup from scratch.

Don't rush. Learn incrementally. Take on one new keybind at a time and use it until it is second nature.

### Final Thoughts
Vim keybinds are not hipster hacker wannabe. They are about preserving flow. They permit you to compose, refactor, and travel through your code without breaking rhythm.

Even should you not take the plunge and become a zealot Neovim convert, the time you spend learning at least a few Vim keybinds will accelerate you and make you more cognizant of how you operate with code.

Just don't forget to actually write some code in the meantime.
