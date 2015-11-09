---
layout: post
title: Is Git acquired taste?
comments: true
---

Ever since my team decided to move to Git I was involved in discussions on how to use Git. This included basic questions like "how do I check in" as well as
higher level questions like "how should we model code flow". My team is using Git for over a year now and I'm still running into folks that find Git complicated, cumbersome, and generally ugly. Where does all that resistance come from?

## I'm not a hacker

First let me start by saying I was never a Unix hacker. In fact, when I joined Microsoft five years ago I wasn't a command line aficionado either. I'm the kind of guy that really enjoys UI and will zoom in to fix off-by-one pixel errors.

However, I'm in love with Git ever since I moved switched from Mercurial about three years ago. The fact that so many folks I deeply respect and admire seem to think Git is complicated made me wonder why *I* like it. I don't think of myself as particularly clever. I already told you that I'm not a command line hacker (I still can't seem to remember the syntax of `findstr` for fuck's sake).

So I wonder what causes so much resistance that I've seen for Git.

## Why the strong dislike for Git?

A couple of days ago I had a thought. Maybe it's not that Git is hard, ugly, or complicated. Maybe it's a matter of first impression. I tweeted the following:

<blockquote class="twitter-tweet" lang="en"><p lang="en" dir="ltr">I&#39;ve come to believe that Git is an awesome tool for a single developer but acquired taste for a team environment.</p>&mdash; Immo Landwerth (@terrajobst) <a href="https://twitter.com/terrajobst/status/663222749188329473">November 8, 2015</a></blockquote> <script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

Many folks replied and pointed out that Git is an excellent tool for teams -- given that I really love Git it should not come as a surprise that I think so too.

I tried to say something different. When you learn Git as a tool to organize yourself your perspective is drastically different from when you learn Git to organize a team. Let's compare them.

## Git for individuals vs. Git for teams

Git was designed around automating the patch submission process the Linux kernel developers uses. [Linus wanted a system](https://www.youtube.com/watch?v=4XpnKHJAok8) where he gets exactly out what he put in. Once you have that mindset, it's obvious that you want your own repository that only *you* have access to and that all operations are based around a pull-based model.

In other words: you *pull* changes from people you trust rather than letting trusted people *push* to an agreed-upon sync point.

This model is so successful that it found wide adoption outside the Linux kernel. In fact, GitHub is "nothing more" *handwavymotion* than a web front end over Git and this process. GitHub provides a first class feature to allow people to *request* to pull their changes. This pull request feature is great because it combines code flow with code reviews.

Needless to say that the pull request process can even be used in cases where all participants are in fact allowed to push their changes directly to the centralized sync point. That's akin to ignore the guidance to conduct a code review before checking in (however, a kitten dies every time it's done).

In a centralized version control system (CVCS), such as SVN, TVFC, Perforce, you simply check in. The only thing you may do before is using whatever your code review tool is. That's it.

You may argue that I'm simplifying a lot in that CVCS isn't that easy either. You're correct. But folks *already* have those skills. Even worse, they are *ingrained* in most professional devs.

Trying to explain why they need to fork, clone, commit, push to origin, create PR from origin to upstream, squash, and merge, is an exercise in patience -- for both sides.

## Git is special

"But surely technology is always changing", you must think right now. That's true, but I believe Git is somewhat special in that it's the only version control tool that I know of that has a reputation of being excessively complicated.

Here are two popular examples:

1. [XKCD](http://xkcd.com/1597/)
2. [Fake man pages for Git](http://git-man-page-generator.lokaltog.net)

The fake man pages highlight how hideously complicated and absurd Git can appear to newcomers. Here is [an example](http://git-man-page-generator.lokaltog.net/#4ae83247df429db41968bc5618c22612):

> git-lick-archive — lick some non-filter-branched downstream archives next to a few diffed non-repacked local remotes

At this point, it should be clear that I believe one reason for this perception is that the workflows of distributed version control (DVCS) are simply different from the ones used in a CVCS, which are what most teams still use.

Another reason is the command line. The command line wasn't necessarily designed top-down but rather grown over time. It suffers from complex terminology and many inconsistencies of operations between different commands. Example? Sure:

```
git tag rm old-tag
```

Sigh. You just created a tag called `rm` that points to `old-tag`. Obviously.

## OK, what's your point?

If you read that far, you must wonder what exactly my point is. Hey, it's my blog. I get to rant all I want here. I'm under no obligation to provide a conclusion.

Nonetheless, I do have some thoughts on how to make folks more successful in learning Git:

* **Have a single centralized repo, no forks**. First of, I believe it's much easier to switch to Git from a CVCS if there is the one true copy. Yes, this means no forks. I can't count then number of times I had to explain the difference between origin and upstream to team members. Avoid that if you can.

* **Use the command line**. What? UI is much easier! I beg to differ. UI might make your workflows smoother but it doesn't help you to understand Git. Also, if you google a question, you're much more likely to find a command line based answer than a step-by-step recipe for the UI you happen to use. The command line also helps you to learn the official Git terminology -- many UI tools have their own lingo.

* **Watch a video on Git internals**. Seriously? I'm not going to use hex editor to check in. Riiiight. But understanding the basic way in which Git thinks helps you to predict what commands will do, how they behave, how to recover from mistakes, and what the limitations of Git are. An excellent video is [Git From the Bits Up](https://www.youtube.com/watch?v=MYP56QJpDr4).

* **Read a book on Git**. Come on, I didn't need to read a book on \<your current version control tool\>. That might be true, but you've a lot of experience in using it. The easiest way to jump start is by reading a short book on Git. Invest half an hour every night for about a week. The return on invest is huge. And if the book is well written, you might actually enjoy it. I really liked [Version Control By Example](http://www.amazon.com/dp/0983507902).

* **Give up and ask your local Git expert**. Don't laugh. We're social beings and we learn a lot by asking a coworker. However, in your own interest you shouldn't ask your expert every time you need to commit; but it's better to ask than to become horribly inefficient due to lack of understanding.

Happy hacking.
