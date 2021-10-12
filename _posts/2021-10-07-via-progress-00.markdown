---
layout: post
title:  "VIA progress #0"
date:   2021-10-07 15:55:32 +0200
categories: VIA
---

Hello everyone!

I'm writing this blog post and more coming in the next few weeks to document my progress in
the "Vývoj internetových aplikací (VIA)", or "Web application development", course at the Faculty
of Electrical Engineering at the Czech Technical University.

### Choosing a topic

The main task of the course is to create a web app of our choosing. There are only a few requirements
1. We must use three or more APIs
2. Two must be publicly accessible, one must be our own making
3. We must use an application server
4. We must provide [Swagger](https://swagger.io/) documentation for our API
5. We must provide a link to our app here

I was not sure what kind of app I would like to make, but I really wanted to use some 
of the [Golemio](https://golemio.cz/) APIs. They are quite limited as of the time of writing, but
I wanted my focus to be on Prague, and they are easily accessible.

After not being able to figure out anything for a week, I finally had an idea the day of the deadline.
I sincerely apologise to our tutor for this, since I was not able to confirm the topic with him.
Hopefully, he'll forgive me, and it'll turn out alright.

The topic I've chosen is __Public transport racing bets__.

What does that mean?

The idea is to create a sort of game. Using the real time public transport locations, we can detect
whenever two vehicles are due to arrive at a station at the same time. If there are any users online,
we can offer them to place a bet on which one will arrive at its destination sooner. If we want to get
really creative, we can offer different odds based on what other people are betting and on historical
data. Each user starts with some amount of coins, which they then acquire more if they bet correctly
and lose if they bet incorrectly. Most importantly, if they are very good at predicting the outcomes,
they get to have bragging rights. Of course, there also needs to be a way to get more coins if you lose
everything.

Is this idea silly? Yes! Is it going to be fun to do? I hope so! And if not, well, it at least
fulfills the requirements.

### Technical implementation

I have not fully committed on what kind of tech stack I should be using. I would prefer to work
mostly in TypeScript, so I think node.js server with express and with React frontend would be the
safest choice. I don't have any experience with React yet, but we are here to learn.

In terms of APIs, one is going to be the public transport locations from
[Golemio](https://golemioapi.docs.apiary.io/#reference/public-transport/realtime-vehicle-positions)
and we're going to need some kind of map API. I'll choose one when I get to that point.

For our own API, we're going to need to send message back and forth between the client and the server.
The client wants to receive a possible bet as soon as it is available. The client then wants to send
the amount of coins and the vehicle it is betting on. They also want to get notifications immediately once
they win or lose. The client data also needs to be persistent, stored safely in a database.

I believe this is enough of the specifications for now. I'll return next week, maybe even with mockups! We'll see.
