---
updated: 2012-01-07
---

# Mercurial or Git?

**Recently I made the decision. When SVN started to go wonky after my update to Snow Leopard, I knew I had to switch to a DVCS, but I didn’t know which to use.**

Through my researching travels on the internet I quickly noticed that *all* the reviews other people wrote were old, usually a couple years old. The reviews also had one common theme through them all:

- Git is more complicated to use/learn and has more features;
- and Mercurial is simpler to use/learn and has less features.

But after much more researching and digging into the systems I realized this isn’t so much the case.

## Feature Comparison

I am not going to do a feature comparison here because there isn’t any reason to. **Mercurial and Git have the same features.** All the features are built in to Git, whereas Mercurial just requires extensions (often built in, but disabled by default).

My favourite comparative review is: [Git is MacGyver and Mercurial is James Bond](http://importantshock.wordpress.com/2008/08/07/git-vs-mercurial/).

### The Git Index

People either love it or hate and it is one of the major points of contention. People choose Git because of it. People choose Mercurial because it doesn’t have it. And that reason is enough for many people.

But the truth is Mercurial does have an extension that adds a very similar idea: Mercurial Queues. Though the implementation is different, the same idea is there.

I didn’t even know if this was a reason I would choose Git or not. Yes, I could see the benefit of being able to commit just a few files at a time but also I could see it being a little annoying having to constantly specify the files I wanted to commit.

### Local Branches

Another major difference between the two was Git’s local branches. In Git branches are only local (by default). In Mercurial branches aren’t local—of course there is an extension for local branches in Mercurial.

This wasn’t a major issue for me because I would be using the DVCS primarily for my own client projects, on my own development server. So it didn’t really matter whether the branches are local or not.

### Built in Python

I have been having a bit of a PHP crisis lately. I am outgrowing PHP and Python is looking pretty awesome. It is kinda weird, but I feel like Python is a perfect fit for the way I work, though I only know a little yet. So the fact that Mercurial is built in Python and can be imported and used natively in Python apps was a really compelling feature.

### Command Line Fu

Git is seen as requiring a lot of command line fu and Mercurial is always proud of its simple, intuitive command line interface. Though Git has gotten better/simpler in the more recent versions, there apparently are a few nagging, weird things. Since I am not super amazing at the command line yet (but trying hard), I could see this as a plus for Mercurial. One review I read mentioned that Git is like Linux (wow, that’s a creative comparison): requires a lot of configuration and Mercurial is like Mac: slick and simple to use, with hidden power.

## The Popular Kid in Town

Git is the popular kid in town right now. And people *love* it! Since Git’s popularity is so great, finding help for it should be easy because so many people are talking about/using it. I have always hated the popular kid and that makes me respect Mercurial a little more as the underdog.

## GitHub

[GitHub](https://github.com/) is awesome! And the guys behind it [really care](https://github.com/blog/). GitHub is a major plus for Git. Yes, [BitBucket](http://bitbucket.com/) exists, but lacks many of the social aspects that make GitHub what it is. Then I found [Hg-Git](http://hg-git.github.com/), a Mercurial plugin to allow Mercurial direct integration with Git (and GitHub)—made by the guys at GitHub. Hg-Git makes me respect the service GitHub offers even more. (Will you marry me GitHub? I love you.)

### The GitHub Community

Git has a massive community and recently I read a couple tweets that may, or may not have, influenced my decision.

Positive:

> “I’m loving the influx of new contributors to jQuery core since moving to Github.” —&nbsp;<cite>[@jereisig](http://twitter.com/jeresig/status/6387795184)</cite>

And negative:

> “Is github now a Single Point of Failure for the whole OSS ecosystem? I love it, but worry a bit.” —&nbsp;<cite>[@timbray](http://twitter.com/timbray/status/6411879609)</cite>

## So, What Did I Choose?

Well, it was a stressful decision and took me about two weeks after all my research to actually make the decision.

**And my decision was… Mercurial.**

I chose Mercurial for a couple reasons, *I think*. First I decided that since my command line abilities aren’t as strong as I would like, Mercurial seemed like the simpler choice. I also thought Git may be too complicated and have too many features for my first foray into the command line version control eco-system (previously, with SVN, I used a GUI). Since Mercurial has all the same features, I liked the idea that they were hidden until I was comfortable with the basic features and could unlock them as I needed them. A few other things that influenced my decision were Hg-Git, my support of underdogs and the whole Python thing.

After using if for almost a week I am, so far, happy with my decision. But I admit I have already run into a situation where Git Index would have been very useful.

---

## Updates

Two years after this post, I now switch back and forth between Git and Mercurial. I use both GitHub and BitBucket (BitBucket now supports Git). I’ve even got more proficient with the command line, but I still find Mercurial more user friendly.

**[I think this site sums the discussion up nicely.](http://gitvsmercurial.com/)**
