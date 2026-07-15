# 论文清单 Papers Reading List（按重要性 + 主题聚类）

BigCat 人工维护的 IT / 计算机 / AI 里程碑论文清单。**按重要性排列、并把高度相关的论文聚在一起**（如 Google 分布式系统三件套、Lamport 共识系、计算理论基石各自成簇），方便一个主题连着读透。

> **选题 / 编号规则**
> - routine 每次从清单**顶部往下**挑第一个「slug 还没做过」的（做没做看 `ls *-paper*.html`，按 slug 判断）。聚类顺序即优先级，从上往下做即可。
> - 文件名 `paper{N}` 的 **N 用写作顺序的下一个编号**（现有最大 N + 1），**与本清单顺序解耦**——重排清单不会打乱已发布文件。
> - 这份清单**人工策划、routine 只读不改**（`publish.sh` 硬卡 TOPICS.md 改动）。做完就发 PushNotification 请 BigCat 续单、本次不发布。
> - 要加论文：插到最贴切的主题簇里，别只往末尾堆——保持「相关的在一起」。

## 深度学习 / 现代 AI
- **Transformer** — Attention Is All You Need · Vaswani 等 (Google) · 2017 — 用纯注意力取代 RNN/CNN，当代大模型的地基（**已作为样例 paper1**，slug: `attention-is-all-you-need`）
- **AlexNet** — ImageNet Classification with Deep CNNs · Krizhevsky, Sutskever, Hinton · 2012 — 点燃深度学习革命的那一篇（slug: `alexnet`）
- **ResNet** — Deep Residual Learning for Image Recognition · He 等 (MSRA) · 2015 — 残差连接让网络能训到上百层，现代深网基本构件（slug: `deep-residual-learning`）
- **ViT** — An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale · Dosovitskiy 等 (Google) · 2020 — 把图切成 patch 喂 Transformer，视觉从 CNN 换代到注意力（slug: `vision-transformer`）
- **CLIP** — Learning Transferable Visual Models From Natural Language Supervision · Radford 等 (OpenAI) · 2021 — 图文对比预训练打通视觉与语言，zero-shot 分类与多模态大模型的地基（slug: `clip`）
- **Word2Vec** — Efficient Estimation of Word Representations · Mikolov 等 (Google) · 2013 — 把词变成向量、语义可做算术，表示学习启蒙（slug: `word2vec`）
- **LSTM** — Long Short-Term Memory · Hochreiter & Schmidhuber · 1997 — 门控机制解梯度消失，Transformer 之前统治序列建模二十年的那个答案（slug: `lstm`）
- **Seq2Seq** — Sequence to Sequence Learning with Neural Networks · Sutskever 等 (Google) · 2014 — encoder-decoder 端到端学序列映射，机器翻译范式转折（slug: `seq2seq`）
- **Bahdanau Attention** — Neural Machine Translation by Jointly Learning to Align and Translate · Bahdanau 等 · 2014 — 注意力机制的起点，三年后长成 Transformer（slug: `bahdanau-attention`）
- **BERT** — Pre-training of Deep Bidirectional Transformers · Devlin 等 (Google) · 2018 — 双向预训练 + 微调范式，NLP 分水岭（slug: `bert`）
- **GPT-3** — Language Models are Few-Shot Learners · Brown 等 (OpenAI) · 2020 — 规模化 + in-context learning，通向对话大模型（slug: `gpt-3`）
- **Scaling Laws** — Scaling Laws for Neural Language Models · Kaplan 等 (OpenAI) · 2020 — 损失随规模幂律下降，"大就是好"的定量依据；与 Chinchilla (Hoffmann 等 · 2022) 的数据-参数最优配比修正对读（slug: `scaling-laws`）
- **Emergent Abilities** — Emergent Abilities of Large Language Models · Wei 等 (Google) · 2022 — 能力随规模"涌现"的观察与争议（与 Stanford "mirage" 反方对读），理解大模型评估的关键辩论（slug: `emergent-abilities`）
- **InstructGPT (RLHF)** — Training Language Models to Follow Instructions with Human Feedback · Ouyang 等 (OpenAI) · 2022 — SFT + 奖励模型 + PPO 三步，把补全模型变成对话助手的那篇（slug: `instructgpt-rlhf`）
- **Constitutional AI** — Constitutional AI: Harmlessness from AI Feedback · Bai 等 (Anthropic) · 2022 — 用一部「宪法」让 AI 自我批评替代人工无害标注（RLAIF），对齐的另一条路线（slug: `constitutional-ai`）
- **GAN** — Generative Adversarial Networks · Goodfellow 等 · 2014 — 两个网络对抗博弈来生成，生成式建模一大范式（slug: `generative-adversarial-networks`）

## Google 分布式系统（老三件套 · 新三驾马车 · 演进）
- **GFS** — The Google File System · Ghemawat 等 · 2003 — 廉价机器 + 副本容错撑起 PB 级分布式存储（老三件套之一，slug: `google-file-system`）
- **MapReduce** — Simplified Data Processing on Large Clusters · Dean & Ghemawat · 2004 — 把大规模并行抽象成 map+reduce，开启大数据时代（老三件套之一，slug: `map-reduce`）
- **Bigtable** — A Distributed Storage System for Structured Data · Chang 等 · 2006 — 稀疏多维有序宽表，列式存储先驱（老三件套之一，slug: `bigtable`）
- **Chubby** — The Chubby Lock Service for Loosely-Coupled Distributed Systems · Burrows · 2006 — 把 Paxos 落地成分布式锁与协调服务，GFS / Bigtable 都靠它选主与元数据一致（slug: `chubby`）
- **Percolator (Caffeine)** — Large-scale Incremental Processing Using Distributed Transactions and Notifications · Peng & Dabek · 2010 — 给 Bigtable 加跨行事务 + 通知，把批量重建索引变成增量更新，支撑 Caffeine 实时收录（新三驾马车之一，slug: `percolator`）
- **Pregel** — A System for Large-Scale Graph Processing · Malewicz 等 · 2010 — 「像顶点一样思考」的 BSP 图计算模型，PageRank 类大规模图算法的分布式框架（新三驾马车之一，slug: `pregel`）
- **Dremel** — Interactive Analysis of Web-Scale Datasets · Melnik 等 · 2010 — 列式存储 + 多级执行树，秒级交互式查询万亿行，BigQuery 的底子（新三驾马车之一，slug: `dremel`）
- **Spanner** — Google's Globally-Distributed Database · Corbett 等 · 2012 — 用 TrueTime 实现全球尺度的外部一致性事务（slug: `spanner`）
- **F1** — F1: A Distributed SQL Database That Scales · Shute 等 · 2013 — 建在 Spanner 之上的分布式 SQL 层，兼顾强一致与 SQL 生态（slug: `f1-distributed-sql`）
- **Dapper** — Large-Scale Distributed Systems Tracing · Sigelman 等 · 2010 — 分布式追踪，现代可观测性蓝本（slug: `dapper`）
- **The Tail at Scale** — Dean & Barroso · 2013 — 大规模系统里尾延迟为何致命、怎么治（slug: `tail-at-scale`）

## 深度学习 · 现代 AI（次优先 · 训练技巧 / 生成 / 强化学习）
> AI 主线（上面第一簇）已铺得比较厚，这批组件类 / RL 论文降为次优先，等分布式几簇推进后再回来做。
- **Diffusion (DDPM)** — Denoising Diffusion Probabilistic Models · Ho 等 · 2020 — 扩散模型，当代图像/视频生成主力（slug: `ddpm`）
- **Batch Normalization** — Ioffe & Szegedy (Google) · 2015 — 归一化中间激活，让深网训练更快更稳（slug: `batch-normalization`）
- **Dropout** — Srivastava 等 · 2014 — 随机「关掉」神经元来正则化（slug: `dropout`）
- **Adam** — A Method for Stochastic Optimization · Kingma & Ba · 2014 — 默认优化器，几乎每个深度模型都在用（slug: `adam-optimizer`）
- **DQN** — Playing Atari with Deep Reinforcement Learning · Mnih 等 (DeepMind) · 2013 — 深度网络从像素学会玩游戏，深度强化学习开篇（slug: `dqn-atari`）
- **AlphaGo** — Mastering the Game of Go · Silver 等 (DeepMind) · 2016 — 深度网络 + 蒙特卡洛树搜索击败围棋冠军（slug: `alphago`）

## 分布式共识 · 一致性 · 存储
- **逻辑时钟** — Time, Clocks, and the Ordering of Events · Lamport · 1978 — 逻辑时钟与 happens-before，分布式一致性思想原点（slug: `time-clocks-ordering`）
- **拜占庭将军** — The Byzantine Generals Problem · Lamport, Shostak, Pease · 1982 — 有节点会说谎时如何达成一致（slug: `byzantine-generals`）
- **Paxos** — Paxos Made Simple · Lamport · 2001 — 分布式共识的奠基算法（的简化讲法）（slug: `paxos-made-simple`）
- **Raft** — In Search of an Understandable Consensus Algorithm · Ongaro & Ousterhout · 2014 — 为「可理解」而设计的共识算法，工业界事实标准（slug: `raft`）
- **Dynamo** — Amazon's Highly Available Key-value Store · DeCandia 等 · 2007 — 最终一致 + 一致性哈希 + 向量时钟，NoSQL 浪潮源头（slug: `dynamo`）
- **CAP 雏形** — Harvest, Yield, and Scalable Tolerant Systems · Fox & Brewer · 1999 — CAP 定理思想雏形，一致性与可用性取舍（slug: `harvest-yield`）
- **Chord** — A Scalable Peer-to-peer Lookup Service · Stoica 等 (MIT) · 2001 — 分布式哈希表（DHT），P2P 查找经典（slug: `chord`）
- **Kafka** — a Distributed Messaging System for Log Processing · Kreps 等 (LinkedIn) · 2011 — 以日志为中心的流处理与消息系统（slug: `kafka`）

## 数据库 · 数据模型
- **关系模型** — A Relational Model of Data for Large Shared Data Banks · E. F. Codd · 1970 — 几乎所有现代数据库的理论根（slug: `relational-model`）

## 操作系统 · 网络架构
- **UNIX** — The UNIX Time-Sharing System · Ritchie & Thompson · 1974 — 定义现代操作系统哲学：一切皆文件、小工具组合（slug: `unix-time-sharing`）
- **端到端原则** — End-to-End Arguments in System Design · Saltzer, Reed, Clark · 1984 — 「功能该放在哪一层」，互联网架构第一性原理（slug: `end-to-end-arguments`）
- **TCP 拥塞控制** — Congestion Avoidance and Control · Van Jacobson · 1988 — 让互联网没有在流量下崩溃（slug: `congestion-avoidance-and-control`）

## 密码学 · 安全 · 去中心化
- **公钥密码学** — New Directions in Cryptography · Diffie & Hellman · 1976 — 公钥密码学诞生，无需预共享密钥也能安全通信（slug: `new-directions-in-cryptography`）
- **RSA** — A Method for Obtaining Digital Signatures and Public-Key Cryptosystems · Rivest, Shamir, Adleman · 1978 — 第一个实用公钥体制（slug: `rsa`）
- **Bitcoin** — A Peer-to-Peer Electronic Cash System · Satoshi Nakamoto · 2008 — 工作量证明解决无信任双花，区块链源头（slug: `bitcoin`）
- **信任的信任** — Reflections on Trusting Trust · Ken Thompson · 1984 — 「你能信任你没亲手写的代码吗」，最深刻的安全思想实验（slug: `reflections-on-trusting-trust`）

## 万维网 · 搜索 · 信息
- **超文本先知** — As We May Think · Vannevar Bush · 1945 — 预言了超链接与个人信息机器（slug: `as-we-may-think`）
- **PageRank** — The Anatomy of a Large-Scale Hypertextual Web Search Engine · Brin & Page · 1998 — PageRank，谷歌的起点（slug: `anatomy-of-a-search-engine`）

## 计算与信息理论基石
- **信息论** — A Mathematical Theory of Communication · Claude Shannon · 1948 — 信息论奠基，定义了「比特」与信道容量（slug: `mathematical-theory-of-communication`）
- **图灵机** — On Computable Numbers, with an Application to the Entscheidungsproblem · Alan Turing · 1936 — 图灵机与「可计算性」，计算理论的根（slug: `on-computable-numbers`）
- **图灵测试** — Computing Machinery and Intelligence · Alan Turing · 1950 — 「机器能思考吗」与图灵测试，AI 哲学起点（slug: `computing-machinery-and-intelligence`）
- **NP 完全性** — The Complexity of Theorem-Proving Procedures · Stephen Cook · 1971 — NP 完全性，P vs NP 问题开端（slug: `complexity-of-theorem-proving`）

## 软件工程 · 编程思想
- **结构化编程** — Go To Statement Considered Harmful · Edsger Dijkstra · 1968 — 结构化编程宣言，一封信改变编程范式（slug: `goto-considered-harmful`）
- **信息隐藏** — On the Criteria To Be Used in Decomposing Systems into Modules · David Parnas · 1972 — 模块化与封装的思想源（slug: `decomposing-systems-into-modules`）
- **没有银弹** — No Silver Bullet: Essence and Accident in Software Engineering · Fred Brooks · 1986 — 为什么软件复杂性没有银弹（slug: `no-silver-bullet`）
