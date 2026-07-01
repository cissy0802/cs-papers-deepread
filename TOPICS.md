# 论文清单 Papers Reading List（按引用量降序）

BigCat 人工维护的 IT / 计算机 / AI 里程碑论文清单，**按 Google Scholar 引用量从高到低排列**（编号 = 引用排名）。四方向：`[AI]` 深度学习、`[DS]` 分布式/数据库、`[SYS]` 系统/网络/安全、`[TH]` 理论/计算经典。

> **引用数是约数**（`≈`，取数量级，随时间漂移），仅用于排序参考，不必当精确值。
>
> **选题/编号规则**
> - routine 每次从清单**顶部往下**挑第一个「slug 还没做过」的（即优先做引用最高的还没做的那篇）。做没做看文件系统：`ls *-paper*.html`，按 slug 判断。
> - 文件名的 `paper{N}` 用**写作顺序**的下一个编号（现有最大 N + 1），**与本清单的引用排名解耦**——这样以后重排清单、或引用数变化，都不会打乱已发布文件。
> - 这份清单**人工策划、routine 只读不改**（`publish.sh` 硬卡 TOPICS.md 改动，防止机器自我生成）。清单做完就发 PushNotification 请 BigCat 续单、本次不发布。
> - 要加论文：插到合适的引用位置，或直接追加到末尾（排名不必时刻精确）。

- 1. `[AI]` **ResNet** — Deep Residual Learning for Image Recognition · He 等 (MSRA) · 2015 · ≈25 万 — 残差连接让网络能训到上百层，现代深网的基本构件（slug: `deep-residual-learning`）
- 2. `[AI]` **Adam** — Adam: A Method for Stochastic Optimization · Kingma & Ba · 2014 · ≈19 万 — 默认优化器，几乎每个深度模型都在用（slug: `adam-optimizer`）
- 3. `[AI]` **AlexNet** — ImageNet Classification with Deep Convolutional Neural Networks · Krizhevsky, Sutskever, Hinton · 2012 · ≈17 万 — 点燃深度学习革命的那一篇（slug: `alexnet`）
- 4. `[AI]` **Transformer** — Attention Is All You Need · Vaswani 等 (Google) · 2017 · ≈14 万 — 用纯注意力取代 RNN/CNN，当代大模型的地基（**已作为样例 paper1**，slug: `attention-is-all-you-need`）
- 5. `[AI]` **BERT** — Pre-training of Deep Bidirectional Transformers · Devlin 等 (Google) · 2018 · ≈11 万 — 双向预训练 + 微调范式，NLP 的分水岭（slug: `bert`）
- 6. `[TH]` **信息论** — A Mathematical Theory of Communication · Claude Shannon · 1948 · ≈10 万 — 信息论奠基，定义了「比特」与信道容量（slug: `mathematical-theory-of-communication`）
- 7. `[AI]` **GAN** — Generative Adversarial Networks · Goodfellow 等 · 2014 · ≈8 万 — 让两个网络对抗博弈来生成，生成式建模一大范式（slug: `generative-adversarial-networks`）
- 8. `[AI]` **Batch Normalization** — Ioffe & Szegedy (Google) · 2015 · ≈6 万 — 归一化中间激活，让深网训练更快更稳（slug: `batch-normalization`）
- 9. `[AI]` **Dropout** — A Simple Way to Prevent Neural Networks from Overfitting · Srivastava 等 · 2014 · ≈5 万 — 随机「关掉」神经元来正则化（slug: `dropout`）
- 10. `[AI]` **Word2Vec** — Efficient Estimation of Word Representations in Vector Space · Mikolov 等 (Google) · 2013 · ≈4.5 万 — 把词变成向量、语义可做算术，表示学习启蒙（slug: `word2vec`）
- 11. `[AI]` **GPT-3** — Language Models are Few-Shot Learners · Brown 等 (OpenAI) · 2020 · ≈4 万 — 规模化 + in-context learning，通向今天的对话大模型（slug: `gpt-3`）
- 12. `[SYS]` **RSA** — A Method for Obtaining Digital Signatures and Public-Key Cryptosystems · Rivest, Shamir, Adleman · 1978 · ≈3 万 — 第一个实用公钥体制（slug: `rsa`）
- 13. `[SYS]` **Bitcoin** — A Peer-to-Peer Electronic Cash System · Satoshi Nakamoto · 2008 · ≈3 万 — 用工作量证明解决无信任环境下的双花，区块链源头（slug: `bitcoin`）
- 14. `[SYS]` **公钥密码学** — New Directions in Cryptography · Diffie & Hellman · 1976 · ≈2.8 万 — 公钥密码学诞生，无需预共享密钥也能安全通信（slug: `new-directions-in-cryptography`）
- 15. `[SYS]` **PageRank** — The Anatomy of a Large-Scale Hypertextual Web Search Engine · Brin & Page · 1998 · ≈2.5 万 — PageRank，谷歌的起点（slug: `anatomy-of-a-search-engine`）
- 16. `[DS]` **MapReduce** — Simplified Data Processing on Large Clusters · Dean & Ghemawat (Google) · 2004 · ≈2.5 万 — 把大规模并行抽象成 map+reduce，开启大数据时代（slug: `map-reduce`）
- 17. `[TH]` **图灵测试** — Computing Machinery and Intelligence · Alan Turing · 1950 · ≈2.2 万 — 「机器能思考吗」与图灵测试，AI 的哲学起点（slug: `computing-machinery-and-intelligence`）
- 18. `[DS]` **Chord** — A Scalable Peer-to-peer Lookup Service · Stoica 等 (MIT) · 2001 · ≈1.8 万 — 分布式哈希表（DHT），P2P 查找经典（slug: `chord`）
- 19. `[AI]` **DQN** — Playing Atari with Deep Reinforcement Learning · Mnih 等 (DeepMind) · 2013 · ≈1.6 万 — 深度网络直接从像素学会玩游戏，深度强化学习开篇（slug: `dqn-atari`）
- 20. `[AI]` **AlphaGo** — Mastering the Game of Go with Deep Neural Networks and Tree Search · Silver 等 (DeepMind) · 2016 · ≈1.6 万 — 深度网络 + 蒙特卡洛树搜索击败围棋冠军（slug: `alphago`）
- 21. `[AI]` **Diffusion (DDPM)** — Denoising Diffusion Probabilistic Models · Ho 等 · 2020 · ≈1.6 万 — 扩散模型，当代图像/视频生成主力范式（slug: `ddpm`）
- 22. `[DS]` **关系模型** — A Relational Model of Data for Large Shared Data Banks · E. F. Codd · 1970 · ≈1.5 万 — 几乎所有现代数据库的理论根（slug: `relational-model`）
- 23. `[SYS]` **TCP 拥塞控制** — Congestion Avoidance and Control · Van Jacobson · 1988 · ≈1.3 万 — 让互联网没有在流量下崩溃（slug: `congestion-avoidance-and-control`）
- 24. `[TH]` **图灵机** — On Computable Numbers, with an Application to the Entscheidungsproblem · Alan Turing · 1936 · ≈1.1 万 — 图灵机与「可计算性」，计算理论的根（slug: `on-computable-numbers`）
- 25. `[TH]` **NP 完全性** — The Complexity of Theorem-Proving Procedures · Stephen Cook · 1971 · ≈9 千 — NP 完全性，P vs NP 问题的开端（slug: `complexity-of-theorem-proving`）
- 26. `[TH]` **信息隐藏** — On the Criteria To Be Used in Decomposing Systems into Modules · David Parnas · 1972 · ≈9 千 — 模块化与封装的思想源（slug: `decomposing-systems-into-modules`）
- 27. `[DS]` **Bigtable** — A Distributed Storage System for Structured Data · Chang 等 (Google) · 2006 · ≈9 千 — 稀疏多维有序宽表，列式存储先驱（slug: `bigtable`）
- 28. `[DS]` **GFS** — The Google File System · Ghemawat 等 (Google) · 2003 · ≈8 千 — 廉价机器 + 副本容错撑起 PB 级分布式存储（slug: `google-file-system`）
- 29. `[TH]` **超文本先知** — As We May Think · Vannevar Bush · 1945 · ≈8 千 — 预言了超链接与个人信息机器（slug: `as-we-may-think`）
- 30. `[SYS]` **端到端原则** — End-to-End Arguments in System Design · Saltzer, Reed, Clark · 1984 · ≈7 千 — 「功能该放在哪一层」，互联网架构的第一性原理（slug: `end-to-end-arguments`）
- 31. `[SYS]` **UNIX** — The UNIX Time-Sharing System · Ritchie & Thompson · 1974 · ≈6 千 — 定义现代操作系统哲学：一切皆文件、小工具组合（slug: `unix-time-sharing`）
- 32. `[DS]` **Paxos** — Paxos Made Simple · Lamport · 2001 · ≈6 千 — 分布式共识的奠基算法（的简化讲法）（slug: `paxos-made-simple`）
- 33. `[DS]` **Dynamo** — Amazon's Highly Available Key-value Store · DeCandia 等 (Amazon) · 2007 · ≈5 千 — 最终一致 + 一致性哈希 + 向量时钟，NoSQL 浪潮源头（slug: `dynamo`）
- 34. `[TH]` **没有银弹** — No Silver Bullet: Essence and Accident in Software Engineering · Fred Brooks · 1986 · ≈5 千 — 为什么软件复杂性没有银弹（slug: `no-silver-bullet`）
- 35. `[DS]` **Raft** — In Search of an Understandable Consensus Algorithm · Ongaro & Ousterhout · 2014 · ≈5 千 — 为「可理解」而设计的共识算法，工业界事实标准（slug: `raft`）
- 36. `[DS]` **Spanner** — Google's Globally-Distributed Database · Corbett 等 (Google) · 2012 · ≈3 千 — 用 TrueTime 实现全球尺度的外部一致性事务（slug: `spanner`）
- 37. `[TH]` **结构化编程** — Go To Statement Considered Harmful · Edsger Dijkstra · 1968 · ≈3 千 — 结构化编程宣言，一封信改变编程范式（slug: `goto-considered-harmful`）
- 38. `[SYS]` **信任的信任** — Reflections on Trusting Trust · Ken Thompson · 1984 · ≈2.5 千 — 「你能信任你没亲手写的代码吗」，最深刻的安全思想实验（slug: `reflections-on-trusting-trust`）
- 39. `[DS]` **尾延迟** — The Tail at Scale · Dean & Barroso (Google) · 2013 · ≈2.5 千 — 大规模系统里尾延迟为何致命、怎么治（slug: `tail-at-scale`）
- 40. `[DS]` **Kafka** — a Distributed Messaging System for Log Processing · Kreps 等 (LinkedIn) · 2011 · ≈2 千 — 以日志为中心的流处理与消息系统（slug: `kafka`）
- 41. `[TH]` **逻辑时钟** — Time, Clocks, and the Ordering of Events in a Distributed System · Lamport · 1978 · ≈1.5 万* — 逻辑时钟与 happens-before，分布式一致性的思想原点（*这篇其实引用极高，约 1.5 万；放这里方便与其它 Lamport 工作并读）（slug: `time-clocks-ordering`）
- 42. `[DS]` **拜占庭将军** — The Byzantine Generals Problem · Lamport, Shostak, Pease · 1982 · ≈1 万 — 有节点会说谎时如何达成一致，容错共识经典抽象（slug: `byzantine-generals`）
- 43. `[DS]` **CAP 雏形** — Harvest, Yield, and Scalable Tolerant Systems · Fox & Brewer · 1999 · ≈1.5 千 — CAP 定理的思想雏形，一致性与可用性的取舍（slug: `harvest-yield`）
- 44. `[DS]` **Dapper** — a Large-Scale Distributed Systems Tracing Infrastructure · Sigelman 等 (Google) · 2010 · ≈1.5 千 — 分布式追踪，现代可观测性的蓝本（slug: `dapper`）

> 注：#41/#42（Lamport 的逻辑时钟、拜占庭将军）引用其实很高，严格按数排应更靠前；此处稍作聚拢方便主题连读，若你要严格排名可把它们上移。
