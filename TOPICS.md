# 论文清单 Papers Reading List

BigCat 人工维护的「值得逐篇精读」的 IT / 计算机 / AI 里程碑论文清单。routine 每次挑**编号最小、还没做过**的一篇（做没做看文件系统 `ls *-paper*.html`），写一篇单篇深读。

> **维护规则**
> - 这份清单是**人工策划**的，routine **只读不改**（`publish.sh` 会硬卡 TOPICS.md 改动——防止机器自我生成、滑向同质化）。
> - 清单做完了：routine 发 PushNotification 请 BigCat 续单，本次不发布。
> - 要加论文：在末尾按序号追加 `N: 标题 — 作者/团队 · 年份 — 一行『为什么值得精读』`。
> - 选题偏好：**改变了一个领域、且单篇就有厚度**的论文；分布式系统 / 数据库、AI / 深度学习、系统 / 网络 / 安全、理论 / 计算经典四条线兼顾，经典与当代并存。

## 分布式系统 / 数据库
- 1: Attention Is All You Need — Vaswani 等 (Google) · 2017 — 提出 Transformer，用纯注意力取代 RNN/CNN，是当代大模型的地基（**已作为样例 paper1**）
- 2: MapReduce: Simplified Data Processing on Large Clusters — Dean & Ghemawat (Google) · 2004 — 把「大规模并行」抽象成 map+reduce 两个函数，开启大数据时代
- 3: The Google File System — Ghemawat 等 (Google) · 2003 — 用廉价机器 + 副本容错，撑起 PB 级分布式存储
- 4: Time, Clocks, and the Ordering of Events in a Distributed System — Lamport · 1978 — 逻辑时钟与「happens-before」，分布式一致性的思想原点
- 5: The Byzantine Generals Problem — Lamport, Shostak, Pease · 1982 — 有节点会「说谎」时如何达成一致，容错共识的经典抽象
- 6: Paxos Made Simple — Lamport · 2001 — 分布式共识的奠基算法（的「简化」讲法）
- 7: In Search of an Understandable Consensus Algorithm (Raft) — Ongaro & Ousterhout · 2014 — 为「可理解」而设计的共识算法，工业界共识事实标准
- 8: Dynamo: Amazon's Highly Available Key-value Store — DeCandia 等 (Amazon) · 2007 — 最终一致、一致性哈希、向量时钟，NoSQL 浪潮的源头
- 9: Bigtable: A Distributed Storage System for Structured Data — Chang 等 (Google) · 2006 — 稀疏、多维、有序的宽表模型，列式存储的先驱
- 10: Spanner: Google's Globally-Distributed Database — Corbett 等 (Google) · 2012 — 用 TrueTime（原子钟 + GPS）实现全球尺度的外部一致性事务
- 11: A Relational Model of Data for Large Shared Data Banks — E. F. Codd · 1970 — 关系模型，几乎所有现代数据库的理论根
- 12: The Tail at Scale — Dean & Barroso (Google) · 2013 — 大规模系统里「尾延迟」为何致命、怎么治

## AI / 深度学习
- 13: ImageNet Classification with Deep Convolutional Neural Networks (AlexNet) — Krizhevsky, Sutskever, Hinton · 2012 — 点燃深度学习革命的那一篇
- 14: Deep Residual Learning for Image Recognition (ResNet) — He 等 (MSRA) · 2015 — 残差连接让网络能训到上百层，现代深网的基本构件
- 15: BERT: Pre-training of Deep Bidirectional Transformers — Devlin 等 (Google) · 2018 — 双向预训练 + 微调范式，NLP 的分水岭
- 16: Language Models are Few-Shot Learners (GPT-3) — Brown 等 (OpenAI) · 2020 — 规模化 + in-context learning，通向今天的对话大模型
- 17: Generative Adversarial Networks — Goodfellow 等 · 2014 — 让两个网络对抗博弈来生成，生成式建模的一大范式
- 18: Efficient Estimation of Word Representations in Vector Space (Word2Vec) — Mikolov 等 (Google) · 2013 — 把词变成向量、语义可做算术，表示学习的启蒙
- 19: Mastering the Game of Go with Deep Neural Networks and Tree Search (AlphaGo) — Silver 等 (DeepMind) · 2016 — 深度网络 + 蒙特卡洛树搜索，击败围棋世界冠军
- 20: Adam: A Method for Stochastic Optimization — Kingma & Ba · 2014 — 默认优化器，几乎每个深度模型都在用
- 21: Playing Atari with Deep Reinforcement Learning (DQN) — Mnih 等 (DeepMind) · 2013 — 深度网络直接从像素学会玩游戏，深度强化学习开篇
- 22: Batch Normalization — Ioffe & Szegedy (Google) · 2015 — 归一化中间激活，让深网训练更快更稳
- 23: Dropout: A Simple Way to Prevent Neural Networks from Overfitting — Srivastava 等 · 2014 — 随机「关掉」神经元来正则化
- 24: Denoising Diffusion Probabilistic Models (DDPM) — Ho 等 · 2020 — 扩散模型，当代图像 / 视频生成的主力范式

## 系统 / 网络 / 安全
- 25: The UNIX Time-Sharing System — Ritchie & Thompson (Bell Labs) · 1974 — 定义了现代操作系统的哲学：一切皆文件、小工具组合
- 26: End-to-End Arguments in System Design — Saltzer, Reed, Clark · 1984 — 「功能该放在哪一层」——互联网架构的第一性原理
- 27: Congestion Avoidance and Control — Van Jacobson · 1988 — TCP 拥塞控制，让互联网没有在流量下崩溃
- 28: Bitcoin: A Peer-to-Peer Electronic Cash System — Satoshi Nakamoto · 2008 — 用工作量证明解决无信任环境下的双花，区块链源头
- 29: Reflections on Trusting Trust — Ken Thompson · 1984 — 「你能信任你没亲手写的代码吗」——最深刻的安全思想实验
- 30: The Anatomy of a Large-Scale Hypertextual Web Search Engine — Brin & Page (Stanford) · 1998 — PageRank，谷歌的起点
- 31: New Directions in Cryptography — Diffie & Hellman · 1976 — 公钥密码学的诞生，无需预共享密钥也能安全通信
- 32: A Method for Obtaining Digital Signatures and Public-Key Cryptosystems (RSA) — Rivest, Shamir, Adleman · 1978 — 第一个实用公钥体制

## 理论 / 计算经典
- 33: A Mathematical Theory of Communication — Claude Shannon · 1948 — 信息论奠基，定义了「比特」与信道容量
- 34: Computing Machinery and Intelligence — Alan Turing · 1950 — 「机器能思考吗」与图灵测试，AI 的哲学起点
- 35: On Computable Numbers, with an Application to the Entscheidungsproblem — Alan Turing · 1936 — 图灵机与「可计算性」，计算理论的根
- 36: Go To Statement Considered Harmful — Edsger Dijkstra · 1968 — 结构化编程宣言，一封信改变了编程范式
- 37: On the Criteria To Be Used in Decomposing Systems into Modules — David Parnas · 1972 — 「信息隐藏」，模块化与封装的思想源
- 38: No Silver Bullet: Essence and Accident in Software Engineering — Fred Brooks · 1986 — 为什么软件复杂性没有银弹
- 39: As We May Think — Vannevar Bush · 1945 — 预言了超链接与个人信息机器，信息时代的先知文
- 40: The Complexity of Theorem-Proving Procedures — Stephen Cook · 1971 — NP 完全性，P vs NP 问题的开端

## 补充（分布式续）
- 41: Kafka: a Distributed Messaging System for Log Processing — Kreps 等 (LinkedIn) · 2011 — 以「日志」为中心的流处理与消息系统
- 42: Chord: A Scalable Peer-to-peer Lookup Service — Stoica 等 (MIT) · 2001 — 分布式哈希表（DHT），P2P 查找的经典
- 43: Harvest, Yield, and Scalable Tolerant Systems — Fox & Brewer · 1999 — CAP 定理的思想雏形，一致性与可用性的取舍
- 44: Dapper, a Large-Scale Distributed Systems Tracing Infrastructure — Sigelman 等 (Google) · 2010 — 分布式追踪，现代可观测性的蓝本
