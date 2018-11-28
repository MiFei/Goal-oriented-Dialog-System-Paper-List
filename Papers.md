# Goal-oriented-Dialog-System --- Datasets/ Dialog State Tracking/ Policy/ Response Generation

## 1 Datasets

## 2 Dialog State Tracking

## 3 Policy & Dialog Management

### 1 Deep Reinforcement Learning

**[1]** Milica Gasic, C. Breslin, M. Henderson, D. Kim, M. Szummer, B. Thomson, P. Tsiakoulis and Steve Young 
**POMDP-based dialogue manager adaptation to extended domains**
SigDial 2013  **[GPRL]**   

**[2]** Milica Gasic and Steve Young. 
**Gaussian processes for pomdp-based dialogue manager optimization.**
IEEE/ACM Transactions on Audio, Speech, and Language Processing, 2014 **[GPRL]**

**[3]** Milica Gasic, Nikola Mrksic, Pei-Hao Su, David Vandyke, Tsung-Hsien Wen, and Steve Young.
**Policy committee for adaptation in multi-domain spoken dialogue systems.**
ASRU 2015 **[BCM]**

**[4]** Pei-Hao Su, Milica Gasic, Nikola Mrksic, Lina Rojas- Barahona, Stefan Ultes, David Vandyke, Tsung-Hsien Wen, and Steve Young.  
**Continuously learning neural dialogue management.**
arXiv 2016

**[5]** Pei-Hao Su, Paweł Budzianowski, Stefan Ultes, Milica Gasic, and Steve Young 
**Sample-efficient Actor-Critic Reinforcement Learning with Supervised Data for Dialogue Management**
SigDial 2017

**[6]** Pei-Hao Su, Milica Gasic, Nikola Mrksic, Lina Rojas-Barahona, Stefan Ultes, David Vandyke, Tsung-Hsien Wen, and Steve Young. 
**On-line active reward learning for policy optimisation in spoken dialogue systems.**
ACL 2016
1. The dialogue success is modeled using Gaussian Process
2. If the reward model is uncertain, user feedback is required; otherwise the predicted success rate is utilized.

**[7]** Bing Liu, Ian Lane
**Iterative Policy Learning in End-to-End Trainable Task-Oriented Neural Dialog Models**
ASRU 2017

**[8]** Baolin Peng, Xiujun Li, Jianfeng Gao, Jingjing Liu, Yun-Nung Chen, and Kam-Fai Wong. 
**Adversarial advantage actor-critic model for task-completion dialogue policy learning.** 
arXiv 2017.

**[9]** Bhuwan Dhingra, Lihong Li, Xiujun Li, Jianfeng Gao, Yun-Nung Chen, Faisal Ahmed, and Li Deng.
**Towards end-to-end reinforcement learning of dialogue agents for information access.**
ACL 2017

**[10]** Pararth Shah, Dilek Hakkani-Tur, Bing Liu, Gokhan Tur
**Bootstrapping a Neural Conversational Agent with Dialogue Self-Play, Crowdsourcing and On-Line Reinforcement Learning**
NAACL 2018

**[11]** Zachary Lipton, Xiujun Li, Jianfeng Gao, Lihong Li, Faisal Ahmed, Li Deng
**BBQ-Networks: Efficient Exploration in Deep Reinforcement Learning for Task-Oriented Dialogue Systems**
AAAI 2018
1. BBQ maintains an distribution q over the parameters to estimate their uncertainty. 
2. Use Thompson Sampling to select actions based on the probability distribution.

**[12]** Baolin Peng Xiujun Li Jianfeng Gao Jingjing Liu Kam-Fai Wong Shang-Yu Su
**Deep Dyna-Q: Integrating Planning for Task-Completion Dialogue Policy Learning**
ACL 2018 **[DDQ]**
1. Train the policy and simulator jointly
2. The “world model” is actually a simulator


**[13]** Shang-Yu Su Xiujun Li Jianfeng Gao Jingjing Liu Yun-Nung Chen
**D3Q: Robust Planning for Dialogue Policy Learning**
EMNLP 2018 **[D3Q]**
1. Applying a discriminator to identify whether an experience is from simulator or real user
2. In the simulation stage, repeat simulation until 𝐾 high quality experiences are collected


**[14]** Yuexin Wu, Xiujun Li, Jingjing Liu, Jianfeng Gao, Yiming Yang
**Switch-based Active Deep Dyna-Q: Efficient Adaptive Planning for Task-Completion Dialogue Policy Learning**
AAAI 2019 **[Switch-DDQ]**
1. Train a score function 𝑆𝑐𝑜𝑟𝑒() to measure the quality of simulated experience (Similar to the discriminator in D3Q)

2. Select the user goal based on validation accuracy (Goals with lower success rate are of higher priority)


**[15]** Kaixiang Mo, Shuangyin Li, Yu Zhang, Jiajun Li, Qiang Yang
**Personalizing a Dialogue System with Transfer Reinforcement Learning**
AAAI 2018
1. The dialogue policy of a user can be decomposed to a general and a user-specific policy.
2. Learning general policy from source data (large), and user-specific policy with target data (small).

**[16]** Vladimir Ilievski, Claudiu Musat, Andreea Hossmann, Michael Baeriswyl
**Goal-Oriented Chatbot Dialog Management Bootstrapping with Transfer Learning**
IJCAI 2018 **[done by my colleague]**
1. Similar domains share some common slots.
2. After training in target domain, the parameters of common slots can be copied to source model.
3. Experiment done on two domains (Restaurant and Movie)




### 2 Multi-domain/Composite-task Dialogues

**[1]** Milica Gasic, C. Breslin, M. Henderson, D. Kim, M. Szummer, B. Thomson, P. Tsiakoulis and Steve Young 
**POMDP-based dialogue manager adaptation to extended domains**
SigDial 2013 Best Paper 

**[2]** Milica Gasic, Nikola Mrksic, Pei-hao Su, David Vandyke, Tsung-Hsien Wen, and Steve Young
**Policy committee for adaptation in multi-domain spoken dialogue systems**
ASRU2015
1. Some policies are firstly trained on different datasets.
2. All policies recommend an action, which are then aggregated into a final action by the BCM policy.


**[3]** Zhuoran Wang, Yannis Stylianou, Tsung-Hsien Wen, Pei-Hao Su, Steve Young
**Learning Domain-Independent Dialogue Policies via Ontology Parameterisation**
SigDial 2015
1. 人工基于不同domain的ontology定义了 **很多很多** domain-invariant feature喂到policy的state表示里，文中叫Domain Independent Parametrisation (DIP)
2. 这篇是基于 **[1]** 的高斯过程POMDP， 后面 **[6,10]** 加入DeepRL，这类方法像是transfer learning

**[4]** Heriberto Cuayáhuitl, Seunghak Yu, Ashley Williamson, Jacob Carse
**Deep Reinforcement Learning for Multi-Domain Dialogue Systems**
NIPS 2016 RL workshop
1. model domain transition by a deterministic F, F is trained with MLP+SVM.
2. EMNLP2017’的HRL和这个思路相似，不过domain transition是通过top-level policy学得
3. 本文后面发在IJCNN2017 **[5]**

**[5]** Heriberto Cuayáhuitl, Seunghak Yu Ashley Williamson, Jacob Carse
**Scaling Up Deep Reinforcement Learning for Multi-Domain Dialogue Systems**
IJCNN 2017

**[6]** Alexandros Papangelis and Yannis Stylianou
**Single-Model Multi-domain Dialogue Management with Deep Learning**
IWSDS 2017
1. propose DIP **[3]** + DQN
2. 直接吧Deep Q Learning中的state换成了DIP表示，所以可以domain independent

**[7]** Alexandros Papangelis, Stefan Ultes and Yannis Stylianou
**Domain Complexity and Policy Learning in Task-Oriented Dialogue Systems**
IWSDS 2017

1. 比较最普通的GPRL和DQN在不同的domain的效率

**[8]** Baolin Peng, Xiujun Li, Lihong Li, Jianfeng Gao, Asli Celikyilmaz, Sungjin Lee, and Kam-Fai Wong. 
**Composite task-completion dialogue policy learning via hierarchical deep reinforcement learning.**
EMNLP 2017
1. 提出了temporal HRL to model temporal transition between subtasks. 优化DQN 定义了每个subtask的intrinsic reward，表示该子任务的完成度
2. 提到了slot constraints among subtasks的概念，并且通过在user simulation中加入constraints，让HRL去学。user simulation是FRAMES+Constraints

**[9]** Pawel Budzianowski, Stefan Ultes, Pei-Hao Su, Nikola Mrksic, Tsung-Hsien Wen, Inigo Casanueva, Lina Rojas-Barahona, and Milica Gasic.
**Sub-domain modelling for dialogue management with hierarchical reinforcement learning.** 
arXiv 2017

1. 和 **[8]** 类似，也是model HRL，但是Q function是用的 **[1]** 中的Gaussian Process去估计的。

**[10]** 
Inigo Casanueva, Paweł Budzianowski,Pei-Hao Su, Stefan Ultes, Lina Rojas-Barahona, Bo-Hsiang Tseng, and Milica Gasic
**Feudal Reinforcement Learning for Dialogue Management in Large Domains**
NAACL 2018
1. 本文基于DIP **[3]** 的domain-independent特征表示，提出Feudal RL。 其本质也是一种HRL，不过微软的HRL **[8]** 是基于定义好的temporal subtasks，本文只考虑是否和slot相关，不定义tasks. 先根据state选act_type, if it's slot-independent -> 跳Q^i else 跳Q^s 选<s,v>。所以微软的HRL是temporal，本文是spatial ！！！
2. information sharing mechanism between slots：Q^s policy的参数对不同的slot共享
3. 实验中的比了 **[6]** ， 证明FDQN比普通DNQ好，没比 **[8]**


## 2 Other Papers



