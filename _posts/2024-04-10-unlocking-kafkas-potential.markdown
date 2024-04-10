---
layout: post
title:  "Unlocking Kafka's Potential: Tackling Tail Latency with eBPF"
date:   2024-04-10 20:00:00 +0100
categories: [performance]
---

In March, together with my colleague Piotr Rżysko we have published an article about Kafka performance analysis
using eBPF: [https://blog.allegro.tech/2024/03/kafka-performance-analysis.html](https://blog.allegro.tech/2024/03/kafka-performance-analysis.html).

I won't be going into technical details here (I encourage you read the original piece) instead I would like to offer 
some random thoughts around it:

- I think that [Brendan Gregg's System Performance](https://www.brendangregg.com/blog/2020-07-15/systems-performance-2nd-edition.html)
  is truly one of the most inspiring and valuable CS books I have read. I have first learned about eBPF from it and it provides a lot of
  performance tuning methodologies and does a solid job at explaining key OS concepts. For me it is one of 2 books from the last ~5 years that I would recommend
  every Software Engineer to read (the other one would be [Martin Kleppmann's Desining Data Intensive Applications](https://learning.oreilly.com/library/view/designing-data-intensive-applications/9781491903063/)).
- I've seen a couple of comments saying that the whole analysis was pointless because Kafka docs are explicitly saying
that XFS may be a better choice - we could have simply tried XFS first! I'd argue that such an approach is a variant of `Streetlight Anti-Method` described by Brendan Gregg (i.e. looking for the keys not were you lost them but where the light is best). 
Sure, trying random options known without measuring performance and analysing the root cause may work. But you can also end up spending days tweaking 
random permutations of different parameters hoping to find the right one.
- Solving problems together is a great way to learn and make progress. This ma be an obvious one but 
it always fascinates me how effective working in a pair is.
