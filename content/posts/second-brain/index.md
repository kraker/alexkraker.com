---
title: How I Automated 
date: 2023-11-09
draft: true
---

I'm a religious note-taker. Back in my school days I kept lots of notebooks and
I had a habit of always carying around a Moleskine and jotting down ideas,
writing notes, or journaling. Now many years later I've develped a habit of
writing my notes in digital form. Mostly this was so that I could make them
searchable. At first my notes started out as a few text files but eventually
I started writing all of my notes in [Markdown](https://daringfireball.net/projects/markdown/).
They're still text files, but Markdown is an easy to read and easy to write
markup that renders nicely to HTML. 

Here's an example from my notes:

```markdown
---
title: OSI Model
date: 2020-10-06 07:42
---

**OSI:** Open Systems Interconnection

1. [Layer 7 - Application](2020-10-11--16-57-07Z--layer_7.md)
2. [Layer 6 - Presentation](2020-10-11--16-52-39Z--layer_6.md)
3. [Layer 5 - Session](2020-10-11--16-46-48Z--layer_5.md)
4. [Layer 4 - Transport](2020-10-10--18-46-30Z--layer_4.md)
5. [Layer 3 - Network](2020-10-10--18-44-39Z--layer_3.md)
6. [Layer 2 - Data Link](2020-10-10--18-43-20Z--layer_2.md)
7. [Layer 1 - Physical](2020-10-10--18-41-00Z--layer_1.md)

Mnemonic:
_All People Seem To Need Data Processing._

## References

* https://www.freecodecamp.org/news/osi-model-networking-layers-explained-in-plain-english/
* [Wikipedia - OSI model](https://en.wikipedia.org/wiki/OSI_model)
```

At some point I stumbled across how to maintain your own personal
knowledge-base as a [Zettelkasten](https://zettelkasten.de/introduction/).
I call mine my [second brain](https://notes.kraker.dev/). I experimented with
maintaining a personal wiki in Vim with things like [vimwiki](https://github.com/vimwiki/vimwiki)
and [wiki.vim](https://github.com/lervag/wiki.vim), and even learned Emacs so
that I could try to organize my life with [org-mode](https://orgmode.org/).

These days I use [Obsidian](https://obsidian.md/) to take notes and maintian my
personal knowledge base. After spending countless hours [shaving yaks](https://en.wiktionary.org/wiki/yak_shaving)
with my Emacs or [Vim configs](https://github.com/kraker/dotfiles/tree/master/nvim/.config/nvim)
I've realized that the text-editor you use to write and maintain your notes
isn't that important. It's the activity of taking notes that is. Obsidian gives
me most of what I need out of the box and it has a
[vim-mode](https://publish.obsidian.md/hub/04+-+Guides%2C+Workflows%2C+%26+Courses/for+Vim+users) 
so that I can still use modal editing which I like. It also has a mind-map
feature to visualize the links between notes which I think is pretty neat.

![](Screenshot_20231110_001607.png)

Since all of my notes are just a collection of Markdown files I can easily
port them to any text-editor or knowledge-base tool that supports that.
I can also easily back them up to the cloud as a 
[git repository](https://github.com/kraker/second-brain/tree/main) which has
the added benefit of making my notes version controlled. My
notes are portable and I own my data. Long-term I don't run the risk of losing
them if they're stuck in a proprietary platform like [Roam Research](https://roamresearch.com/),
for example. On long-enough time-scales most proprietary tools may not exist,
just look at the [Killed by Google](https://killedbygoogle.com/) for lots of
examples.

