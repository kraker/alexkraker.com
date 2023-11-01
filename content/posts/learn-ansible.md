---
title: On Learning Ansible
date: 2023-10-31
draft: false
---

_Short on time? Skip to the [tl;dr](#tldr)._

I recently had somebody reach out to me on LinkedIn asking if I would mentor them
in Ansible. This isn't the first time I've received a request to coach or mentor on
some skill that I have, but like most sysadmins I'm low on bandwidth and it's
hard to find time to put towards my own side-projects let alone take on
individual mentees who reach out on social media.

"The cobbler's children have no shoes," as they say...

But, I do really enjoy mentoring junior sysadmins, developers, 
and sharing my knowledge with others when I have the opportunity. I gave this 
person a book 
recommendation, "Ansible for DevOps" by Jeff Geerling, and a link to the
Ansible Discord server where I sometimes field questions or requests for help.
(Hari, if you're reading this, thanks for the inspiration to make this post!)
I've given advice to co-workers and other tech friends I know
outside of work on learning Ansible. But this got me thinking that I should
really write up some of my suggestions so that it can be useful to more people.

And so, without further ado, here are my recommendations for learning Ansible.

## Pre-requisites

Learn Linux.

You don't have to be a Linux system administrator, but because Ansible
runs on Linux and to learn it you need to run Ansible commands in the Linux
CLI, it's helpful to have some Linux under your belt. You don't have to be a
seasoned Linux administrator to become productive with Ansible, but I would say
basic proficiency with the Linux CLI is a pre-requisite. Otherwise, it's
going to be a steep learning curve, and there's real risk that you won't overcome
frustration barriers to learning and will quit before you've really
[grok'd](https://en.wikipedia.org/wiki/Grok) enough to feel empowered with it.

_Learning the Linux CLI is out of the scope of this guide, but is probably a
good topic for a future post, so stay-tuned!_

In the meantime feel free to check out my list of
[Unix & Linux](devops-learning-resources.md#unix--linux)
devops learning resources.

## Write 1-2 useful playbooks

Write a simple playbook or two that does something useful and get it to run.

I was fortunate enough to have to write Ansible to solve problems at
work. If you have work problems you can solve with Ansible you're in luck! Just
start with one of those.

But, if you don't need to learn Ansible for work, try to think of some things
that might be useful to you if you were to automate them. Things that you've had to
do more than a handful of times repeatedly are probably good candidates. Or just
pick something you think is interesting or relevant. Some examples..
setup a [LAMP stack](https://en.wikipedia.org/wiki/LAMP_(software_bundle)) with
Ansible, automate system updates, configure some tool you
use, like SSH, for example... Or maybe take a Bash script you've written to
automate something and "ansibleize" it by converting it to Ansible code.
There's lots of options.

Pick something that's relevant to you, so you're invested, and then break
ground on it.

> **TIP:** Go find an [example playbook](https://github.com/ansible/ansible-examples)
> or two, and copy some of the boilerplate code to get you started.

Start by doing, and then when you work through more formal learning materials
later on, the topics and concepts will make more sense to you because you've
already had some exposure. This primes the mind for those "ah-hah" moments that
really solidify your learning.

## "Ansible for DevOps" by Jeff Geerling

After you've written some useful little playbooks and maybe played with a few 
[ad-hoc](https://docs.ansible.com/ansible/latest/command_guide/intro_adhoc.html)
commands my next suggestion is to go buy
[Ansible for DevOps](https://www.ansiblefordevops.com/) by Jeff Geerling.

Seriously, if you want to learn Ansible, go buy this book.

This is the single greatest resource I found for learning Ansible. Actually, go 
buy this first, and then [write 1-2 useful playbooks](#write-little-playbooks),
if you haven't already.

Jeff Geerling does a really superb job of working through all of the important
concepts of automation and Ansible, including some DevOps and CI/CD stuff. I
would say if you do nothing else, work through (most of) the
chapters in this book, and that's 80-90% of what you need to know to become
proficient with Ansible. The rest will come from experience as you build things
with it.

And do this sooner rather than later. I wish I had read this sooner. Some of the
more advanced concepts like using Ansible "Roles" and integration testing with Molecule
I wasn't even aware of until I read this book. This is the point where I started to think
about Ansible as a _system_ for describing infrastructure as code (IaC), as part of
CI/CD pipelines, and not just a tool for deploying things with playbooks.

It would be perfectly fine to stop at this point. Everything else I'm going
to recommend after this point is merely supplemental.

### Ansible for DevOps on YouTube

If you're somebody who prefers to ingest learning materials through video, Jeff
Geerling has helpfully published a series of YouTube videos that covers all of the
material from the book titled [Ansible 101](https://www.youtube.com/playlist?list=PL2_OBreMn7FqZkvMYt6ATmgC0KAGGJNAN).

## Ansible Docs

The [Ansible documentation](https://docs.ansible.com/) is really pretty good in
my opinion. It's well written with lots of helpful examples. After you've learned
some of the basics, this is a great resource.

## Where to ask for help

Knowing where to look for answers or ask for help is important. Other than the
usual suspects (i.e. Googling, or Stack Overflow...), there's a few helpful
resources that are Ansible-specific that you should be aware of.

### Ansible Discord

There's an [Ansible Discord](https://discord.gg/3v9snT7QgA) that is a helpful
resource to get your questions answered or ask for help with something.
There's usually a few smart individuals who answer questions and give helpful advice. I've been
known to answer questions or help debug an issue or two here and there. (Say hello
to @stovepipe if you stop by).

### Ansible Forums

The [Ansible forums](https://forum.ansible.com/) are also a good place to search
for answers or get your questions answered if there's not already a relevant thread.

## Learn by doing

There's really no substitute to learning by doing. This should really be a
constant throughout your learning path in my opinion. After you've learned the
basics or perhaps you've worked through parts of "Ansible for DevOps", find a piece
of automation or two that you're interested in or that solves a problem
relevant to you and work on it. Issues that are relevant to you have
staying power. It may be more challenging to stick with developing something
that you're not invested in.

## Write an Ansible Role

Before using things like
[Ansible Roles](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_reuse_roles.html)
in your playbooks it's important to understand how they work. The best way to do
this is to write one yourself. I suggest taking a playbook you've written that's
on the longer or more complex side, and see if you can refactor it into a role.
This is helpful for starting to think about how to "generalize" a solution so
that it works for multiple use-cases (i.e. is reusable).

> **TIP:** Actually, even if I know what I'm writing is going to end up being a
> Role, often times I'll start out by writing it as a playbook. I find that it's
> easier to reason out the nuts and bolts of a piece of automation this way.

"Ansible for DevOps" has a chapter on Ansible Roles, so that's a good place to
start, but definitely write your own Role at some point so that you understand
how they work.

It's a bit of a cognitive leap from writing playbooks to developing a role.
Expect there to be a bit of a frustration barrier here. If you've learned any
object oriented programming (OOP) I think learning how Ansible roles work is
similar to trying to wrap your head around OOP for the first time.

Learning how to write and use Ansible Roles is what unlocked the true power of
automating things with Ansible for me.

## Ansible Galaxy and reading other people's code

Once you've authored your own Ansible Role, you can confidently adapt and use
Ansible Roles from [Ansible Galaxy](https://galaxy.ansible.com/). Be sure to
read the
[Galaxy User Guide](https://docs.ansible.com/ansible/latest/galaxy/user_guide.html),
if you haven't already.

I recommend reviewing the source-code of any Ansible Role you intend to use. This
is a good way to pick up useful idioms and tricks from other developers. You'll
also start to develop a discerning eye for good Ansible code. Once you've 
learned the fundamentals, reading, understanding, and adapting other people's
code is a great way to accelerate your learning.

Or if you're like me, you may find yourself
[forking existing roles](https://github.com/kraker?tab=repositories&q=ansible&type=&language=&sort=)
to add features, or make small improvements. This can be a great way to advance
your skills, also.

## Other miscellaneous tips & tricks

### Notes on ChatGPT and other LLM's

Stay away from ChatGPT and ather LLM's at first. It's
ok to use ChatGPT to summarize concepts and as a learning aid, but try to
refrain from using it to write your code for you. Learn Ansible "the hard way"
first, and then when you do turn to those types of tools later on, you'll have a
more descerning eye and will be able to effectively judge the merits of an answer
given to you by something like ChatGPT.

### Don't be afraid to refactor your own code as you learn

As you learn, you'll understand better ways to implement your ideas or solve
problems with Ansible. Don't be afraid to do a complete refactor of something to
implement it using what you've learned. I've completely refactored some solutions
2-3 times or more...

Refactoring code you've written while incorporating new skills and concepts is a
great way to solidify that learning.

### Use debug statements liberally

When testing and developing Ansible, use
[debug statements](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/debug_module.html)
to understand your variables or print useful debug messages. Use them liberally
to understand your code. You can delete them (or comment them out) later.

### Use -vvv

With `ansible` and `ansible-playbook` commands use `-vvv` to get a better idea
of what the different modules are doing while your playbook or ad-hoc
commands are running.

### Do things manually first

Make sure you know how to do something manually by running commands in the
terminal first before automating it with Ansible. If you don't know how to do
something manually via commands in the CLI you're going to have a hard time
automating it with Ansible.

### Smoke tests and validation

Frequently remote into the machines your writing code for with SSH (or WinRM if
you're targeting Windows Servers), and check that your Ansible code did what you
intended for it to do. Don't just take Ansible's word for it.

## tl;dr

**Pre-requisites:** Basic Linux CLI proficiency.

0. Start by [installing Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html) and write a few simple little playbooks that do useful things and get them to run.
1. Go get [Ansible for DevOps](https://www.ansiblefordevops.com/) by Jeff Geerling and work through (most of) the chapters and do the exercises. **If you only do one thing, do this!**
2. Read the [docs](https://docs.ansible.com/).
3. Know where to go to ask for help. [Ansible Discord](https://www.ansiblefordevops.com/) and [Ansible Forums](). 
4. Learn by doing. Pick something you're invested in, and work on it. It's ok if you don't finish.
5. After you've learned the basics of how to run ad-hoc commands and write playbooks, write an [Ansible Role](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_reuse_roles.html).
6. Read other people's code. (**TIP:** search [Ansible Galaxy](https://galaxy.ansible.com/) for Roles, and look at the source).
7. Incorporate other people's code into your own whether that's borrowing code snippits, using a role, or something else.
8. Learn Ansible "the hard way" first before leveraging AI tools like ChatGPT or other LLM's.
9. Use lots of debug statements and run ansible commands with `-vvv` to understand what your code is doing.
