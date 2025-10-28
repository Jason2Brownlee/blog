---
date: '2025-10-29T06:41:28+11:00'
title: 'Sequence of Innovations for LLMs'
---

Yesterday, I was listening to the [Modern Wisdom](https://chriswillx.com/podcast/) podcast interview with Eliezer Yudkowsky about his new book (which I've read).

The podcast:

* [#1011 – Eliezer Yudkowsky – Why Superhuman AI Would Kill Us All](https://www.youtube.com/watch?v=nRvAt4H7d7E)

The book:

* [If Anyone Builds It, Everyone Dies: Why Superhuman AI Would Kill Us All](https://amzn.asia/d/0Qj0B1P), Eliezer Yudkowsky & Nate Soares, 2025.

Yudkowsky always gives great analogies, this interview was no different. The climbing the ladder analogy hit for me:

> ... and with artificial intelligence, what we've got is a ladder where every time you climb another step on the ladder, you get five times as much money. But one of those steps of the ladder destroys the world.

Reminds me of Nick Bostrom's urn analogy ([The Vulnerable World Hypothesis](https://en.wikipedia.org/wiki/Vulnerable_world_hypothesis)), something like (via Claude):

> In this thought experiment, Bostrom imagines that technological discoveries are like drawing balls from a giant urn. Most balls are white (beneficial or neutral technologies), some are grey (technologies with mixed effects), but there might be a black ball in the urn - a technology that's so destructive and easy to access that it would be essentially impossible for civilization to survive its discovery.

Anyway, at one point Yudkowsky was enumerating some of the innovations that got us to modern systems, I think as making a point about how we can't predict what/when for the next innovation.

It got me thinking. It would be fun to build/read a reference that walks through innovations to current systems.

Perhaps not all, but some or most. This is probably what a modern University course on LLMs would do.

Something like starting at backprop and ending up at RL on reasoning or something. I suspect the early stuff is simpler, more tractable to build with numpy in a notebook, and more fun. The later stuff is probably too big and heavy and would just be "ideas to know".

Anyway, I asked GPT5 to think on this, and here's what it gave me:

---

Here’s a compact, CS-focused lineage of the core innovations that made late-2025 LLMs like ChatGPT/Claude possible—each item lists the key idea and a representative paper.

* Backpropagation & gradient training for deep nets — general learning recipe for multi-layer networks. ([Gwern][1])

* ReLU activations — efficient, sparse, non-saturating nonlinearity. ([Proceedings of Machine Learning Research][2])

* Batch Normalization — stable/fast training via internal covariate shift reduction. ([Proceedings of Machine Learning Research][3])

* Dropout — stochastic regularization to prevent overfitting. ([Journal of Machine Learning Research][4])

* GPU deep learning at scale (e.g., AlexNet) — practical, high-throughput training. ([NeurIPS Papers][5])

* Mixed-precision training (FP16/bfloat16) — halves memory, speeds up training. ([arXiv][6])

* Adam / AdamW-style optimizers — adaptive, first-order optimization at scale. ([arXiv][7])

* Layer Normalization — normalization that works in non-batch/sequence settings. ([arXiv][8])

* Attention mechanisms → Transformers — parallel sequence modeling w/ self-attention (“Attention Is All You Need”). ([arXiv][9])

* Tokenization via subwords — BPE/SentencePiece enable open-vocabulary LMs. ([arXiv][10])

* Decoding strategies — nucleus (top-p) sampling reduces degeneration vs. beam search. ([arXiv][11])

* Position handling for long contexts — RoPE, ALiBi, Transformer-XL. ([arXiv][12])

* Multi-/Grouped-Query Attention — faster decoder inference via shared KV heads. ([arXiv][13])

* Pretraining → instruction-following evolution

  * GPT-style generative pretraining (GPT-1/2) — zero-/few-shot behaviors emerge. ([OpenAI][14])
  * BERT — bidirectional masked-LM pretraining for encoders. ([arXiv][15])
  * T5 — unify tasks as text-to-text; large-scale transfer learning. ([arXiv][16])

* Scaling laws & data/compute optimality — guides model/data sizing and budgets. ([arXiv][17])

* Chinchilla compute-optimal training — “more data per parameter” rule-of-thumb. ([arXiv][18])

* Massive data corpora (open) — The Pile (text), LAION-5B (image-text). ([arXiv][19])

* Alignment from human preferences

  * RLHF concept — learn reward models from human comparisons. ([arXiv][20])
  * InstructGPT — PPO-based fine-tuning to follow instructions. ([NeurIPS Proceedings][21])
  * PPO algorithm (RL backbone). ([arXiv][22])
  * DPO — preference optimization without explicit RL/reward model. ([NeurIPS Proceedings][23])

* Reasoning & tool-use prompting

  * Chain-of-Thought; Self-Consistency — elicit multi-step reasoning. ([arXiv][24])
  * ReAct — interleave reasoning with actions/tool calls. ([arXiv][25])
  * Toolformer — self-learned API/tool use. ([arXiv][26])

* Systems-level scaling for training

  * Model/parallel training: Megatron-LM; ZeRO (DeepSpeed). ([arXiv][27])
  * Sparse Mixture-of-Experts: MoE layer; GShard; Switch Transformer. ([OpenReview][28])
  * High-throughput attention kernels: FlashAttention (and successors). ([arXiv][29])

* Inference efficiency at scale

  * KV-cache memory management: vLLM / PagedAttention. ([arXiv][30])
  * Speculative decoding — exact-distribution speedups using draft models. ([arXiv][31])

* Parameter-efficient adaptation & quantization

  * LoRA — low-rank adapters for cheap fine-tuning. ([arXiv][32])
  * QLoRA — 4-bit quantized finetuning with NF4/paged optimizers. ([arXiv][33])

* Multimodality & generative media foundations

  * CLIP — contrastive image–text pretraining enabling zero-shot transfer. ([arXiv][34])
  * Diffusion models (DDPM) & Latent Diffusion — practical, high-fidelity image generation (basis for modern multimodal LLMs). ([NeurIPS Proceedings][35])

[1]: https://gwern.net/doc/ai/nn/1986-rumelhart-2.pdf?utm_source=chatgpt.com "Learning representations by back-propagating errors - Gwern"
[2]: https://proceedings.mlr.press/v15/glorot11a.html?utm_source=chatgpt.com "Deep Sparse Rectifier Neural Networks - PMLR"
[3]: https://proceedings.mlr.press/v37/ioffe15.html?utm_source=chatgpt.com "Batch Normalization: Accelerating Deep Network Training by Reducing ..."
[4]: https://jmlr.org/papers/v15/srivastava14a.html?utm_source=chatgpt.com "Dropout: A Simple Way to Prevent Neural Networks from Overfitting"
[5]: https://papers.nips.cc/paper/2012/file/c399862d3b9d6b76c8436e924a68c45b-Paper.pdf?utm_source=chatgpt.com "ImageNet Classification with Deep Convolutional Neural Networks - NIPS"
[6]: https://arxiv.org/abs/1710.03740?utm_source=chatgpt.com "Mixed Precision Training"
[7]: https://arxiv.org/abs/1412.6980?utm_source=chatgpt.com "Adam: A Method for Stochastic Optimization"
[8]: https://arxiv.org/abs/1607.06450?utm_source=chatgpt.com "Layer Normalization"
[9]: https://arxiv.org/abs/1706.03762?utm_source=chatgpt.com "Attention Is All You Need"
[10]: https://arxiv.org/abs/1508.07909?utm_source=chatgpt.com "Neural Machine Translation of Rare Words with Subword Units"
[11]: https://arxiv.org/abs/1904.09751?utm_source=chatgpt.com "The Curious Case of Neural Text Degeneration"
[12]: https://arxiv.org/abs/2104.09864v5?utm_source=chatgpt.com "RoFormer: Enhanced Transformer with Rotary Position Embedding"
[13]: https://arxiv.org/abs/1911.02150?utm_source=chatgpt.com "Fast Transformer Decoding: One Write-Head is All You Need"
[14]: https://cdn.openai.com/research-covers/language-unsupervised/language_understanding_paper.pdf?utm_source=chatgpt.com "Improving Language Understanding by Generative Pre-Training"
[15]: https://arxiv.org/abs/1810.04805?utm_source=chatgpt.com "BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding"
[16]: https://arxiv.org/abs/1910.10683?utm_source=chatgpt.com "Exploring the Limits of Transfer Learning with a Unified Text-to-Text Transformer"
[17]: https://arxiv.org/abs/2001.08361?utm_source=chatgpt.com "[2001.08361] Scaling Laws for Neural Language Models - arXiv.org"
[18]: https://arxiv.org/abs/2203.15556?utm_source=chatgpt.com "Training Compute-Optimal Large Language Models"
[19]: https://arxiv.org/abs/2101.00027?utm_source=chatgpt.com "The Pile: An 800GB Dataset of Diverse Text for Language Modeling"
[20]: https://arxiv.org/abs/1706.03741?utm_source=chatgpt.com "[1706.03741] Deep reinforcement learning from human preferences - arXiv.org"
[21]: https://proceedings.neurips.cc/paper_files/paper/2022/file/b1efde53be364a73914f58805a001731-Paper-Conference.pdf?utm_source=chatgpt.com "Training language models to follow instructions with human feedback"
[22]: https://arxiv.org/abs/1707.06347?utm_source=chatgpt.com "Proximal Policy Optimization Algorithms"
[23]: https://proceedings.neurips.cc/paper_files/paper/2023/file/a85b405ed65c6477a4fe8302b5e06ce7-Paper-Conference.pdf?utm_source=chatgpt.com "Direct Preference Optimization: Your Language Model is ... - NeurIPS"
[24]: https://arxiv.org/abs/2201.11903?utm_source=chatgpt.com "Chain-of-Thought Prompting Elicits Reasoning in Large Language Models"
[25]: https://arxiv.org/abs/2210.03629?utm_source=chatgpt.com "ReAct: Synergizing Reasoning and Acting in Language Models"
[26]: https://arxiv.org/abs/2302.04761v1?utm_source=chatgpt.com "Toolformer: Language Models Can Teach Themselves to Use Tools"
[27]: https://arxiv.org/abs/1909.08053?utm_source=chatgpt.com "Megatron-LM: Training Multi-Billion Parameter Language Models Using Model Parallelism"
[28]: https://openreview.net/forum?id=B1ckMDqlg&utm_source=chatgpt.com "Outrageously Large Neural Networks: The Sparsely-Gated Mixture-of ..."
[29]: https://arxiv.org/abs/2205.14135?utm_source=chatgpt.com "FlashAttention: Fast and Memory-Efficient Exact Attention with IO-Awareness"
[30]: https://arxiv.org/abs/2309.06180?utm_source=chatgpt.com "Efficient Memory Management for Large Language Model Serving with PagedAttention"
[31]: https://arxiv.org/abs/2211.17192?utm_source=chatgpt.com "Fast Inference from Transformers via Speculative Decoding"
[32]: https://arxiv.org/abs/2106.09685v1?utm_source=chatgpt.com "LoRA: Low-Rank Adaptation of Large Language Models"
[33]: https://arxiv.org/abs/2305.14314?utm_source=chatgpt.com "QLoRA: Efficient Finetuning of Quantized LLMs"
[34]: https://arxiv.org/abs/2103.00020?utm_source=chatgpt.com "Learning Transferable Visual Models From Natural Language Supervision"
[35]: https://proceedings.neurips.cc/paper/2020/hash/4c5bcfec8584af0d967f1ab10179ca4b-Abstract.html?utm_source=chatgpt.com "Denoising Diffusion Probabilistic Models - NeurIPS"
