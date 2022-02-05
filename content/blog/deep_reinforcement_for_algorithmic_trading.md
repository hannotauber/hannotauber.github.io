+++
title = "Deep reinforcement for algorithmic trading"
draft = true

date = 2022-02-05T00:00:00Z

[extra]
author = "Hanno Tauber, dmtrsflaco"

[taxonomies]
tags = ["ai","trading"]
+++

## AI

>To be more precise, [Pwnagotchi](https://pwnagotchi.ai/intro/) is using an [LSTM with MLP feature extractor](https://stable-baselines.readthedocs.io/en/master/modules/policies.html#stable_baselines.common.policies.MlpLstmPolicy) as its policy network for the [A2C agent](https://stable-baselines.readthedocs.io/en/master/modules/a2c.html). If you’re unfamiliar with A2C, here is a very good [introductory explanation](https://hackernoon.com/intuitive-rl-intro-to-advantage-actor-critic-a2c-4ff545978752) (in comic form!) of the basic principles behind how Pwnagotchi learns. Be sure to check out the Usage doc for more pragmatic details of how to help your Pwnagotchi learn as quickly as possible.

*A2C* A synchronous, deterministic variant of Asynchronous Advantage Actor Critic (A3C) . It uses multiple workers to avoid the use of a replay buffer.

[A3C Abstract](https://arxiv.org/pdf/1602.01783.pdf)
> We present asynchronous variants offour standard reinforcement learning algorithmsand show that parallel actor-learners have astabilizing effect on training allowing all four methods to successfully train neural network controllers. The best performing method, an asynchronous variant of actor-critic, surpasses the current state-of-the-art on the Atari domain while training for half the time on a single multi-core CPU instead of a GPU.

## Trading

### Research
- [Deep Reinforcement Learning for Automated Stock Trading](https://towardsdatascience.com/deep-reinforcement-learning-for-automated-stock-trading-f1dad0126a02). Using reinforcement learning to trade multiple stocks through Python and OpenAI Gym | Presented at ICAIF 2020. Columbia University [Whitepaper](https://deliverypdf.ssrn.com/delivery.php?ID=600090118106119102075091075107125069101037019087067074070003087094099127010082067124050026032061006034030081070116100067074119029029009051050010064014122016016077022046085012008125026126095113097072073014112085080109078107087116064086086124009004104064&EXT=pdf&INDEX=TRUE) [Github repository](https://github.com/Albert-Z-Guo/Deep-Reinforcement-Stock-Trading)
  - [References](https://github.com/Albert-Z-Guo/Deep-Reinforcement-Stock-Trading#references)
- [Deep Reinforcement Learning For Forex Trading (pages 4)](https://cs230.stanford.edu/projects_fall_2020/reports/55813822.pdf) Stanford 2020
- [Deep Learning Applying on Stock Trading (pages 6)](https://cs230.stanford.edu/projects_spring_2021/reports/74.pdf) Stanford 2021
- [Reinforcement Learning for FX trading](https://web.stanford.edu/class/msande448/2019/Final_reports/gr2.pdf) Stanford 2019


### Technology
- [ElegantRL “小雅”: Scalable and Elastic Deep Reinforcement Learning](https://github.com/AI4Finance-Foundation/ElegantRL). Columbia Univesrity 2020 research github is under same account.
- [FinRL: Deep Reinforcement Learning for Quantitative Finance](https://github.com/AI4Finance-Foundation/FinRL)

## AI4Finace
- [Youtube: FinRL: A Deep Reinforcement Learning Library for Automated Trading in Quantitative Finance](https://www.youtube.com/watch?v=ZSGJjtM-5jA)
