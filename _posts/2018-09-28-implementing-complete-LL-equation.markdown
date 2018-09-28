
---
layout: post
title:  "Notes | Implementing complete Landau-Lifshitz equation into EPOCH"
date:   2018-09-28 15:50:01 +0800
categories: notes research
---

Recently, to answer the referee's questions, I implemented the complete LL
equation into `EPOCH`. Here I wanna talk about the issues I encountered in this
process.

At first, I was not sure how to implement the derivative of fields into particle
pusher. It turned out that it's super easy. All you need to do is to store the
fields felt by the particle from the last time step and calculate the deviation.

##### How to store the fields from the last time step?

This is the first problem I met. The particle pusher is called every step, so I
was stuck by how to get the previous field. At first, I define a plain variable
in particle pusher to store fields. However, when I calculate the deviation, the
variable is always 0 (cos it is initialized as 0). Jing suggested that I could add
an additional particle information and store it. Marvellous. In that way, I can
easily calc the difference of fields by letting current fields minus last fields
stored in the particle information.

##### Double free or corruption error.

Quite a dumb mistake. When I added an additional particle property, I forgot to
add to the counter of total properties.

##### Benchmark

I benchmarked my result with Vranic's, which is quite the same.

##### Underlying Problem

Howard suggested that time is not aligned in my method. I should get the
derivative of fields from updating fields module.

