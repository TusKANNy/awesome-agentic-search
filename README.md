# Awesome Retrieval for Agentic Search

[![Awesome](https://awesome.re/badge-flat.svg)](https://awesome.re) ![Status](https://img.shields.io/badge/status-active-brightgreen.svg)

An extensive and commented list of resources on **agentic search** and **agentic deep research** — systems where an LLM acts as an autonomous agent that plans, searches, inspects, and refines its retrieval in an iterative reasoning loop, rather than retrieving once and generating.

## Contents

- [Foundations](#foundations)
  - [Classic RAG](#classic-rag)
- [Retrieval Interface](#retrieval-interface)
  - [Retriever Training](#retriever-training)
  - [Reranking](#reranking)
  - [Structured & Hierarchical Retrieval](#structured--hierarchical-retrieval)
  - [Direct Corpus Interaction](#direct-corpus-interaction)
  - [Retrieval Analysis & Evaluation](#retrieval-analysis--evaluation)
- [The Agentic Search Loop](#the-agentic-search-loop)
  - [Planning & Reasoning](#planning--reasoning)
  - [Query Formulation & Decomposition](#query-formulation--decomposition)
  - [Adaptive Retrieval Control](#adaptive-retrieval-control)
  - [Context & Memory Management](#context--memory-management)
- [Training & Optimization](#training--optimization)
  - [RL-based Training](#rl-based-training)
  - [Data Synthesis](#data-synthesis)
  - [Analysis & Ablations](#analysis--ablations)
- [Systems & Benchmarks](#systems--benchmarks)
  - [Systems & Frameworks](#systems--frameworks)
  - [Benchmarks](#benchmarks)
- [Resources](#resources)
  - [Surveys & Position Papers](#surveys--position-papers)


## Foundations

### Classic RAG

The retrieve-then-generate paradigm that agentic search builds upon: a single retrieval step followed by generation, without iterative planning or tool use.

- *REALM: Retrieval-Augmented Language Model Pre-Training*  
Kelvin Guu, Kenton Lee, Zora Tung, Panupong Pasupat, Ming-Wei Chang  
ICML, 2020  
📄 [paper](https://arxiv.org/abs/2002.08909)

- *Dense Passage Retrieval for Open-Domain Question Answering*  
Vladimir Karpukhin, Barlas Oğuz, Sewon Min, Patrick Lewis, Ledell Wu, Sergey Edunov, Danqi Chen, Wen-tau Yih  
EMNLP, 2020  
📄 [paper](https://arxiv.org/abs/2004.04906) | 🛠️ [code](https://github.com/facebookresearch/DPR)

- *Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks*  
Patrick Lewis, Ethan Perez, Aleksandra Piktus, Fabio Petroni, Vladimir Karpukhin, Naman Goyal, Heinrich Küttler, Mike Lewis, Wen-tau Yih, Tim Rocktäschel, Sebastian Riedel, Douwe Kiela  
NeurIPS, 2020  
📄 [paper](https://arxiv.org/abs/2005.11401) | 🛠️ [code](https://github.com/huggingface/transformers/tree/main/src/transformers/models/rag)

- *Leveraging Passage Retrieval with Generative Models for Open Domain Question Answering*  
Gautier Izacard, Edouard Grave  
EACL, 2021  
📄 [paper](https://arxiv.org/abs/2007.01282) | 🛠️ [code](https://github.com/facebookresearch/FiD)


## Retrieval Interface

How the agent accesses knowledge sources — the substrate underlying the entire agentic search loop, from retriever training to structured indexing to raw corpus interaction.

### Retriever Training

Training the retriever/embedder itself to be reasoning-aware and agentic-search-aware, rather than treating it as a fixed component.

- *O1 Embedder: Let Retrievers Think Before Action*  
Ruiran Yan, Zheng Liu, Defu Lian  
arXiv, 2025  
📄 [paper](https://arxiv.org/abs/2502.07555)

- *DeepRetrieval: Hacking Real Search Engines and Retrievers with Large Language Models via Reinforcement Learning*  
Pengcheng Jiang, Jiacheng Lin, Lang Cao, Runchu Tian, SeongKu Kang, Zifeng Wang, Jimeng Sun, Jiawei Han  
COLM, 2025  
📄 [paper](https://arxiv.org/abs/2503.00223) | 🛠️ [code](https://github.com/pat-jj/DeepRetrieval)

- *ReasonIR: Training Retrievers for Reasoning Tasks*  
Rulin Shao, Rui Qiao, Varsha Kishore, Niklas Muennighoff, Xi Victoria Lin, Daniela Rus, Bryan Kian Hsiang Low, Sewon Min, Wen-tau Yih, Pang Wei Koh, Luke Zettlemoyer  
arXiv, 2025  
📄 [paper](https://arxiv.org/abs/2504.20595) | 🛠️ [code](https://github.com/facebookresearch/ReasonIR)

- *ConvSearch-R1: Enhancing Query Reformulation for Conversational Search with Reasoning via Reinforcement Learning*  
Changtai Zhu, Siyin Wang, Ruijun Feng, Kai Song, Xipeng Qiu  
EMNLP, 2025  
📄 [paper](https://arxiv.org/abs/2505.15776) | 🛠️ [code](https://github.com/BeastyZ/ConvSearch-R1)

- *RaDeR: Reasoning-aware Dense Retrieval Models*  
Debrup Das, Seán Ó Nualláin, Razieh Rahimi  
ICML, 2025  
📄 [paper](https://arxiv.org/abs/2505.18405)

- *TongSearch-QR: Reinforced Query Reasoning for Retrieval*  
Xubo Qin, Jun Bai, Jiaqi Li, Zixia Jia, Zilong Zheng  
arXiv, 2025  
📄 [paper](https://arxiv.org/abs/2506.11603) | 🛠️ [code](https://github.com/bigai-nlco/TongSearch-QR)

- *DIVER: A Multi-Stage Approach for Reasoning-intensive Information Retrieval*  
Meixiu Long, Duolin Sun, Dan Yang, Junjie Wang, Yecheng Luo, Yue Shen, Jian Wang, Hualei Zhou, Chunxiao Guo, Peng Wei, Jiahai Wang, Jinjie Gu  
arXiv, 2025  
📄 [paper](https://arxiv.org/abs/2508.07995)

- *Search-R3: Unifying Reasoning and Embedding Generation in Large Language Models*  
Yuntao Gui, James Cheng  
arXiv, 2025  
📄 [paper](https://arxiv.org/abs/2510.07048)

- *ReasonEmbed: Enhanced Text Embeddings for Reasoning-Intensive Document Retrieval*  
Jianlyu Chen, Junwei Lan, Chaofan Li, Defu Lian, Zheng Liu  
arXiv, 2025  
📄 [paper](https://arxiv.org/abs/2510.08252) | 🛠️ [code](https://github.com/FlagOpen/FlagEmbedding)

- *Agentic-R: Learning to Retrieve for Agentic Search*  
Wenhan Liu, Xinyu Ma, Yutao Zhu, Yuchen Li, Daiting Shi, Dawei Yin, Zhicheng Dou  
arXiv, 2026  
📄 [paper](https://arxiv.org/abs/2601.11888)

- *LaSER: Internalizing Explicit Reasoning into Latent Space for Dense Retrieval*  
Jiajie Jin, Yanzhao Zhang, Mingxin Li, Dingkun Long, Pengjun Xie, Yutao Zhu, Zhicheng Dou  
SIGIR, 2026  
📄 [paper](https://arxiv.org/abs/2603.01425) | 🛠️ [code](https://github.com/RUC-NLPIR/LaSER)

- *AgentIR: Reasoning-Aware Retrieval for Deep Research Agents*  
Zijian Chen, Xueguang Ma, Shengyao Zhuang, Jimmy Lin, Akari Asai, Victor Zhong  
arXiv, 2026  
📄 [paper](https://arxiv.org/abs/2603.04384) | 🛠️ [code](https://github.com/texttron/AgentIR)

- *Learning to Retrieve from Agent Trajectories (LRAT)*  
Yuqi Zhou, Sunhao Dai, Changle Qu, Liang Pang, Jun Xu, Ji-Rong Wen  
SIGIR, 2026  
📄 [paper](https://arxiv.org/abs/2604.04949) | 🛠️ [code](https://github.com/Yuqi-Zhou/LRAT)

- *CoSearch: Joint Training of Reasoning and Document Ranking via Reinforcement Learning for Agentic Search*  
Hansi Zeng, Liam Collins, Bhuvesh Kumar, Neil Shah, Hamed Zamani  
arXiv, 2026  
📄 [paper](https://arxiv.org/abs/2604.17555) | 🛠️ [code](https://github.com/snap-research/CoSearch)

- *Rethinking Reasoning-Intensive Retrieval: Evaluating and Advancing Retrievers in Agentic Search Systems (RTriever / BRIGHT-Pro)*  
Yilun Zhao, Jinbiao Wei, Tingyu Song, Siyue Zhang, Chen Zhao, Arman Cohan  
arXiv, 2026  
📄 [paper](https://arxiv.org/abs/2605.04018)

- *LatentRAG: Latent Reasoning and Retrieval for Efficient Agentic RAG*  
Yijia Zheng, Marcel Worring  
arXiv, 2026  
📄 [paper](https://arxiv.org/abs/2605.06285)

- *Critic-R: Improving Agentic Search using Instruction-tuned Retrievers with Natural Language Introspective Feedback*  
Md Zarif Ul Alam, Alireza Salemi, Hamed Zamani  
arXiv, 2026  
📄 [paper](https://arxiv.org/abs/2606.00590)

- *RL-Index: Reinforcement Learning for Retrieval Index Reasoning*  
Yongjia Lei, Zhisheng Qi, Utkarsh Sahu, Yu Wang, Nedim Lipka, Koustava Goswami, Franck Dernoncourt, Ryan A. Rossi  
arXiv, 2026  
📄 [paper](https://arxiv.org/abs/2606.16316)

### Reranking

Reranking components made reasoning-aware or reorganized around agentic search, rather than a fixed sequential pass.

- *Beyond Sequential Reranking: Reranker-Guided Search Improves Reasoning Intensive Retrieval*  
Haike Xu, Miao Zhang, Yipeng Kang, Zeyu Zhang, Sian-Chen Huang, Piotr Indyk  
arXiv, 2025  
📄 [paper](https://arxiv.org/abs/2509.07163)

- *LimRank: Less is More for Reasoning-Intensive Information Reranking*  
Tingyu Song, Yilun Zhao, Siyue Zhang, Chen Zhao, Arman Cohan  
EMNLP, 2025  
📄 [paper](https://arxiv.org/abs/2510.23544) | 🛠️ [code](https://github.com/SighingSnow/LimRank)

- *Reproducing Adaptive Reranking for Reasoning-Intensive IR*  
Mandeep Rathee, Venktesh V, Sean MacAvaney, Avishek Anand  
SIGIR, 2026  
📄 [paper](https://arxiv.org/abs/2604.27577)

- *Verbal-R3: Verbal Reranker as the Missing Bridge between Retrieval and Reasoning*  
Sangkwon Park, Donghun Kang, Jisoo Mok, Sungroh Yoon  
arXiv, 2026  
📄 [paper](https://arxiv.org/abs/2605.01399) | 🛠️ [code](https://github.com/0k9d0h1/VerbalR3)

- *MemReranker: Reasoning-Aware Reranking for Agent Memory Retrieval*  
Chunyu Li, Mengyuan Zhang, Jingyi Kang, Ding Chen, Jiajun Shen, Bo Tang, Xuanhe Zhou, Feiyu Xiong, Zhiyu Li  
arXiv, 2026  
📄 [paper](https://arxiv.org/abs/2605.06132)

### Structured & Hierarchical Retrieval

Reorganizing the corpus itself into structures (graphs, hierarchies, wikis) that agents can traverse, rather than a flat similarity index.

- *From Local to Global: A Graph RAG Approach to Query-Focused Summarization (GraphRAG)*  
Darren Edge, Ha Trinh, Newman Cheng, Joshua Bradley, Alex Chao, Apurva Mody, Steven Truitt, Jonathan Larson  
arXiv, 2024  
📄 [paper](https://arxiv.org/abs/2404.16130) | 🛠️ [code](https://github.com/microsoft/graphrag)

- *HippoRAG: Neurobiologically Inspired Long-Term Memory for Large Language Models*  
Bernal Jiménez Gutiérrez, Yiheng Shu, Yu Gu, Michihiro Yasunaga, Yu Su  
NeurIPS, 2024  
📄 [paper](https://arxiv.org/abs/2405.14831) | 🛠️ [code](https://github.com/OSU-NLP-Group/HippoRAG)

- *From RAG to Memory: Non-Parametric Continual Learning for Large Language Models (HippoRAG 2)*  
Bernal Jiménez Gutiérrez, Yiheng Shu, Weijian Qi, Sizhe Zhou, Yu Su  
arXiv, 2025  
📄 [paper](https://arxiv.org/abs/2502.14802) | 🛠️ [code](https://github.com/OSU-NLP-Group/HippoRAG)

- *Youtu-GraphRAG: Vertically Unified Agents for Graph Retrieval-Augmented Complex Reasoning*  
Junnan Dong, Siyu An, Yifei Yu, Qianwen Zhang, Linhao Luo, Xiao Huang, Yunsheng Wu, Di Yin, Xing Sun  
ICLR, 2026  
📄 [paper](https://arxiv.org/abs/2508.19855) | 🛠️ [code](https://github.com/TencentCloudADP/youtu-graphrag)

- *LLM-Guided Hierarchical Retrieval (LATTICE)*  
Nilesh Gupta, Wei-Cheng Chang, Ngot Bui, Cho-Jui Hsieh, Inderjit S. Dhillon  
arXiv, 2025  
📄 [paper](https://arxiv.org/abs/2510.13217) | 🛠️ [code](https://github.com/nilesh2797/llm-guided-hierarchical-search)

- *Deep GraphRAG: A Balanced Approach to Hierarchical Retrieval and Adaptive Integration*  
Yuejie Li, Ke Yang, Bolin Chen, Bowen Li, Chengjun Mao, Tao Wang  
arXiv, 2026  
📄 [paper](https://arxiv.org/abs/2601.11144)

- *T-Retriever: Tree-based Hierarchical Retrieval Augmented Generation for Textual Graphs*  
Chunyu Wei, Huaiyu Qin, Siyuan He, Yunhai Wang, Yueguo Chen  
AAAI, 2026  
📄 [paper](https://arxiv.org/abs/2601.04945) | 🛠️ [code](https://github.com/T-Retriever/T-Retriever)

- *A-RAG: Scaling Agentic Retrieval-Augmented Generation via Hierarchical Retrieval Interfaces*  
Mingxuan Du, Benfeng Xu, Chiwei Zhu, Shaohan Wang, Pengyu Wang, Xiaorui Wang, Zhendong Mao  
arXiv, 2026  
📄 [paper](https://arxiv.org/abs/2602.03442) | 🛠️ [code](https://github.com/Ayanami0730/arag)

- *DeepRead: Document Structure-Aware Reasoning to Enhance Agentic Search*  
Zhanli Li, Huiwen Tian, Lvzhou Luo, Yixuan Cao, Ping Luo  
arXiv, 2026  
📄 [paper](https://arxiv.org/abs/2602.05014) | 🛠️ [code](https://github.com/Zhanli-Li/DeepRead)

- *Don't Retrieve, Navigate: Distilling Enterprise Knowledge into Navigable Agent Skills for QA and RAG (Corpus2Skill)*  
Yiqun Sun, Pengfei Wei, Lawrence B. Hsieh  
arXiv, 2026  
📄 [paper](https://arxiv.org/abs/2604.14572) | 🛠️ [code](https://github.com/dukesun99/Corpus2Skill)

- *Retrieval as Reasoning: Self-Evolving Agent-Native Retrieval via LLM-Wiki*  
Haoliang Ming, Feifei Li, Xiaoqing Wu, Wenhui Que  
arXiv, 2026  
📄 [paper](https://arxiv.org/abs/2605.25480)

### Direct Corpus Interaction

The agent bypasses pre-computed indexes entirely, interacting with the raw corpus via terminal-style tools (grep, file reads, shell commands).

- *Interact-RAG: Reason and Interact with the Corpus, Beyond Black-Box Retrieval*  
Yulong Hui, Chao Chen, Zhihang Fu, Yihao Liu, Jieping Ye, Huanchen Zhang  
ICLR, 2026  
📄 [paper](https://arxiv.org/abs/2510.27566) | 🔗 [openreview](https://openreview.net/forum?id=yHUjWb6eMe)

- *Beyond Semantic Similarity: Rethinking Retrieval for Agentic Search via Direct Corpus Interaction*  
Zhuofeng Li, Haoxiang Zhang, Cong Wei, Pan Lu, Ping Nie, Yi Lu, Yuyang Bai, Shangbin Feng, Hangxiao Zhu, Ming Zhong, Yuyu Zhang, Jianwen Xie, Yejin Choi, James Zou, Jiawei Han, Wenhu Chen, Jimmy Lin, Dongfu Jiang, Yu Zhang.
arXiv, 2026  
📄 [paper](https://arxiv.org/abs/2605.05242) | 🛠️ [code](https://github.com/DCI-Agent/DCI-Agent-Lite)

- *Rethinking Agentic Search with PI-SERINI: Is Lexical Retrieval Sufficient?*  
Tz-Huan Hsu, Jheng-Hong Yang, Jimmy Lin  
arXiv, 2026  
📄 [paper](https://arxiv.org/abs/2605.10848) | 🛠️ [code](https://github.com/justram/pi-serini)

- *Rethinking Agentic RAG: Toward LLM-Driven Logical Retrieval Beyond Embeddings (LogicalRAG)*  
Yuqi Zeng, Qixiang Deng, Yulei Wan, Ruiquan Jiang, Xiaoqing Zheng, Xuanjing Huang  
arXiv, 2026  
📄 [paper](https://arxiv.org/abs/2605.27123)

- *GrepSeek: Training Search Agents for Direct Corpus Interaction*  
Alireza Salemi, Chang Zeng, Atharva Nijasure, Jui-Hui Chung, Razieh Rahimi, Fernando Diaz, Hamed Zamani  
arXiv, 2026  
📄 [paper](https://arxiv.org/abs/2605.29307)

- *Harness-1: Reinforcement Learning for Search Agents with State-Externalizing Harnesses*  
Pengcheng Jiang, Zhiyi Shi, Kelly Hong, Xueqiang Xu, Jiashuo Sun, Jimeng Sun, Hammad Bashir, Jiawei Han  
arXiv, 2026  
📄 [paper](https://arxiv.org/abs/2606.02373) | 🛠️ [code](https://github.com/pat-jj/harness-1)

- *Towards Retrieving Interaction Spaces for Agentic Search (RISE)*  
Shengyao Zhuang, Yuansheng Ni, Hengxin Fun, Jimmy Lin, Xueguang Ma  
arXiv, 2026  
📄 [paper](https://arxiv.org/abs/2606.06880) | 🛠️ [code](https://github.com/texttron/RISE)

- *DR-DCI: Scaling Direct Corpus Interaction via Dynamic Workspace Expansion*  
Yi Lu, Zhuofeng Li, Ping Nie, Haoxiang Zhang, Yuyu Zhang, Kai Zou, Wenhu Chen, Jimmy Lin, Dongfu Jiang, Yu Zhang  
arXiv, 2026  
📄 [paper](https://arxiv.org/abs/2606.14885)

- *Boolean Queries Are All You Need? (Vole)*  
Charles L. A. Clarke, Mark D. Smucker  
arXiv, 2026  
📄 [paper](https://arxiv.org/abs/2607.11362) | 🛠️ [code (Vole)](https://github.com/claclark/TheVole) | 🛠️ [code (Cottontail)](https://github.com/claclark/Cottontail)

### Retrieval Analysis & Evaluation

Studies characterizing agentic query workloads, comparing retrieval interfaces, and evaluating retrieval quality in deep research settings.

- *Rerank Before You Reason: Analyzing Reranking Tradeoffs through Effective Token Cost in Deep Search Agents*  
Sahel Sharifymoghaddam, Jimmy Lin  
arXiv, 2026  
📄 [paper](https://arxiv.org/abs/2601.14224) | 🛠️ [code](https://github.com/texttron/BrowseComp-Plus)

- *SAGE: Benchmarking and Improving Retrieval for Deep Research Agents*  
Tiansheng Hu, Yilun Zhao, Canyu Zhang, Arman Cohan, Chen Zhao  
arXiv, 2026  
📄 [paper](https://arxiv.org/abs/2602.05975) | 🛠️ [code](https://github.com/HughieHu/Sage)

- *A Picture of Agentic Search (ASQ)*  
Francesca Pezzuti, Ophir Frieder, Fabrizio Silvestri, Sean MacAvaney, Nicola Tonellotto  
arXiv, 2026  
📄 [paper](https://arxiv.org/abs/2602.17518) | 🛠️ [code](https://github.com/fpezzuti/ASQ)

- *Revisiting Text Ranking in Deep Research*  
Chuan Meng, Litu Ou, Sean MacAvaney, Jeff Dalton  
SIGIR, 2026  
📄 [paper](https://arxiv.org/abs/2602.21456) | 🛠️ [code](https://github.com/ChuanMeng/text-ranking-in-deep-research)

- *Keyword Search is All You Need: Achieving RAG-Level Performance Without Vector Databases Using Agentic Tool Use*  
Shreyas Subramanian, Adewale Akinfaderin, Yanyan Zhang, Ishan Singh, Mani Khanuja, Sandeep Singh, Maira Ladeira Tanke  
AAAI, 2026  
📄 [paper](https://arxiv.org/abs/2602.23368)

- *Superintelligent Retrieval Agent: The Next Frontier of Information Retrieval*  
Zeyu Yang, Qi Ma, Jason Chen, Anshumali Shrivastava  
arXiv, 2026  
📄 [paper](https://arxiv.org/abs/2605.06647) | 🛠️ [code](https://github.com/facebookresearch/sira)

- *Is Grep All You Need? How Agent Harnesses Reshape Agentic Search*  
Sahil Sen, Akhil Kasturi, Elias Lumer, Anmol Gulati, Vamse Kumar Subbiah  
arXiv, 2026  
📄 [paper](https://arxiv.org/abs/2605.15184)

## The Agentic Search Loop

Core papers on the agent's search behavior: how it plans, queries, retrieves, and adapts across the full information-seeking loop. This section is provided for context — this list's focus is on the retrieval side of agentic search. For a more in-depth selection of papers on the agentic search loop itself, see [Awesome-Search-Agent-Papers](https://github.com/YunjiaXi/Awesome-Search-Agent-Papers#early-iterative-retrieval).

### Planning & Reasoning

Foundational architectures that define the agent's core reasoning loop: interleaving thought, action, and retrieval.

- *WebGPT: Browser-Assisted Question-Answering with Human Feedback*  
Reiichiro Nakano, Jacob Hilton, Suchir Balaji, Jeff Wu, Long Ouyang, Christina Kim, Christopher Hesse, Shantanu Jain, Vineet Kosaraju, William Saunders, Xu Jiang, Karl Cobbe, Tyna Eloundou, Gretchen Krueger, Kevin Button, Matthew Knight, Benjamin Chess, John Schulman.  
arXiv, 2021  
📄 [paper](https://arxiv.org/abs/2112.09332)

- *ReAct: Synergizing Reasoning and Acting in Language Models*  
Shunyu Yao, Jeffrey Zhao, Dian Yu, Nan Du, Izhak Shafran, Karthik Narasimhan, Yuan Cao  
ICLR, 2023  
📄 [paper](https://arxiv.org/abs/2210.03629) | 🛠️ [code](https://github.com/ysymyth/ReAct)

- *Interleaving Retrieval with Chain-of-Thought Reasoning for Knowledge-Intensive Multi-Step Questions (IRCoT)*  
Harsh Trivedi, Niranjan Balasubramanian, Tushar Khot, Ashish Sabharwal  
ACL, 2023  
📄 [paper](https://arxiv.org/abs/2212.10509) | 🛠️ [code](https://github.com/StonyBrookNLP/ircot)

- *Search-o1: Agentic Search-Enhanced Large Reasoning Models*  
Xiaoxi Li, Guanting Dong, Jiajie Jin, Yuyao Zhang, Yujia Zhou, Yutao Zhu, Peitian Zhang, Zhicheng Dou  
EMNLP, 2025  
📄 [paper](https://arxiv.org/abs/2501.05366) | 🛠️ [code](https://github.com/RUC-NLPIR/Search-o1)

- *Agentic Reasoning: A Streamlined Framework for Enhancing LLM Reasoning with Agentic Tools*  
Junde Wu, Jiayuan Zhu, Yuyuan Liu, Min Xu, Yueming Jin  
ACL, 2025  
📄 [paper](https://arxiv.org/abs/2502.04644) | 🛠️ [code](https://github.com/theworldofagents/Agentic-Reasoning)

- *LLM-based Search Assistant with Holistically Guided MCTS for Intricate Information Seeking*  
Ruiyang Ren, Yuhao Wang, Junyi Li, Jinhao Jiang, Wayne Xin Zhao, Wenjie Wang, Tat-Seng Chua  
SIGIR, 2025  
📄 [paper](https://arxiv.org/abs/2502.04751)

- *WebThinker: Empowering Large Reasoning Models with Deep Research Capability*  
Xiaoxi Li, Jiajie Jin, Guanting Dong, Hongjin Qian, Yutao Zhu, Yongkang Wu, Ji-Rong Wen, Zhicheng Dou  
NeurIPS, 2025  
📄 [paper](https://arxiv.org/abs/2504.21776) | 🛠️ [code](https://github.com/RUC-NLPIR/WebThinker)

### Query Formulation & Decomposition

How the agent structures, decomposes, and parallelizes its search queries.

- *Decomposed Prompting: A Modular Approach for Solving Complex Tasks (DecomP)*  
Tushar Khot, Harsh Trivedi, Matthew Finlayson, Yao Fu, Kyle Richardson, Peter Clark, Ashish Sabharwal  
ICLR, 2023  
📄 [paper](https://arxiv.org/abs/2210.02406) | 🛠️ [code](https://github.com/allenai/decomp)

- *Measuring and Narrowing the Compositionality Gap with Language Models (Self-Ask)*  
Ofir Press, Muru Zhang, Sewon Min, Ludwig Schmidt, Noah A. Smith, Mike Lewis  
EMNLP Findings, 2023  
📄 [paper](https://arxiv.org/abs/2210.03350) | 🛠️ [code](https://github.com/ofirpress/self-ask)

- *BELLE: A Bi-Level Multi-Agent Reasoning Framework for Multi-Hop Question Answering*  
Taolin Zhang, Dongyang Li, Qizhou Chen, Chengyu Wang, Xiaofeng He  
ACL, 2025  
📄 [paper](https://arxiv.org/abs/2505.11811)

- *ParallelSearch: Train your LLMs to Decompose Query and Search Sub-queries in Parallel with Reinforcement Learning*  
Shu Zhao, Tan Yu, Anbang Xu, Japinder Singh, Aaditya Shukla, Rama Akkiraju  
arXiv, 2025  
📄 [paper](https://arxiv.org/abs/2508.09303)

- *SmartSearch: Process Reward-Guided Query Refinement for Search Agents*  
Tongyu Wen, Guanting Dong, Zhicheng Dou  
SIGIR, 2026  
📄 [paper](https://arxiv.org/abs/2601.04888) | 🛠️ [code](https://github.com/RUC-NLPIR/SmartSearch)

### Adaptive Retrieval Control

When to retrieve, how many times, and when to stop — including the decision between internal parametric knowledge and external retrieval.

- *Active Retrieval Augmented Generation (FLARE)*  
Zhengbao Jiang, Frank F. Xu, Luyu Gao, Zhiqing Sun, Qian Liu, Jane Dwivedi-Yu, Yiming Yang, Jamie Callan, Graham Neubig  
EMNLP, 2023  
📄 [paper](https://arxiv.org/abs/2305.06983) | 🛠️ [code](https://github.com/jzbjyb/FLARE)

- *Self-RAG: Learning to Retrieve, Generate, and Critique through Self-Reflection*  
Akari Asai, Zeqiu Wu, Yizhong Wang, Avi Sil, Hannaneh Hajishirzi  
ICLR, 2024  
📄 [paper](https://arxiv.org/abs/2310.11511) | 🛠️ [code](https://github.com/AkariAsai/self-rag)

- *Adaptive-RAG: Learning to Adapt Retrieval-Augmented Large Language Models through Question Complexity*  
Soyeong Jeong, Jinheon Baek, Sukmin Cho, Sung Ju Hwang, Jong C. Park  
NAACL, 2024  
📄 [paper](https://arxiv.org/abs/2403.14403) | 🛠️ [code](https://github.com/starsuzi/Adaptive-RAG)

- *Chain-of-Retrieval Augmented Generation (CoRAG)*  
Liang Wang, Haonan Chen, Nan Yang, Xiaolong Huang, Zhicheng Dou, Furu Wei  
NeurIPS, 2025  
📄 [paper](https://arxiv.org/abs/2501.14342) | 🛠️ [code](https://github.com/microsoft/LMOps/tree/main/corag)

- *DeepRAG: Thinking to Retrieve Step by Step for Large Language Models*  
Xinyan Guan, Jiali Zeng, Fandong Meng, Chunlei Xin, Yaojie Lu, Hongyu Lin, Xianpei Han, Le Sun, Jie Zhou  
ICLR, 2026  
📄 [paper](https://arxiv.org/abs/2502.01142)

- *Towards Adaptive Memory-Based Optimization for Enhanced Retrieval-Augmented Generation (Amber)*  
Qitao Qin, Yucong Luo, Yihang Lu, Zhibo Chu, Xiaoman Liu, Xianwei Meng  
ACL Findings, 2025  
📄 [paper](https://arxiv.org/abs/2504.05312)

- *Scent of Knowledge: Optimizing Search-Enhanced Reasoning with Information Foraging*  
Hongjin Qian, Zheng Liu  
NeurIPS, 2025  
📄 [paper](https://arxiv.org/abs/2505.09316)

- *R1-Searcher++: Incentivizing the Dynamic Knowledge Acquisition of LLMs via Reinforcement Learning*  
Huatong Song, Jinhao Jiang, Wenqing Tian, Zhipeng Chen, Yuhuan Wu, Jiahao Zhao, Yingqian Min, Wayne Xin Zhao, Lei Fang, Ji-Rong Wen.  
arXiv, 2025  
📄 [paper](https://arxiv.org/abs/2505.17005) | 🛠️ [code](https://github.com/RUCAIBox/R1-Searcher-plus)

- *Pangu DeepDiver: Adaptive Search Intensity Scaling via Open-Web Reinforcement Learning*  
Wenxuan Shi, Haochen Tan, Chuqiao Kuang, Xiaoguang Li, Xiaozhe Ren, Chen Zhang, Hanting Chen, Yasheng Wang, Lu Hou, Lifeng Shang.
arXiv, 2025  
📄 [paper](https://arxiv.org/abs/2505.24332)

- *Stop-RAG: Value-Based Retrieval Control for Iterative RAG*  
Jaewan Park, Solbee Cho, Jay-Yoon Lee  
NeurIPS Workshop, 2025  
📄 [paper](https://arxiv.org/abs/2510.14337)

- *AutoSearch: Adaptive Search Depth for Efficient Agentic RAG via Reinforcement Learning*  
Jingbo Sun, Wenyue Chong, Songjun Tu, Qichao Zhang, Yaocheng Zhang, Jiajun Chai, Xiaohan Wang, Wei Lin, Guojun Yin, Dongbin Zhao  
ACL Findings, 2026  
📄 [paper](https://arxiv.org/abs/2604.17337) | 🛠️ [code](https://github.com/bofusun/AutoSearch)

- *GRASP: GRanularity-Aware Search Policy for Agentic RAG*  
Varun Gandhi, Jaewook Lee, Shantanu Todmal, Andrew Lan, Franck Dernoncourt, Ryan Rossi, Zichao Wang  
arXiv, 2026  
📄 [paper](https://arxiv.org/abs/2607.10463)

- *R²-Searcher: Calibrating Retrieval and Reasoning Boundaries for Agentic Search*  
Sheng Zhang, Junyi Li, Wenlin Zhang, Xiaowei Qian, Yingyi Zhang, Maolin Wang, Yichao Wang, Yong Liu, Xiangyu Zhao  
arXiv, 2026  
📄 [paper](https://arxiv.org/abs/2606.28566)

- *TASR: Training-Free Adaptive Stopping for Iterative Retrieval*  
Adrian Kieback, Uyiosa Philip Amadasun, Aman Chadha, Aaron Elkins  
arXiv, 2026  
📄 [paper](https://arxiv.org/abs/2606.13814) | 🛠️ [code](https://github.com/JSBAICenter/TASR)

### Context & Memory Management

Managing information across long-horizon search trajectories without losing critical context.

- *MEM1: Learning to Synergize Memory and Reasoning for Efficient Long-Horizon Agents*  
Zijian Zhou, Ao Qu, Zhaoxuan Wu, Sunghwan Kim, Alok Prakash, Daniela Rus, Jinhua Zhao, Bryan Kian Hsiang Low, Paul Pu Liang  
ICLR, 2026  
📄 [paper](https://arxiv.org/abs/2506.15841) | 🛠️ [code](https://github.com/MIT-MI/MEM1)

- *WebResearcher: Unleashing Unbounded Reasoning Capability in Long-Horizon Agents*  
Zile Qiao, Guoxin Chen, Xuanzhong Chen, Donglei Yu, Wenbiao Yin, Xinyu Wang, Zhen Zhang, Baixuan Li, Huifeng Yin, Kuan Li, Rui Min, Minpeng Liao, Yong Jiang, Pengjun Xie, Fei Huang, Jingren Zhou.
arXiv, 2025  
📄 [paper](https://arxiv.org/abs/2509.13309) | 🛠️ [code](https://github.com/Alibaba-NLP/DeepResearch)

- *ReSum: Unlocking Long-Horizon Search Intelligence via Context Summarization*  
Xixi Wu, Kuan Li, Yida Zhao, Liwen Zhang, Litu Ou, Huifeng Yin, Zhongwang Zhang, Xinmiao Yu, Dingchu Zhang, Yong Jiang, Pengjun Xie, Fei Huang, Minhao Cheng, Shuai Wang, Hong Cheng, Jingren Zhou.
arXiv, 2025  
📄 [paper](https://arxiv.org/abs/2509.13313) | 🛠️ [code](https://github.com/Alibaba-NLP/WebAgent)

- *AgentFold: Long-Horizon Web Agents with Proactive Context Management*  
Rui Ye, Zhongwang Zhang, Kuan Li, Huifeng Yin, Zhengwei Tao, Yida Zhao, Liangcai Su, Liwen Zhang, Zile Qiao, Xinyu Wang, Pengjun Xie, Fei Huang, Siheng Chen, Jingren Zhou, Yong Jiang.
arXiv, 2025  
📄 [paper](https://arxiv.org/abs/2510.24699)

- *MemSearch-o1: Empowering Large Language Models with Reasoning-Aligned Memory Growth in Agentic Search*  
Sheng Zhang, Junyi Li, Yingyi Zhang, Pengyue Jia, Yichao Wang, Xiaowei Qian, Wenlin Zhang, Maolin Wang, Yong Liu, Xiangyu Zhao  
ACL, 2026  
📄 [paper](https://arxiv.org/abs/2604.17265)

## Training & Optimization

Methods for training agents to search effectively, through reinforcement learning or synthetic data generation. This section is provided for context — this list's focus is on the retrieval side of agentic search. For a more in-depth selection of RL-based agentic search training papers, see [Awesome-RL-based-Agentic-Search-Papers](https://github.com/ventr1c/Awesome-RL-based-Agentic-Search-Papers).

### RL-based Training

- *PaSa: An LLM Agent for Comprehensive Academic Paper Search*  
Yichen He, Guanhua Huang, Peiyuan Feng, Yuan Lin, Yuchen Zhang, Hang Li, Weinan E  
ACL, 2025  
📄 [paper](https://arxiv.org/abs/2501.10120) | 🛠️ [code](https://github.com/bytedance/pasa)

- *RAG-Gym: Optimizing Reasoning and Search Agents with Process Supervision*  
Guangzhi Xiong, Qiao Jin, Xiao Wang, Yin Fang, Haolin Liu, Yifan Yang, Fangyuan Chen, Zhixing Song, Dengyu Wang, Minjia Zhang, Zhiyong Lu, Aidong Zhang  
arXiv, 2025  
📄 [paper](https://arxiv.org/abs/2502.13957) | 🛠️ [code](https://github.com/RAG-Gym/RAG-Gym)

- *R1-Searcher: Incentivizing the Search Capability in LLMs via Reinforcement Learning*  
Huatong Song, Jinhao Jiang, Yingqian Min, Jie Chen, Zhipeng Chen, Wayne Xin Zhao, Lei Fang, Ji-Rong Wen  
arXiv, 2025  
📄 [paper](https://arxiv.org/abs/2503.05592) | 🛠️ [code](https://github.com/RUCAIBox/R1-Searcher)

- *Search-R1: Training LLMs to Reason and Leverage Search Engines with Reinforcement Learning*  
Bowen Jin, Hansi Zeng, Zhenrui Yue, Jinsung Yoon, Sercan Ö. Arik, Dong Wang, Hamed Zamani, Jiawei Han  
COLM, 2025  
📄 [paper](https://arxiv.org/abs/2503.09516) | 🛠️ [code](https://github.com/PeterGriffinJin/Search-R1)

- *ReSearch: Learning to Reason with Search for LLMs via Reinforcement Learning*  
Mingyang Chen, Linzhuang Sun, Tianpeng Li, Haoze Sun, Yijie Zhou, Chenzheng Zhu, Haofen Wang, Jeff Z. Pan, Wen Zhang, Huajun Chen, Fan Yang, Zenan Zhou, Weipeng Chen  
arXiv, 2025  
📄 [paper](https://arxiv.org/abs/2503.19470) | 🛠️ [code](https://github.com/Agent-RL/ReCall)

- *DeepResearcher: Scaling Deep Research via Reinforcement Learning in Real-World Environments*  
Yuxiang Zheng, Dayuan Fu, Xiangkun Hu, Xiaojie Cai, Lyumanshan Ye, Pengrui Lu, Pengfei Liu  
EMNLP, 2025  
📄 [paper](https://arxiv.org/abs/2504.03160) | 🛠️ [code](https://github.com/GAIR-NLP/DeepResearcher)

- *ZeroSearch: Incentivize the Search Capability of LLMs without Searching*  
Hao Sun, Zile Qiao, Jiayan Guo, Xuanbo Fan, Yingyan Hou, Yong Jiang, Pengjun Xie, Yan Zhang, Fei Huang, Jingren Zhou  
arXiv, 2025  
📄 [paper](https://arxiv.org/abs/2505.04588) | 🛠️ [code](https://github.com/Alibaba-NLP/ZeroSearch)

- *Search and Refine During Think: Facilitating Knowledge Refinement for Improved Retrieval-Augmented Reasoning (AutoRefine)*  
Yaorui Shi, Shihan Li, Chang Wu, Zhiyuan Liu, Junfeng Fang, Hengxing Cai, An Zhang, Xiang Wang  
NeurIPS, 2025  
📄 [paper](https://arxiv.org/abs/2505.11277) | 🛠️ [code](https://github.com/syr-cn/AutoRefine)

- *s3: You Don't Need That Much Data to Train a Search Agent via RL*  
Pengcheng Jiang, Xueqiang Xu, Jiacheng Lin, Jinfeng Xiao, Zifeng Wang, Jimeng Sun, Jiawei Han  
EMNLP, 2025  
📄 [paper](https://arxiv.org/abs/2505.14146) | 🛠️ [code](https://github.com/pat-jj/s3)

- *StepSearch: Igniting LLMs Search Ability via Step-Wise Proximal Policy Optimization*  
Ziliang Wang, Xuhui Zheng, Kang An, Cijun Ouyang, Jialu Cai, Yuhang Wang, Yichao Wu  
EMNLP, 2025  
📄 [paper](https://arxiv.org/abs/2505.15107)

- *Iterative Self-Incentivization Empowers Large Language Models as Agentic Searchers (ExSearch)*  
Zhengliang Shi, Lingyong Yan, Dawei Yin, Suzan Verberne, Maarten de Rijke, Zhaochun Ren  
NeurIPS, 2025  
📄 [paper](https://arxiv.org/abs/2505.20128)

- *MaskSearch: A Universal Pre-Training Framework to Enhance Agentic Search Capability*  
Weiqi Wu, Xin Guan, Shen Huang, Yong Jiang, Pengjun Xie, Fei Huang, Jiuxin Cao, Hai Zhao, Jingren Zhou  
arXiv, 2025  
📄 [paper](https://arxiv.org/abs/2505.20285) | 🛠️ [code](https://github.com/Alibaba-NLP/MaskSearch)

- *WebDancer: Towards Autonomous Information Seeking Agency*  
Jialong Wu, Baixuan Li, Runnan Fang, Wenbiao Yin, Liwen Zhang, Zhengwei Tao, Dingchu Zhang, Zekun Xi, Gang Fu, Yong Jiang, Pengjun Xie, Fei Huang, Jingren Zhou  
arXiv, 2025  
📄 [paper](https://arxiv.org/abs/2505.22648) | 🛠️ [code](https://github.com/Alibaba-NLP/WebAgent)

- *R-Search: Empowering LLM Reasoning with Search via Multi-Reward Reinforcement Learning*  
Qingfei Zhao, Ruobing Wang, Dingling Xu, Daren Zha, Limin Liu  
arXiv, 2025  
📄 [paper](https://arxiv.org/abs/2506.04185)

- *WebSailor: Navigating Super-Human Reasoning for Web Agent*  
Kuan Li, Zhongwang Zhang, Huifeng Yin, Liwen Zhang, Litu Ou, Jialong Wu, Wenbiao Yin, Baixuan Li, Zhengwei Tao, Xinyu Wang, Weizhou Shen, Junkai Zhang, Dingchu Zhang, Xixi Wu, Yong Jiang, Ming Yan, Pengjun Xie, Fei Huang, Jingren Zhou.
arXiv, 2025  
📄 [paper](https://arxiv.org/abs/2507.02592) | 🛠️ [code](https://github.com/Alibaba-NLP/WebAgent)

- *Beyond Ten Turns: Unlocking Long-Horizon Agentic Search with Large-Scale Asynchronous RL (ASearcher)*  
Jiaxuan Gao, Wei Fu, Minyang Xie, Shusheng Xu, Chuyi He, Zhiyu Mei, Banghua Zhu, Yi Wu  
arXiv, 2025  
📄 [paper](https://arxiv.org/abs/2508.07976) | 🛠️ [code](https://github.com/inclusionAI/ASearcher)

- *ReSeek: A Self-Correcting Framework for Search Agents with Instructive Rewards*  
Shiyu Li, Yang Tang, Yifan Wang, Peiming Li, Xi Chen  
arXiv, 2025  
📄 [paper](https://arxiv.org/abs/2510.00568)

- *HiPRAG: Hierarchical Process Rewards for Efficient Agentic RAG*  
Peilin Wu, Mian Zhang, Kun Wan, Wentian Zhao, Kaiyu He, Xinya Du, Zhiyu Chen  
arXiv, 2025  
📄 [paper](https://arxiv.org/abs/2510.07794)

- *InfoFlow: Reinforcing Search Agent via Reward Density Optimization*  
Kun Luo, Hongjin Qian, Zheng Liu, Ziyi Xia, Shitao Xiao, Siqi Bao, Jun Zhao, Kang Liu  
arXiv, 2025  
📄 [paper](https://arxiv.org/abs/2510.26575)

- *Optimizing Agentic Reasoning with Retrieval via Synthetic Semantic Information Gain Reward (InfoReasoner)*  
Senkang Hu, Yong Dai, Yuzhi Zhao, Yihang Tao, Yu Guo, Zhengru Fang, Sam Tak Wu Kwong, Yuguang Fang  
ICML, 2026  
📄 [paper](https://arxiv.org/abs/2602.00845) | 🛠️ [code](https://github.com/dl-m9/InfoReasoner)

- *SubSearch: Intermediate Rewards for Unsupervised Guided Reasoning in Complex Retrieval*  
Roxana Petcu, Evangelos Kanoulas, Maarten de Rijke  
arXiv, 2026  
📄 [paper](https://arxiv.org/abs/2604.07415) | 🛠️ [code](https://github.com/RoxanaPetcu/SubSearch)

### Data Synthesis

- *HopWeaver: Cross-Document Synthesis of High-Quality and Authentic Multi-Hop Questions*  
Zhiyu Shen, Jiyuan Liu, Yunhe Pang, Yanghui Rao, Fu Lee Wang, Jianxing Yu  
ACL, 2026  
📄 [paper](https://arxiv.org/abs/2505.15087) | 🛠️ [code](https://github.com/Zh1yuShen/HopWeaver)

- *SimpleDeepSearcher: Deep Information Seeking via Web-Powered Reasoning Trajectory Synthesis*  
Shuang Sun, Huatong Song, Yuhao Wang, Ruiyang Ren, Jinhao Jiang, Junjie Zhang, Fei Bai, Jia Deng, Wayne Xin Zhao, Zheng Liu, Lei Fang, Zhongyuan Wang, Ji-Rong Wen. 
EMNLP Findings, 2025  
📄 [paper](https://arxiv.org/abs/2505.16834) | 🛠️ [code](https://github.com/RUCAIBox/SimpleDeepSearcher)

- *WebShaper: Agentically Data Synthesizing via Information-Seeking Formalization*  
Zhengwei Tao, Jialong Wu, Wenbiao Yin, Junkai Zhang, Baixuan Li, Haiyang Shen, Kuan Li, Liwen Zhang, Xinyu Wang, Yong Jiang, Pengjun Xie, Fei Huang, Jingren Zhou.
arXiv, 2025  
📄 [paper](https://arxiv.org/abs/2507.15061) | 🛠️ [code](https://github.com/Alibaba-NLP/WebAgent)

### Analysis & Ablations

Empirical studies analyzing reinforcement learning dynamics and reward design for agentic search training.

- *Process vs. Outcome Reward: Which is Better for Agentic RAG Reinforcement Learning*  
Wenlin Zhang, Xiangyang Li, Kuicai Dong, Yichao Wang, Pengyue Jia, Xiaopeng Li, Yingyi Zhang, Derong Xu, Zhaocheng Du, Huifeng Guo, Ruiming Tang, Xiangyu Zhao  
arXiv, 2025  
📄 [paper](https://arxiv.org/abs/2505.14069)

- *An Empirical Study on Reinforcement Learning for Reasoning-Search Interleaved LLM Agents*  
Bowen Jin, Jinsung Yoon, Priyanka Kargupta, Sercan Ö. Arık, Jiawei Han  
arXiv, 2025  
📄 [paper](https://arxiv.org/abs/2505.15117) | 🛠️ [code](https://github.com/PeterGriffinJin/Search-R1)

## Systems & Benchmarks

### Systems & Frameworks

End-to-end systems, serving-efficiency work, and open multi-agent frameworks.

- *Demystifying and Enhancing the Efficiency of LLM-Based Search Agents (SearchAgent-X)*  
Tiannuo Yang, Zebin Yao, Bowen Jin, Lixiao Cui, Yusen Li, Gang Wang, Xiaoguang Liu  
ICLR, 2026  
📄 [paper](https://arxiv.org/abs/2505.12065) | 🛠️ [code](https://github.com/tiannuo-yang/SearchAgent-X)

- *ManuSearch: Democratizing Deep Search in Large Language Models with a Transparent and Open Multi-Agent Framework*  
Lisheng Huang, Yichen Liu, Jinhao Jiang, Rongxiang Zhang, Jiahao Yan, Junyi Li, Wayne Xin Zhao  
EMNLP, 2025  
📄 [paper](https://arxiv.org/abs/2505.18105) | 🛠️ [code](https://github.com/RUCAIBox/ManuSearch)

- *Tongyi DeepResearch Technical Report*  
Tongyi DeepResearch Team  
arXiv, 2025  
📄 [paper](https://arxiv.org/abs/2510.24701) | 🛠️ [code](https://github.com/Alibaba-NLP/DeepResearch)

### Benchmarks

- *HotpotQA: A Dataset for Diverse, Explainable Multi-hop Question Answering*  
Zhilin Yang, Peng Qi, Saizheng Zhang, Yoshua Bengio, William W. Cohen, Ruslan Salakhutdinov, Christopher D. Manning  
EMNLP, 2018  
📄 [paper](https://arxiv.org/abs/1809.09600) | 🛠️ [code](https://hotpotqa.github.io)

- *MuSiQue: Multihop Questions via Single-hop Question Composition*  
Harsh Trivedi, Niranjan Balasubramanian, Tushar Khot, Ashish Sabharwal  
TACL, 2022  
📄 [paper](https://arxiv.org/abs/2108.00573) | 🛠️ [code](https://github.com/StonyBrookNLP/musique)

- *GAIA: A Benchmark for General AI Assistants*  
Grégoire Mialon, Clémentine Fourrier, Craig Swift, Thomas Wolf, Yann LeCun, Thomas Scialom  
ICLR, 2024  
📄 [paper](https://arxiv.org/abs/2311.12983)

- *Researchy Questions: A Dataset of Multi-Perspective, Decompositional Questions for Deep Research*  
Corby Rosset, Ho-Lam Chung, Guanghui Qin, Ethan C. Chau, Zhuo Feng, Ahmed Awadallah, Jennifer Neville, Nikhil Rao  
SIGIR, 2025  
📄 [paper](https://arxiv.org/abs/2402.17896)

- *BRIGHT: A Realistic and Challenging Benchmark for Reasoning-Intensive Retrieval*  
Hongjin Su, Howard Yen, Mengzhou Xia, Weijia Shi, Niklas Muennighoff, Han-yu Wang, Haisu Liu, Quan Shi, Zachary S. Siegel, Michael Tang, Ruoxi Sun, Jinsung Yoon, Sercan Ö. Arik, Danqi Chen, Tao Yu  
ICLR, 2025  
📄 [paper](https://arxiv.org/abs/2407.12883) | 🛠️ [code](https://github.com/xlang-ai/BRIGHT)

- *AssistantBench: Can Web Agents Solve Realistic and Time-Consuming Tasks?*  
Ori Yoran, Samuel Joseph Amouyal, Chaitanya Malaviya, Ben Bogin, Ofir Press, Jonathan Berant  
EMNLP, 2024  
📄 [paper](https://arxiv.org/abs/2407.15711) | 🛠️ [code](https://github.com/oriyor/assistantbench)

- *FRAMES: Fact, Fetch, and Reason — A Unified Evaluation of Retrieval-Augmented Generation*  
Satyapriya Krishna, Kalpesh Krishna, Anhad Mohananey, Steven Schwarcz, Adam Stambler, Shyam Upadhyay, Manaal Faruqui  
NAACL, 2025  
📄 [paper](https://arxiv.org/abs/2409.12941)

- *WebWalker: Benchmarking LLMs in Web Traversal*  
Jialong Wu, Wenbiao Yin, Yong Jiang, Zhenglin Wang, Zekun Xi, Runnan Fang, Linhai Zhang, Yulan He, Deyu Zhou, Pengjun Xie, Fei Huang  
ACL, 2025  
📄 [paper](https://arxiv.org/abs/2501.07572)

- *Humanity's Last Exam (HLE)*  
Long Phan, Alice Gatti, Ziwen Han, Nathaniel Li, et al.  
arXiv, 2025  
📄 [paper](https://arxiv.org/abs/2501.14249)

- *BrowseComp: A Simple Yet Challenging Benchmark for Browsing Agents*  
Jason Wei, Zhiqing Sun, Spencer Papay, Scott McKinney, Jeffrey Han, Isa Fulford, Hyung Won Chung, Alex Tachard Passos, William Fedus, Amelia Glaese  
arXiv, 2025  
📄 [paper](https://arxiv.org/abs/2504.12516)

- *BrowseComp-ZH: Benchmarking Web Browsing Ability of LLMs in Chinese*  
Peilin Zhou, Bruce Leon, Xiang Ying, Can Zhang, Yifan Shao, Qichen Ye, Dading Chong, Zhiling Jin, Chenxuan Xie, Meng Cao, Yuxin Gu, Sixin Hong, Jing Ren, Jian Chen, Chao Liu, Yining Hua.
arXiv, 2025  
📄 [paper](https://arxiv.org/abs/2504.19314)

- *InfoDeepSeek: Benchmarking Agentic Information Seeking for Retrieval-Augmented Generation*  
Yunjia Xi, Jianghao Lin, Menghui Zhu, Yongzhao Xiao, Zhuoying Ou, Jiaqi Liu, Tong Wan, Bo Chen, Weiwen Liu, Yasheng Wang, Ruiming Tang, Weinan Zhang, Yong Yu  
arXiv, 2025  
📄 [paper](https://arxiv.org/abs/2505.15872) | 🛠️ [code](https://github.com/YunjiaXi/InfoDeepSeek)

- *DeepResearch Bench: A Comprehensive Benchmark for Deep Research Agents*  
Mingxuan Du, Benfeng Xu, Chiwei Zhu, Xiaorui Wang, Zhendong Mao  
arXiv, 2025  
📄 [paper](https://arxiv.org/abs/2506.11763) | 🛠️ [code](https://github.com/Ayanami0730/deep_research_bench)

- *Mind2Web 2: Evaluating Agentic Search with Agent-as-a-Judge*  
Boyu Gou, Zanming Huang, Yuting Ning, Yu Gu, Michael Lin, Weijian Qi, Andrei Kopanev, Botao Yu, Bernal Jimenez Gutierrez, Yiheng Shu, Chan Hee Song, Jiaman Wu, Shijie Chen, Hanane Moussa, Tianshu Zhang, Jian Xie, Yifei Li, Tianci Xue, Zeyi Liao, Kai Zhang, Boyuan Zheng, Zhaowei Cai, Viktor Rozgic, Morteza Ziyadi, Huan Sun, Yu Su  
NeurIPS, 2025  
📄 [paper](https://arxiv.org/abs/2506.21506) | 🛠️ [code](https://github.com/OSU-NLP-Group/Mind2Web-2)

- *BrowseComp-Plus: A More Fair and Transparent Evaluation Benchmark of Deep-Research Agents*  
Zijian Chen, Xueguang Ma, Shengyao Zhuang, Ping Nie, Kai Zou, Andrew Liu, Joshua Green, Kshama Patel, Ruoxi Meng, Mingyi Su, Sahel Sharifymoghaddam, Yanxi Li, Haoran Hong, Xinyu Shi, Xuye Liu, Nandan Thakur, Crystina Zhang, Luyu Gao, Wenhu Chen, Jimmy Lin.
arXiv, 2025  
📄 [paper](https://arxiv.org/abs/2508.06600)

- *Beyond Monolingual Deep Research: Evaluating Agents and Retrievers with Cross-Lingual BrowseComp-Plus (XBCP)*  
Yuheng Lu, Qingcheng Zeng, Heli Qi, Puxuan Yu, Fuheng Zhao, Rui Yang, Hitomi Yanaka, Naoto Yokoya, Weihao Xuan  
arXiv, 2026  
📄 [paper](https://arxiv.org/abs/2606.15345)

- *WideSearch: Benchmarking Agentic Broad Info-Seeking*  
Ryan Wong, Jiawei Wang, Junjie Zhao, Li Chen, Yan Gao, Long Zhang, Xuan Zhou, Zuo Wang, Kai Xiang, Ge Zhang, Wenhao Huang, Yang Wang, Ke Wang  
ICLR, 2026  
📄 [paper](https://arxiv.org/abs/2508.07999) | 🛠️ [code](https://github.com/ByteDance-Seed/WideSearch)

- *InteractComp: Evaluating Search Agents With Ambiguous Queries*  
Mingyi Deng, Lijun Huang, Yani Fan, Jiayi Zhang, Fashen Ren, Jinyi Bai, Fuzhen Yang, Dayi Miao, Zhaoyang Yu, Yifan Wu, Yanfei Zhang, Fengwei Teng, Yingjia Wan, Song Hu, Yude Li, Xin Jin, Conghao Hu, Haoyu Li, Qirui Fu, Tai Zhong, Xinyu Wang, Xiangru Tang, Nan Tang, Chenglin Wu, Yuyu Luo.
arXiv, 2025  
📄 [paper](https://arxiv.org/abs/2510.24668) | 🛠️ [code](https://github.com/FoundationAgents/InteractComp)

- *One Interaction Is Worth a Thousand Guesses: Benchmarking the Interactive Capabilities of Deep Research Agents (IDRBench)*  
Yingchaojie Feng, Qiang Huang, Xiaoya Xie, Zhaorui Yang, Jun Yu, Wei Chen, Anthony K. H. Tung  
arXiv, 2026  
📄 [paper](https://arxiv.org/abs/2601.06676)

- *DeepResearch-9K: A Challenging Benchmark Dataset of Deep-Research Agent*  
Tongzhou Wu, Yuhao Wang, Xinyu Ma, Xiuqiang He, Shuaiqiang Wang, Dawei Yin, Xiangyu Zhao  
SIGIR, 2026  
📄 [paper](https://arxiv.org/abs/2603.01152) | 🛠️ [code](https://github.com/Applied-Machine-Learning-Lab/DeepResearch-R1)

- *PaperSearchQA: Learning to Search and Reason over Scientific Papers with RLVR*  
James Burgess, Jan N. Hansen, Duo Peng, Yuhui Zhang, Alejandro Lozano, Min Woo Sun, Emma Lundberg, Serena Yeung-Levy  
arXiv, 2026  
📄 [paper](https://arxiv.org/abs/2601.18207) | 🛠️ [code](https://github.com/jmhb0/PaperSearchQA)

- *DeepWeb-Bench: A Deep Research Benchmark Demanding Massive Cross-Source Evidence and Long-Horizon Derivation*  
Sixiong Xie, Zhuofan Shi, Haiyang Shen, Jiuzheng Wang, Siqi Zhong, Mugeng Liu, Chongyang Pan, Peilun Jia, Baoqing Sun, Xiang Jing, Yun Ma  
arXiv, 2026  
📄 [paper](https://arxiv.org/abs/2605.21482)


## Resources

### Surveys & Position Papers

- *Towards AI Search Paradigm*  
Yuchen Li, Hengyi Cai, Rui Kong, Xinran Chen, Jiamin Chen, Jun Yang, Haojie Zhang, Jiayi Li, Jiayi Wu, Yiqun Chen, Changle Qu, Wenwen Ye, Lixin Su, Xinyu Ma, Lingyong Yan, Long Xia, Daiting Shi, Junfeng Wang, Xiangyu Zhao, Jiashu Zhao, Haoyi Xiong, Shuaiqiang Wang, Dawei Yin  
arXiv, 2025  
📄 [paper](https://arxiv.org/abs/2506.17188)

- *Deep Research Agents: A Systematic Examination And Roadmap*  
Yuxuan Huang, Yihang Chen, Haozheng Zhang, Kang Li, Huichi Zhou, Meng Fang, Linyi Yang, Xiaoguang Li, Lifeng Shang, Songcen Xu, Jianye Hao, Kun Shao, Jun Wang.
arXiv, 2025  
📄 [paper](https://arxiv.org/abs/2506.18096) | 🛠️ [repo](https://github.com/ai-agents-2030/awesome-deep-research-agent)

- *From Web Search towards Agentic Deep Research: Incentivizing Search with Reasoning Agents*  
Weizhi Zhang, Yangning Li, Yuanchen Bei, Junyu Luo, Guancheng Wan, Liangwei Yang, Chenxuan Xie, Yuyao Yang, Wei-Chieh Huang, Chunyu Miao, Henry Peng Zou, Xiao Luo, Yusheng Zhao, Yankai Chen, Chunkit Chan, Peilin Zhou, Xinyang Zhang, Chenwei Zhang, Jingbo Shang, Ming Zhang, Yangqiu Song, Irwin King, Philip S. Yu.
arXiv, 2025  
📄 [paper](https://arxiv.org/abs/2506.18959) | 🛠️ [repo](https://github.com/DavidZWZ/Awesome-Deep-Research)

- *Towards Agentic RAG with Deep Reasoning: A Survey of RAG-Reasoning Systems in LLMs*  
Yangning Li, Weizhi Zhang, Yuyao Yang, Wei-Chieh Huang, Yaozu Wu, Junyu Luo, Yuanchen Bei, Henry Peng Zou, Xiao Luo, Yusheng Zhao, Chunkit Chan, Yankai Chen, Zhongfen Deng, Yinghui Li, Hai-Tao Zheng, Dongyuan Li, Renhe Jiang, Ming Zhang, Yangqiu Song, Philip S. Yu.
EMNLP Findings, 2025  
📄 [paper](https://arxiv.org/abs/2507.09477) | 🛠️ [repo](https://github.com/DavidZWZ/Awesome-RAG-Reasoning)

- *A Survey of LLM-based Deep Search Agents: Paradigm, Optimization, Evaluation, and Challenges*  
Yunjia Xi, Jianghao Lin, Yongzhao Xiao, Zheli Zhou, Rong Shan, Te Gao, Jiachen Zhu, Weiwen Liu, Yong Yu, Weinan Zhang.
arXiv, 2025  
📄 [paper](https://arxiv.org/abs/2508.05668) | 🛠️ [repo](https://github.com/YunjiaXi/Awesome-Search-Agent-Papers)

- *The Landscape of Agentic Reinforcement Learning for LLMs: A Survey*  
Guibin Zhang, Hejia Geng, Xiaohang Yu, Zhenfei Yin, Zaibin Zhang, Zelin Tan, Heng Zhou, Zhongzhi Li, Xiangyuan Xue, Yijiang Li, Yifan Zhou, Yang Chen, Chen Zhang, Yutao Fan, Zihu Wang, Songtao Huang, Francisco Piedrahita-Velez, Yue Liao, Hongru Wang, Mengyue Yang, Heng Ji, Jun Wang, Shuicheng Yan, Philip Torr, Lei Bai.
arXiv, 2025  
📄 [paper](https://arxiv.org/abs/2509.02547) | 🛠️ [repo](https://github.com/xhyumiracle/Awesome-AgenticLLM-RL-Papers)

- *Reinforcement Learning Foundations for Deep Research Systems: A Survey*  
Wenjun Li, Zhi Chen, Jingru Lin, Hannan Cao, Wei Han, Sheng Liang, Zhi Zhang, Kuicai Dong, Dexun Li, Chen Zhang, Yong Liu.
arXiv, 2025  
📄 [paper](https://arxiv.org/abs/2509.06733)

- *A Comprehensive Survey on Reinforcement Learning-based Agentic Search: Foundations, Roles, Optimizations, Evaluations, and Applications* 
Minhua Lin, Zongyu Wu, Zhichao Xu, Hui Liu, Xianfeng Tang, Qi He, Charu Aggarwal, Hui Liu, Xiang Zhang, Suhang Wang.
arXiv, 2025  
📄 [paper](https://arxiv.org/abs/2510.16724) | 🛠️ [repo](https://github.com/ventr1c/Awesome-RL-based-Agentic-Search-Papers)


### List Maintainers

Francesco Benocci (ISTI-CNR, Pisa, Italy)