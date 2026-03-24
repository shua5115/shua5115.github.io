---
layout: post
title: Online NOU Game
tags: TIC
splash: /assets/NOU%20icon.png
summary: An online card game written in Java.
---

*Summer 2022 - Winter 2023*

![](/assets/NOU%20icon.png)

[Github Page](https://github.com/shua5115/OnlineNOU)

OnlineNOU is a game I started while working at TIC as a programming counselor in 2021, and finished in summer 2022.
It is inspired by UNO, featuring the ability to play with custom rulesets.
This game was my foray into networked games. It includes features like:
- Self-hosted servers over LAN
- Player moderation (kicking/banning)
- Cheating protection (players cannot cause an invalid server state or see other player's cards)

I combined what I learned from my previous games, [Plat3D]({% post_url 2021-07-01-Plat3D %}) and [PGolf]({% post_url 2021-07-20-PGolf %}),
for 3D graphics and UI.

Through the development process, I learned fundamental concepts of networking:
- TCP/IP protocol
- Client/server network architecture
- Data validation
- Cyber security

I also used my [MindMapper]({% post_url 2022-01-11-MindMapper %}) software to create a flowchart for the networking layer of the game:

![](/assets/uno%20game%20flowchart.png)