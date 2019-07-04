---
layout: single
title:  "AlphaStar, DeepMind's new success story"
date:   2019-01-26 12:00:00 -0600
author_profile: true
excerpt_separator: "<!--more-->"
header:
  overlay_image: /images/paris.jpg
  overlay_filter: 0.5 # same as adding an opacity of 0.5 to a black background
---

**They did it!** DeepMind, the successful inventors of AlphaGo, the Go game AI that defeated the professional korean player Lee Sedol, just released a new amazing AI agent: AlphaStar, for the well-known strategy game Starcraft 2.

<!--more-->

As a huge fan of DeepMind for what they've achieved so far and an ex amateur player of the game, I followed these events meticulously, and I must say I got completely amazed by this "prototype" they just revealed on January 24th. The goal of this article is to give a simple yet decent analysis about what's the hype is all about. I might express subjectives ideas at some points but will try to be as objective as possible, feel free to let me know your opinion / comments about it.

# Brief introduction to Starcraft 2

One shall always start by definitions, Starcraft 2 is a RTS game (Real-Time Strategy game), created by Blizzard.
The goal of the game is pretty simple, collect resources, build units and destroy your opponent, simple as that. It includes three races that you can play, each got its different diverse units and mechanics, allowing the players to to create a huge variety of army compositions to defeat their enemy. The game has been published in 2010, and has been since then a really impressive game where players from all over the world have been competing and improving continuously over the years.

What's interesting about Starcraft 2 is that the game has always been pretty balanced regarding strategies, and never ever someone found one that would beat all the other. The mind set about the game, often called "meta", is constantly changing, thanks to the community and game's evolutions. For these reasons, in order to be a great player, not only you need to master a set of strategies, but also being able to understand what's your opponent is constantly doing or even thinking.

Starcraft 2 has also been known as the competitve game with the most actions per minute needed, also called APM (clicks and pressed keys). Current professional have an average of 400 APM and can reach up to 500/600 actions per minutes at key times of the game. This will be important later in the article.

{% capture fig_img %}
![Foo]({{ '/images/alphastar-apm.gif' | relative_url }})
{% endcapture %}

<figure>
  {{ fig_img | markdownify | remove: "<p>" | remove: "</p>" }}
  <figcaption>Starcraft 2 pro player APM.</figcaption>
</figure>

# Solving games to achieve AI Milestones

Let's get into it. If you are a fan of AI and never heard of DeepMind, you're missing out something. Founded in 2010 by top AI researchers on the planet, they dedicated themselves mainly on a promising field: Reinforcement Learning. As one of the leading companies regarding AI, they develop and apply state of the art methods to various domains including Medical Research or Speech Generation.

In the history of technology, key steps have been achieved by the invention of new machines, new mechanisms or molecules that scientists would discover. Nowadays, rules have changed a little bit, AI research's milestones are usually achieved thanks to AI agents winning over human players on games, more complicated each time. That might sound weird, but it is actually legit if you think about it.

Players develop strong problem solving skills when mastering the game. Every decision a human takes in a game (and even in his life) is itself the result of an algorithm, just like Yuval Noah Harari likes to mention in his book [Homo Deus](https://www.ynharari.com/book/homo-deus/). All the decisions we take come from the result of a decision-making process that runs inside our brain, aiming for a reward in a soon or further future.

In a simple game like chess, the entire possible actions set is quite limited as the board is relatively small, but in your everyday life, the number of actions you can take, is infinite.
By beating professional gamers using AI, researchers are developing complex algorithms, including neural network architectures, that are able to solve really complex decision-making related problems. The same algorithms can be sometimes directly used to solve real life issues like medical ones.


> **Demis Hassabis** (DeepMind CEO): "... While StarCraft is ‘just’ a (very complex!) game, I’m excited that the techniques behind #AlphaStar could be useful in other problems such as weather prediction & climate modeling, which also involve predictions over very long sequences. Peer-reviewed paper is underway.""

Some sceptic people might believe that these geniuses are wasting their time and energy on games and could tackle real world dramatic problems but they are mistaken. I like to say that AI scientists experiment on games just like neuroscientists experiment on rats.

By "Solving games" I mean creating an AI better than any human player. The first impressive AI agent that could beat pro players was [DeepBlue](https://en.wikipedia.org/wiki/Deep_Blue_(chess_computer)), a Chess AI that defeated Kasparov, the at-the-time world champion. DeepMind started with simple games, including [Atari Games](https://deepmind.com/research/publications/playing-atari-deep-reinforcement-learning/), the [Go Game](https://deepmind.com/research/alphago/) with the recent new ultimate version [AlphaGo Zero](https://deepmind.com/blog/alphago-zero-learning-scratch/), and now **Starcraft 2, known as one of the most difficult strategy game**
The order of these achievements really matters. Indeed, games that got 'solved' by AI became more and more complex. By complex we mean that the set of possible actions became wider and wider, making the search of the best move nearly impossible.
The number of possible boards in the chess game is not that huge. However, the number of possible boards in Go is insanely high. In Starcraft 2, the of possible states is hardly even computable. Indeed, the map, could be considered as a board where each cell would be a pixel where a unit could be standing, which makes it unfeasible to compute.

The other key difference between those previous games and Starcraft 2 is that the **information** a player get is different. For board games we say that the information type is **perfect**, meaning that at a given moment of the game, you have perfect information regarding what your opponent's action, you can always look at your opponent's side of the board. In Starcraft 2, information is most of the time **hidden**. By hidden we mean that both players cannot see what the other is doing unless their unit meet eachother, we also call it **imperfect** information. Card games are also considered as imperfect information games as you can't see your opponent's card.
As you lack knowledge about what your opponent is doing you must prepare yourselves for different potential outcomes and try to gather as much details about your oponent's strategy during the whole game in order to get the information that you are missing.

{% capture fig_img %}
![Foo]({{ '/images/alphastar-diff.png' | relative_url }})
{% endcapture %}

<figure>
  {{ fig_img | markdownify | remove: "<p>" | remove: "</p>" }}
  <figcaption>Complexity differences between Atari, Go and finally Stracraft 2. ©DeepMind</figcaption>
</figure>

That said, you will understand why solving the Go Game was harder than solving Chess Game, and why solving the Stracraft 2 game, is even harder. The gap of difficulty between these games is one of the main reason why AlphaStar has been such an hype and amazing bot.

# But how ?

Two years ago, Blizzard teamed up with DeepMind to create an alternative version of the game, in order to let whoever was interested to play with automation to play with Starcraft. They open sourced a set of python libraries and an enormous dataset of previously played games in order to be able to train model. That was the beginning of a long and exciting journe, many scientists got into it. By solving mini-games that Blizzard developed, the results after several months were promising but not excellent. The mini games were part of a typical Starcraft game but were far from being as complicated as an entire game. At that time the hype around the ability for AI to defeat Starcraft decreased quite significantly ... until recently, AlphaStar was born.
DeepMind has been working around this new agent that demands a lot of training and infrastructures that few companies in the world can achieve.

December 19th 2018, DeepMing invited Dario "TLO" Wünsch, a german pro player to play against their new AI they called AlphaStar. The human player got defeated 5 games to 0, which was pretty surprising. TLO claimed ahead to be confident about the match and all the DeepMind were obviously really happy about the performance they managed to reach.

From a given board, or state in the game, one must compute all the possible actions that it can take, then evaluate what would be the best action in order to win, in a close future, or in a longer term. A human player, when facing a situation that he experienced before, would use memory to recall what's the best action to avoid a loss, and to give himself, a chance to win the game.

# How good is it though ?

So far in this article, I've been glorifying DeepMind's engineers and they really deserve it, what they have done is once again breathtaking. However, unfortunately, some people have been pointing out some small imperfections (that some perfectionists would claim HUGE), that are  nevertheless worth mentioning ! I would try to put to good use my knowledge about the game and the different articles and analysis I read to explain the hecks

- WEIRD SIMPLE STRATEGY
- WEIRD APM
- NO PAPER. WAIT
- CRITICISM
- ANALYSIS OF THE GAMES. BEASTY QT
- CONCLUSION


More recently, DeepMind has been part the occidental trend: AI ethics. As many people, including AI researchers, got worried about the turn AI was taking in certain domains, many researchers and engineers dedicated their careers to use or develop AI in good ethical manners, that would help citizens' life in a non-lucratic way, rather shorting off jobs. This seems to be pretty promising for the next decades, we might see some potential huge changes in the way we think of AI, and particularly the way we want to deal with it in our everyday life.


- Official article from DeepMind: [https://deepmind.com/blog/alphastar-mastering-real-time-strategy-game-starcraft-ii/](https://deepmind.com/blog/alphastar-mastering-real-time-strategy-game-starcraft-ii/)
