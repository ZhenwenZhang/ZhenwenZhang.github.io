---
title: "A Frustratingly Easy Approach for Joint Entity and Relation Extraction"
---

**作者**：Zexuan Zhong, Danqi Chen. Department of Computer Science, Princeton University

**论文下载地址**：[https://arxiv.org/pdf/2010.12812.pdf](https://arxiv.org/pdf/2010.12812.pdf)

**作者提出的问题**：端到端的关系抽取旨在识别命名实体并抽取实体之间的关系，大多数研究工作将其视为两个子任务，要么通过一种结构联合建模，要么通过共享表示的方式进行多任务学习。

**方法** In this work, we describe a very simple approach for joint entity and relation extraction, and establish the new state-of-the-art on standard benchmarks <font color='red'>(ACE04, ACE05, and SciERC)</font>. <font color='blue'>Our approach essentially builds on two independent pre-trained encoders and merely uses the entity model to provide input features for the relation model.</font> Through a series of careful examinations, we validate the importance of learning distinct contextual representations for entities and relations, fusing entity information at the input layer of the relation model, and incorporating global context. Finally, we also present an efficient approximation to our approach which requires only one pass of both encoders at inference time, obtaining a 8-16x speedup with a small accuracy drop.

**Why the pipeline approach performs so well?** 
(1) the contextual representations for the entity and relation models essentially capture distinct information, so sharing their representations hurts performance; 
(2) it is crucial to fuse the entity information (both boundary and type) at the input layer of the relation model;
(3) leveraging cross-sentence information is useful in both tasks; 
(4) stronger pre-trained language models can bring further gains. 

