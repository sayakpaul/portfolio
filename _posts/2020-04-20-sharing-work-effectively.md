---
title: "Sharing your work online effectively"
summary: A few tips on sharing your work online effectively. 
toc: false
comments: true
hide: false
search_exclude: false
author: Sayak Paul
categories: [blogs, sharing]
---

Well, you have put a lot of blood and sweat to write your latest blog post on Machine Learning. Don't let your struggle go in vein and let the world know about it. Sharing your blog posts across different channels not only gives you exposure but also may get you tremendous feedback on your work. In my personal experience, the feedback has been super useful for me to improve myself not only as a writer but also as a communicator. There can be times you might have missed out on a super important detail, you might have unknowingly introduced a snazzy bug in the code listings of your blog -- all those things could be caught in the process of feedback interchange. 

In this short article, I am going to enlist a few different ways to share about your work and get feedback. Note your work can be anything starting from a crucial GitHub PR to a weekend project. Although the following platforms/communities are mostly limited to Machine Learning I hope this guide would be useful for tech bloggers in general. 

## Sharing on platforms/communities

Before I start the sharing process, I generally create a Google Doc to effectively keep track of where I am sharing my work. This essentially acts as a checklist of all the places I would want to share my work on. Here's the template I follow for creating the Google Doc - 

- Link to where the work has been posted:
- Brief description of the work:
- Post table:
	| Platform/Community 	| URL of the post 	|
	|--------------------	|-----------------	|
	| --                 	| --              	|

I generally keep the description to a maximum of _280 characters_ so that I can use it on Twitter as well. 

Now, coming to the platforms/communities, here are the recommendations:
- HackerNews (https://news.ycombinator.com/newest)
- Made With ML (https://madewithml.com/)
- Reddit
    - [r/MachineLearning](https://www.reddit.com/r/MachineLearning/)
    - [r/MachinesLearn](https://www.reddit.com/r/MachinesLearn/)
    - [r/learnmachinelearning](https://www.reddit.com/r/learnmachinelearning/)
    - [r/deeplearning](https://www.reddit.com/r/deeplearning/)
- Twitter
- Facebook 
    - [AIDL](https://www.facebook.com/groups/DeepNetGroup/)
    - [Montreal AI](https://www.facebook.com/groups/MontrealAI/)
    - [Deep Learning](https://www.facebook.com/groups/DeepLearnng/)
- Fast.ai Forum (https://forums.fast.ai/)
- LinkedIn

While sharing about my work, I find it to be important to attach a brief description always. Additionally, if your work is related to implementing a research work, you should definitely include it on [Papers with Code](https://paperswithcode.com/). 

## Sharing to aid discussions

You might be an active person on online forums like Quora, StackOverflow, and so on. While participating in a discussion there you can make effective use of your work _if it is relevant_. In these cases, the approach is to not only just supply a link to your work but also first write about any important pointers relevant to the discussion first and then supply the link to your work to better aid it. Let's say there's a discussion going on _"What is Weight Initialization in Neural Nets?"_ Here's how I would approach my comment:

> A neural net can be viewed as a function with learnable parameters and those parameters are often referred to as weights and biases. Now, while starting the training of neural nets these parameters (typically the weights) are initialized in a number of different ways - sometimes, using contant values like 0’s and 1’s, sometimes with values sampled from some distribution (typically a unifrom distribution or normal distribution), sometimes with other sophisticated schemes like Xavier Initialization.
The performance of a neural net depends a lot on how its parameters are initialized when it is starting to train. Moreover, if we initialize it randomly for each runs, it’s bound to be non-reproducible (almost) and even not-so-performant too. On the other hand, if we initialize it with contant values, it might take it way too long to converge. With that, we also eliminate the beauty of randomness which in turn gives a neural net the power to reach a covergence quicker using gradient-based learning. We clearly need a better way to initialize it.
Careful initialization of weights helps us to develop in training them better. To know more, one can follow [this article of mine](https://www.wandb.com/articles/the-effects-of-weight-initialization-on-neural-nets). 

Well, that's it for this article. I hope it proves to be useful for you. I am thankful to [Alessio](https://www.linkedin.com/in/alessio-gozzoli-530aa2109/) of [FloydHub](https://www.floydhub.com/) for sharing these tips/ways with me. 
