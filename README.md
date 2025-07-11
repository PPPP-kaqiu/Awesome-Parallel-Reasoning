<div align="center">

# Awesome-Parallel-Reasoning

[![License: MIT](https://img.shields.io/badge/License-MIT-purple.svg)](LICENSE)
[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

**Curated collection of papers and resources on unlocking the potential of test time scaling of reasoning in large language models**

</div>

## Overview

In recent years, the capabilities of Large Language Models (LLMs) have advanced at an unprecedented rate. This progress has been largely attributed to the scaling of model parameters, training data, and computational resources. At the same time, inference-time performance has been significantly improved by extending the computational "length" through methods like Chain-of-Thought, which enables models to formulate a reasoning process before delivering a final answer.

This raises a compelling question: beyond scaling the "depth" (model layers) and "length" (sequential reasoning), can we unlock new potential by introducing a "width" dimension to test-time computation? This collection explores this emerging frontier of **parallel reasoning**, which focuses on broadening the computational scope at inference time. Instead of pursuing a single line of thought, this paradigm involves generating and evaluating multiple, diverse reasoning paths or hypotheses in parallel. Conceptual examples can be seen in approaches where a model considers several hypotheses at once before proceeding, or in advanced multi-agent systems, like those explored by Gemini&Anthropic, where a lead agent coordinates multiple parallel agents to accomplish a goal.

The adoption of parallel reasoning offers a dual advantage. First, it significantly expands the effective computational budget for any given query, enhancing the robustness and quality of the final output. Second, it holds immense practical value by drastically reducing latency, a critical factor for improving user experience in real-world applications.

To systematically survey this exciting area, this collection curates key papers and resources, organized into the following categories:

1.  [**Foundational Techniques**](#premium): Papers on precursor methods that laid the groundwork for parallel reasoning by generating multiple independent samples, such as Self-Consistency and Tree-of-Thought (ToT).
2.  [**Parallel Reasoning Strategies**](#interactive-parallasim):
    * [**Interactive Parallelism**](#interactive-parallasim): Methods where multiple reasoning processes are generated simultaneously and can interact internally during inference.
    * [**Collaborative Agent Systems**](#agent-system): Frameworks that leverage multiple, coordinated agents to solve a single, complex task.
3.  [**Parallel Inference Acceleration**](#accelerate): Techniques designed to speed up decoding, such as speculative decoding and novel schemes for allocating computational resources for parallel generation.
4.  [**Infrastructure**](#infra): Frameworks and systems built to support and accelerate parallel reasoning at scale.
4.  [**Industry Applications**](#available): Showcases how parallel reasoning techniques are implemented in prominent products and systems.
<div>

</div>

## 📄 Papers
---
### Premium
#### Self-Consistency
[2203] [Self-Consistency Improves Chain of Thought Reasoning in Language Models](https://arxiv.org/pdf/2203.11171)  [Code 💻]()  
Xuezhi Wang, Jason Wei, Dale Schuurmans, Quoc Le, Ed H. Chi, Sharan Narang, Aakanksha Chowdhery, Denny Zhou

#### Adaptive Self-Consistency
[2305] [Let’s Sample Step by Step: Adaptive-Consistency for Efficient Reasoning and Coding with LLMs](https://arxiv.org/pdf/2305.11860)  [Code 💻](https://github.com/Pranjal2041/AdaptiveConsistency)  
Pranjal Aggarwal, Aman Madaan, Yiming Yang, Mausam

#### Soft Self-Consistency
[2402] [Soft Self-Consistency Improves Language Model Agents](https://arxiv.org/pdf/2402.13212)  [Code 💻](https://github.com/HanNight/soft_self_consistency)  
Han Wang*, Archiki Prasad*, Elias Stengel-Eskin*, Mohit Bansal

#### Tree of Thoughts
[2305] [Tree of Thoughts: Deliberate Problem Solving with Large Language Models](https://arxiv.org/pdf/2305.10601)  [Code 💻](https://github.com/princeton-nlp/tree-of-thought-llm)  
Shunyu Yao, Dian Yu, Jeffrey Zhao, Izhak Shafran, Thomas L. Griffiths, Yuan Cao, Karthik Narasimhan

#### Graph of Thoughts
[2308] [Graph of Thoughts: Solving Elaborate Problems with Large Language Models](https://arxiv.org/pdf/2203.11171)  [Code 💻](https://github.com/spcl/graph-of-thoughts)  
Maciej Besta1*, Nils Blach1*, Ales Kubicek, Robert Gerstenberger, Michał Podstawski, Lukas Gianinazzi, Joanna Gajda, Tomasz Lehmann, Hubert Niewiadomski, Piotr Nyczyk, Torsten Hoefler

---

### Interactive Parallasim
#### Leap
[2505] [Learning from Peers in Reasoning Models](https://arxiv.org/pdf/2505.07787)  [Code 💻](https://github.com/tongxuluo/LeaP)  
Tongxu Luo*, Wenyu Du*, Jiaxi Bi, Stephen Chung, Zhengyang Tang, Hao Yang, Min Zhang, Benyou Wang

#### Hogwild
[2504] [Hogwild! Inference: Parallel LLM Generation via Concurrent Attention](https://arxiv.org/pdf/2504.06261)  [Code 💻](https://github.com/eqimp/hogwild_llm)  
Gleb Rodionov†*, Roman Garipov*, Alina Shutova∗, George Yakushev∗, Erik Schultheis∗, Vage Egiazarian, Anton Sinitsin, Denis Kuznedelev, Dan Alistarh*

#### Adaptive Parallel Reasoning
[2504] [Learning Adaptive Parallel Reasoning with Language Models](https://arxiv.org/pdf/2504.15466)  [Code 💻](https://github.com/Parallel-Reasoning/APR)  
Jiayi Pan*, Xiuyu Li*, Long Lian*, Charlie Snell, Yifei Zhou, Adam Yala, Trevor Darrell, Kurt Keutzer, Alane Suhr

#### Multiverse
[2506] [Multiverse: Your Language Models Secretly Decide How to Parallelize and Merge Generation](https://arxiv.org/pdf/2506.09991)  [Code 💻](https://github.com/Multiverse4FM/Multiverse)  
Xinyu Yang*, Yuwei An*, Hongyi Liu, Tianqi Chen*, Beidi Chen

---

### Agent System
#### Anthropic Research System
[2506] [How we built our multi-agent research system](https://www.anthropic.com/engineering/built-multi-agent-research-system)  
Anthropic Team

#### SSA
[2506] [Learning to Reason Across Parallel Samples for LLM Reasoning](https://arxiv.org/pdf/2506.09014)
Jianing Qi, Xi Ye, Hao Tang, Zhigang Zhu, Eunsol Choi

#### RR-MP
[2501] [Enhancing LLM Reasoning with Multi-Path Collaborative Reactive and Reflection agents](https://arxiv.org/pdf/2501.00430)
Chengbo He, Bochao Zou, Xin Li, Jiansheng Chen, Junliang Xing, Huimin Ma

---

### Accelerate

#### SSR
[2505] [SSR: Speculative Parallel Scaling Reasoning in Test-time](https://arxiv.org/pdf/2505.15340)
Yuanlin, Bo WANG, Xiang LIU, Hong CHEN, Aiwei LIU, Xuming HU

#### SpecSearch
[2505] [Accelerating Large Language Model Reasoning via Speculative Search](https://arxiv.org/pdf/2505.02865)
Chengbo He, Bochao Zou, Xin Li, Jiansheng Chen, Junliang Xing, Huimin Ma, Zhihai Wang, Jie Wang, Jilai Pan, Xilin Xia, Huiling Zhen, Mingxuan Yuan, Jianye Hao, Feng Wu

#### CoSD
[2502] [Speculate, then Collaborate: Fusing Knowledge of Language Models during Decoding](https://arxiv.org/pdf/2502.08020)
Ziyao Wang, Muneeza Azmat, Ang Li, Raya Horesh, Mikhail Yurochkin

#### DoT
[2502] [Division-of-Thoughts: Harnessing Hybrid Language Model Synergy for Efficient On-Device Agents](https://arxiv.org/pdf/2502.04392)
Chenyang Shao, Xinyuan Hu, Yutang Lin, Fengli Xu*

---

### Infra

#### vLLM(PagedAttention)[Code 💻](https://github.com/vllm-project/vllm)  

#### SGLang(RadixAttention)[Code 💻](https://github.com/sgl-project/sglang)  

### Available

+ [Geimini deepthink](https://blog.google/technology/google-deepmind/google-gemini-updates-io-2025/)
+ [Claude4 parallel test-time compute](https://www.anthropic.com/news/claude-4)
+ [Seed thinking1.6 parallel decode](https://seed.bytedance.com/zh/seed1_6)
+ [Grok4 heavy](https://x.com/xai/status/1943158495588815072)