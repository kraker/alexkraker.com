---
title: Learning Ansible
date: 2023-10-31
draft: true
---

I recently had somebody reach out to me on LinkedIn asking if I would mentor them
in Ansible. This isn't the first time something like that has happened, but as
with most sysadmins I'm low on bandwidth and it's hard to find time to put
towards my own side-projects let alone take on mentoring folks individually who ask through
various forums. "The cobbler's children have no shoes," as they say.

But, I do really enjoy mentoring junior sysadmins, junior developers, and sharing my 
knowledge with others. I gave this individual a book recommendation and a link to the 
Ansible Discord server, where I sometimes field questions. But this got me thinking,
I should really write up some of my suggestions so that it can be useful to more
people.

I learned Ansible mostly on my own. And I honestly fell in love with it as a tool.
So much of how Ansible functions just makes
sense to me; as if it was written with the Linux Administrator in mind. And it's 
exhilerating (if a bit nerve-racking) to deploy
changes to not just 1 or 2, or a handful of servers, but literally hundreds of
servers the first time you do it. Ansible really makes Ops possible in so many 
ways that would be more difficult with custom Bash scripts or manually executing 
commands.

And so, without further ado, here are my recommendations for learning Ansible.

## Pre-requisites

Learn Linux. 

You don't have to be a Linux system administrator, but because Ansible
runs on Linux and to learn it you need to run Ansible commands in the Linux 
CLI, it's helpful to have some Linux under your belt. You don't have to be a 
seasoned Linux administrator to become productive with Ansible, but I would say 
basic proficiency with the Linux CLI is a pre-requisite. Otherwise, it's just 
going to be a steep learning curve, and there's real risk that you won't overcome
frustration barriers to learning and quit before you've really grok'd enough
to feel empowered with it.

Learning the Linux CLI is out of the scope of this guide, but is probably a
good topic for a future post, so stay-tuned!

In the meantime feel free to check out the [Unix & Linux](devops-learning-resources.md#unix--linux)
section of my "DevOps Learning Resources" guide.

## Write Little Playbooks

I was fortunate enough to have to write Ansible playbooks to solve problems at
work. Learning projects were work projects and problems I needed to solve, so I
didn't have to go searching for interesting problems.

But, if you don't need to learn Ansible for work, try to think of some things
that might be helpful if you were to automate them. Things that you've had to 
do more than a handful of times repeatedly are probably good candidates. Or just
pick something you think is interesting or relevant. Just a random example, but
you could setup a LAMP stack with Ansible. Run system updates. Configure some tool you
use, like SSH, etc. Or maybe take a Bash script you've written to automate some
thing and "ansibleize" it by converting it to Ansible code. There's lots of options.

Project-based learning is really one of the best ways to learn so why not start
with it? If you have some Linux CLI under your belt, Ansible is forgiving enough
that you can probably muddle your way through installing it and running a few
ad-hoc commands and drafting a simple playbook or two.

Pick something that's relevant to you, so you're invested, and then break
ground on it.

> **TIP:** Go find an example playbook or two, and copy some of the boilerplate code
> to get you started.

Start by doing, and then when you read the books or courses later on, the topics
and concepts will make more sense to you because you've already had some exposure.
This primes the mind for those "ah-hah" moments that really solidify your learning.

## Ansible for DevOps

After you've written some little playbooks, maybe played with a few ad-hoc Ansible
commands, and "made a thing" with Ansible my next suggestion is to go buy
"Ansible for DevOps" by Jeff Geerling. Seriously, if you want to learn Ansible,
go buy this book. This is the single greatest resource I found for learning Ansible. 
Actually, go buy this first, and then write a few little playbooks.

Jeff Geerling does a really superb job of working through all of the important
concepts of automation and Ansible, including some basic CI/CD stuff. I would say
if you do nothing else, work through the
(or most...it's ok to skip a few that might not be relevant to you) 
chapters in this book, and that's 80-90% of what you need to know to become 
proficient with Ansible. The rest will come from practice as you build things with
it.

And do this sooner rather than later. I wish I had read this sooner. Some of the
more advanced concepts like using Ansible "Roles" and "Collections" I wasn't even
aware of until I read this book. This is the point where I started to think
about Ansible as a _system_ for describing infrastructure as code (IaC) and not
just a tool for deploying things with playbooks.

It would be perfectly fine to stop at this point. Everything else I'm going
to recommend after this point is merely supplemental.

### Ansible for DevOps on YouTube

If you're somebody who prefers to ingest learning materials through video, Jeff
Geerling has helpfully published a series of YouTube videos that covers all of the
material from the book "Ansible for DevOps" that I mentioned in the previous
section.

## Ansible Docs

The Ansible documentation is really pretty good in my opinion. It may not make
as much sense at first but after you've learned the basics, the Ansible 
documentation is really fairly easy to understand with lots of helpful examples.
There's certainly a lot of examples of worse docs out there. 

## Ansible Discord

There's an Ansible Discord that is a helpful resource to ask questions with
a few smart individuals who answer questions and give helpful advice. I've been
known to answer questions or help debug an issue or two here and there.

## Write an Ansible Role

Before using Ansible roles from Ansible Galaxy it's important to understand how
they work by writing one yourself. I suggest taking a playbook you've written
that's maybe on the longer and more complex side, and seeing if you can refactor it
into an Ansible Role. This is helpful for starting to think about how variables
are scoped and work in Ansible and how they can be used to "generalize" a solution
so that it works for multiple use-cases. 

"Ansible for DevOps" has a chapter on Ansible Roles, so that's a good place to start,
but definitely write your own Role at some point so that you understand how they work. 

Any longer playbooks that you have that have grown to over 100 lines, you should
seriously consider refactoring into a role. 

It's a bit of a cognitive leap from writing playbooks to authoring a role. Expect
there to be a bit of a frustration barrier here. If you've learned any object
oriented programming I think it's not dissimilar to trying to wrap your head
around OOP the first time.

## Ansible Galaxy and reading other people's code

Once you've authored your own Ansible Role, you can confidently adapt and use
Ansible Roles from Ansible Galaxy. Definitely be sure to check out the 
Ansible Galaxy user's guide first. 

I recommend reviewing the source-code of any Ansible Role you intend to use. This
is also a good way to pick up useful idioms and tricks from other developers. 
You'll also start to develop a discerning eye for good Ansible code. Once you've
learned the fundamentals, reading, understanding, and adopting
other people's code is a great way to accelerate your learning.

> **Note:** In production environments it pays to thoroughly review the code you intend to
> use and make sure that you aren't buying too much technical debt with it, and that
> it's a solid solution for your use-case.

Or if you're like me, you may find yourself forking existing roles to add features, or make
improvements. This can be a great way to advance your skills.

## Other miscellaneous tips & tricks

### Notes on ChatGPT and other LLM's

Stay away from ChatGPT and ather LLM's at first to write your Ansible code. It's
ok to use ChatGPT to summarize concepts and as a learning aid, but try to refrain
from using it to write your code for you.
Learn Ansible the hard way first, and then when you do turn to those types of tools later on, you'll have a more
descerning eye and will be able to effectively judge the merits of any solution
given to you by something like ChatGPT.

### Don't be afraid to refactor your own code as you learn

As you learn, you'll understand better ways to implement your ideas or solve
problems with Ansible. Don't be afraid to do a complete refactor of something to
implement it using what you've learned. I've completely refactored some solutions
2-3 times or more...

Refactoring code you've written while incorporating new skills and concepts is a 
great way to solidify that learning.

### Don't be afraid to change directions

In some cases you may find yourself on a development path that's not bearing
fruit. It's ok to 180 and take a different tack. Don't be a slave to "sunk costs"
and get stuck in a rut. Sometimes the path to the solution is a windy-road, with
many forks along the way. You may have to back-track to get to the destination.

Don't forget to enjoy the journey though ;-\)

### Use debug statements liberally

When testing and writing, use debug statements to understand your variables. Use
them liberally to understand your code. You can delete them (or comment them out) later.

### Use -vvv

With `ansible` and `ansible-playbook` commands use `-vvv` to get a better idea 
of what the different modules are doing while your playbook or ad-hoc 
commands are running.

### Do things manually first

Make sure you know how to do something manually by running commands in the
terminal first before automating it with Ansible. If you don't know how to do
something manually via commands in the CLI you're going to have a hard time 
automating it with Ansible.

Frequently remote into the machines your writing code for with SSH (or WinRM if 
you're targeting Windows Servers), and check that your Ansible code did what you 
intended for it to do.

## tl;dr

**Pre-requisites:** Basic Linux CLI proficiency.

1. Project-based learning. Start by installing Ansible and writing little playbooks to do useful things.
2. Go get "Ansible for DevOps" and work through the chapters and do the exercises. **If you only do one thing, do this.**
3. Read the docs.
4. Know where to go to ask for help. Ansible Discord and Ansible Forums. 
5. After you've learned the basics of how to run ad-hoc commands and write playbooks, write an Ansible Role. This might be a stretch, but push through anyways.
6. Read other people's code. (TIP: search Ansible Galaxy for Roles)
7. Use other people's code by either adapting it or incorporating it into your own somehow.
8. Learn Ansible "the hard way" first before leveraging AI tools like ChatGPT or other LLM's.
9. Use debug statements and `-vvv` when writing your Ansible code to understand what it's doing.
10. Practice, practice, practice...
