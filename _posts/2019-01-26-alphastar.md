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

**They did it!** DeepMind, the successful inventors of AlphaGo, the AI that defeated the professional korean player Lee Sedol, just released a new amazing AI agent: AlphaStar, for the well-known strategy game Starcraft 2, created by Blizzard.
As a huge fan of DeepMind for what they've achieved so far and an ex amateur player of the game, I followed these events meticulously, and I must say I got completely amazed by this "prototype" they just revealed on January 24th.

<!--more-->

# Solving games to achieve AI Milestones

If you are a fan of AI and never heard of DeepMind, you're missing out something. Founded in 2010 by top AI researchers on the planet, they dedicated themselves mainly on a promising field, called Reinforcement Learning. They are one of the leader companies regarding AI, in various domains including Medical Research or Speech Generation.

In the history of technology, key steps have been achieved by the invention of new machines, new mechanisms or molecules that scientists would discover. Nowadays, rules have changed a little bit, AI research's milestones are usually achieved thanks to new AI agents winning over human players on games, more complicated each time. That might sound weird, but it is actually pretty legit if you think about it.
Players develop strong problem solving skills when mastering the game. Every decision a human takes in a game (and even in his life) is itself the result of an algorithm, just like Yuval Noah Harari likes to mention in his book [Homo Deus](https://www.ynharari.com/book/homo-deus/). All the decisions we take come from the result of a decision-making process that runs inside our brain. In a simple game like chess, the entire possible actions is quite limited as the board is relatively small, but in your everyday life, the number of actions you can take, is infinite.

By "Solving games" I mean making an AI better than any human player. The first impressive AI agent that could beat pro players was [DeepBlue](https://en.wikipedia.org/wiki/Deep_Blue_(chess_computer)), a Chess AI that defeated Kasparov, the at-the-time world champion. DeepMind started with simple games, including [Atari Games](https://deepmind.com/research/publications/playing-atari-deep-reinforcement-learning/), the [Go Game](https://deepmind.com/research/alphago/) with the recent new ultimate version [AlphaGo Zero](https://deepmind.com/blog/alphago-zero-learning-scratch/), and now **Starcraft 2, known as one of the most difficult strategy game**
The order of these developments is really important. Indeed, games that got 'solved' by AI became more and more complex. By complex we mean that the set of possible actions became wider and wider, making the search of the best move nearly impossible.
The number of possible boards in the chess game is not that huge. However, the number of possible boards in Go is insanely high. In Starcraft 2, the of possible states is hardly even computable. Indeed, the map, could be considered as a board where each cell would be a pixel where a unit could be standing, which makes it unfeasible to compute.

The other key difference between those previous games and Starcraft 2 is that the information a player get is different. For board games we call the information type **perfect**, meaning that at a given state, you have perfect information regarding what your opponent is doing, you can always look at your opponent's side of the board right. In Starcraft 2, information is most of the time hidden.  

{% capture fig_img %}
![Foo]({{ '/images/alphastar-diff.png' | relative_url }})
{% endcapture %}

<figure>
  {{ fig_img | markdownify | remove: "<p>" | remove: "</p>" }}
  <figcaption>Complexity differences between Atari, Go and finally Stracraft 2.</figcaption>
</figure>

That said, you will understand why solving the Go Game was harder than solving Chess Game, and why solving the Stracraft 2 game, is even harder.

# But how ?

All these games have been solved using tree search method.
From a given board, or state in the game, one must compute all the possible actions that it can take, then evaluate what would be the best action in order to win, in a close future, or in a longer term. A human player, when facing a situation that he experienced before, would use memory to recall what's the best action to avoid a loss, and to give himself, a chance to win the game.

# How good is it though ?

{% capture fig_img %}
![Foo]({{ '/images/alphastar-apm.gif' | relative_url }})
{% endcapture %}

<figure>
  {{ fig_img | markdownify | remove: "<p>" | remove: "</p>" }}
  <figcaption>Starcraft 2 pro player APM.</figcaption>
</figure>



More recently, DeepMind has been part the occidental trend: AI ethics. As many people, including AI researchers, got worried about the turn AI was taking in certain domains, many researchers and engineers dedicated their careers to use or develop AI in good ethical manners, that would help citizens' life in a non-lucratic way, rather shorting off jobs. This seems to be pretty promising for the next decades, we might see some potential huge changes in the way we think of AI, and particularly the way we want to deal with it in our everyday life.


- Official article from DeepMind: [https://deepmind.com/blog/alphastar-mastering-real-time-strategy-game-starcraft-ii/](https://deepmind.com/blog/alphastar-mastering-real-time-strategy-game-starcraft-ii/)
