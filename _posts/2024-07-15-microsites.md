---
layout: post
title: Shutting down several *of.net sites
description: Why I decided to shutdown several of my .NET microsites
comments: true
---

If you follow me on social media you might know that I operate several
microsites to make my life as a product manager on the .NET team at Microsoft
easier.

I have decided to shut most of them down. In this post I'm going to explain
which sites are impacted and why I made that decision.

## Which sites are impacted?

Here is the list of sites I maintain and my plan for those:

| Site            | Plan                  |
| --------------- | --------------------- |
| [apireview.net] | Transfer to Microsoft |
| [apisof.net]    | Transfer to Microsoft |
| [designsof.net] | Shut down             |
| [issuesof.net]  | Shut down             |
| [sitesof.net]   | Shut down             |

## Why would you shut them down?

The short answer is compliance. Most of these sites were built at a time where
open source at Microsoft was new and our engagement with GitHub wasn't fully
fleshed out, both in terms of internal processes as well as in tooling.

This year marks our 10-year anniversary of open sourcing the .NET Core platform.
A lot has changed since then.

After talking with several people on my team about what the right model is I
realized that these sites need significant work in order to be sustainable. The
problem isn't the cost of cloud resources; the domains and Azure services are
reasonable cheap and/or free to me. The problem is the personnel cost of
ensuring the sites become and stay compliant with our policies.

For starters, having resources in my name is obviously not a good plan for
sustainability. Should I be hit by a meteor (or being blessed with winning the
lottery) the team needs to have the ability to continue operating these sites.
That requires transferring the assets to Microsoft and making sure the right
people have permissions. Once you do that, there is a need for compliance. There
are simple things like "ensure the web site is accessible" and more complicated
ones like "ensure all sites comply with EU policies".

One could argue that these sites are Immo's personal pet project, so who cares
whether they comply with Microsoft policies. The problem is that this doesn't
really hold once I advertise these sites on both social media as well as on
GitHub (which I have). I have also used my employer's time to work on these
sites, I had team mates file bugs and request features, and so on. It's very
hard to argue that these sites aren't fundamentally a .NET team asset. Just
continuing to operate them under my name to evade compliance rules would not be
responsible. Yes, following compliance rules isn't exactly the most attractive
thing, but as someone who is also on the hook for defining compliance rules, I'm
also keenly aware how necessary it is. Operating web sites (or online services
in general) isn't the same as running a desktop app; the risks and security
considerations are often much more nuanced.

Reasonable people have an expectation that these sites follow Microsoft's
operating standards, which I simply can't do unless the sites are tracked as
official assets.

At this point, you might understand the direction this going in. Having
Microsoft operate these sites isn't free or even cheap. In order to justify
the expense, the site must add significant value, not just be nice to have.

This brings us to this plan:

* **[apireview.net]**. This site is used to collect notes, publish them, and
  link the right time in the review video. This is an essential tool to design
  in the open. It's also an invaluable tool internally as it gives us high
  quality notes with minimal overhead. I consider this site mission critical for
  my job so I'm pushing for it to be transferred to Microsoft.

* **[apisof.net]**. This is our API catalog that lists all the places an API
  ships for. It's the source of truth for various tools to assist in porting to
  .NET Core. This makes the site mission critical, which is why the domain and
  Azure resources were transferred to Microsoft earlier this year already.

* **[designsof.net]**. This site is an index of all the designs hosted in the
  [dotnet/designs] repo. It's nice because it shows PRs as well as merged
  designs and also has full text search. However, it doesn't provide much value
  over the GitHub repo, except that having a domain and fast loading site is
  cool. As such, the value is too low to justify the operating cost. I'm going
  to shut it down.

* **[issuesof.net]**. This is quite helpful as it has a
  quick reference of all the issues and PRs across all the .NET orgs and repos.
  It also exposes some of our conventions for labelling, allowing team mates to
  search for issues that are relevant to them or their reports. However, we
  don't use it enough to justify the cost of operating it, despite it being very
  useful. While this is personally painful to me, I believe shutting this site
  down is the right call.

* **[sitesof.net]**. It's a static site hosted as GitHub pages that links the
  various microsites. This is in the realm of cool, but not useful enough to
  even spend money on the domain. Shutting this down is an easy call.

* **themesof.net**. You might remember this site from our planning efforts. We
  tried this for a few releases and concluded that using GitHub for high-level
  planning isn't the way we want to go, so we decided to stop using it. As such,
  I already shut it down earlier this year.

## Summary

I'm shutting down [issuesof.net], [designsof.net], and [sitesof.net]. The sites
[apisof.net] and [apireview.net] will be transferred to Microsoft.


[apireview.net]: https://apireview.net
[apisof.net]: https://apisof.net
[designsof.net]: https://designsof.net
[issuesof.net]: https://issuesof.net
[sitesof.net]: https://sitesof.net
[dotnet/designs]: https://github.com/dotnet/designs