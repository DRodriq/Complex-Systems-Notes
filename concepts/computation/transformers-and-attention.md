---
type: concept
domain: computation
related_domains: [dynamics, information]
provenance: mixed
status: developing
relates_to:
  - target: neural-networks
    relation: extends
  - target: concepts/information/shannon-entropy
    relation: overlaps
  - target: concepts/dynamics/chaos-theory
    relation: contrasts
tags: [transformers, attention, LLMs, architecture, self-attention, core]
---

# Transformers and Attention

> The architecture underlying modern large language models: a stack of self-attention layers and feed-forward blocks that processes entire sequences in parallel by computing weighted mixtures of token representations, replacing recurrence with direct global context.

## Orientation

The transformer (Vaswani et al., 2017, "Attention Is All You Need") is the architectural basis for GPT, BERT, and all major large language models. Its significance is not just practical — it represents a fundamental shift in how sequence processing is conceptualized. Rather than processing tokens one at a time through a recurrent state, transformers process all tokens simultaneously, with every token directly attending to every other. This change enables parallelism at training scale, long-range dependency modeling, and the emergent capabilities associated with very large models.

For this vault, transformers sit at the boundary of classical complexity science and modern AI. The architecture is not well described by the dynamical systems framing that applies to recurrent networks, but it has its own structure — the residual stream, attention as information routing, scaling laws — that connects to complexity science questions in different ways.

## Core

### The Problem Transformers Solve

Sequential data (text, speech, time series) has two structural challenges. First, elements can have dependencies across long distances — a word at position 1 may determine the meaning of a word at position 1000. Second, the relevant context for each position varies — not all prior tokens are equally informative.

Recurrent networks (RNNs, LSTMs) address both by maintaining a hidden state that is updated at each step. This is sequential — the hidden state at step t depends on step t-1 — which limits parallelism. And long-range dependencies are bottlenecked through the hidden state, which has finite capacity; information from step 1 is increasingly diluted by step 1000.

The transformer's answer is to abandon recurrence entirely and compute all positions in parallel, with every position attending directly to all others. The attention mechanism replaces the sequential bottleneck with global context at every layer.

### Self-Attention: The Core Mechanism

For a sequence of n tokens, each represented as a vector, self-attention produces a new representation for each token as a weighted sum of all token representations (including itself). The weights — the attention pattern — are computed from the tokens themselves, not fixed by position.

Formally, each token produces three vectors from its representation: a **query** Q, a **key** K, and a **value** V, via learned linear projections. The attention weight from token i to token j is the dot product of token i's query with token j's key, scaled and softmaxed. Token i's output is the weighted sum of all tokens' values, with these weights.

```
Attention(Q, K, V) = softmax(QK^T / √d_k) V
```

The scaling by √d_k (the key dimension) prevents the dot products from growing so large that the softmax saturates, which would cause vanishing gradients.

What this computes: each token's new representation is a context-sensitive mixture of the entire sequence's content, where the mixture weights are determined by learned pairwise relevance. A token can attend strongly to tokens far away if they are relevant, and weakly to adjacent tokens if they are not. The attention pattern is fully dynamic — it changes with every input.

### Multi-Head Attention

A single attention operation learns one notion of relevance. **Multi-head attention** runs h independent attention operations in parallel, each with its own Q, K, V projections, then concatenates and projects the outputs. Different heads learn to attend to different kinds of relationships simultaneously — syntactic dependencies, semantic similarity, positional proximity, coreference — without any explicit supervision.

The number of heads is a hyperparameter. In GPT-3, h=96 for the larger layers. Each head operates on a lower-dimensional subspace (d_k = d_model/h), so the total computation is similar to single-head attention at full dimension.

### The Transformer Block

A transformer is a stack of identical blocks. Each block has two sublayers:

1. **Multi-head self-attention** — compute new token representations as context-sensitive mixtures
2. **Position-wise feed-forward network** — a two-layer MLP applied independently to each token's representation

Each sublayer is wrapped with a **residual connection** (add the input to the output) and **layer normalization**. The residual connection is critical: it allows gradients to flow directly from the output to any earlier layer, enabling very deep stacks. The layer normalization stabilizes training by controlling activation scale.

The feed-forward sublayer is often overlooked but is significant: it operates on each token independently, with no cross-token interaction. The attention sublayer mixes information across tokens; the FFN processes each token's mixed representation further. At large scales, the FFN parameters dominate the parameter count and are thought to store factual associations.

### Positional Encoding

Attention is permutation-equivariant — the same attention pattern would be computed regardless of token order. To give the model positional information, position is injected as an additive encoding on the input embeddings. The original transformer used fixed sinusoidal encodings; modern LLMs use learned relative position encodings (RoPE, ALiBi) that generalize better to sequence lengths not seen in training.

### The Residual Stream Perspective

A useful way to read a transformer is as a residual stream — a vector at each position that flows through the network, with each attention head and FFN block reading from it and adding to it. Each component's contribution is additive; the stream accumulates information from all prior operations. This framing, from Anthropic's mechanistic interpretability work, makes clear that the transformer is not a pipeline where information flows sequentially but a parallel accumulation where multiple operations write to a shared representation.

This is also a departure from the classical dynamical systems framing of neural networks. The residual stream is not a trajectory through a fixed dynamical system — it is a representation being incrementally refined by a sequence of learned operations. The "dynamics" here are in the depth dimension of the network, not in a time dimension.

### Scaling Laws

Empirically, transformer performance on language modeling follows **scaling laws** — power law relationships between loss and model size (parameter count), training compute, and dataset size. These were documented by Kaplan et al. (2020) and refined by Hoffmann et al. (Chinchilla, 2022). For a given compute budget, there is an optimal allocation between model size and training tokens, with loss scaling as:

```
L(N, D) ∝ (N^α + D^β)^{-1}
```

where N is parameters and D is training tokens, and α, β are empirical constants near 0.5.

The significance of scaling laws for this vault: they are power laws in the same spirit as West's biological scaling laws and Barabási's network scaling laws. Whether they reflect the same underlying universality — whether the transformer is a system that exhibits complexity-science scaling for the same reasons that cities and metabolisms do — is an open question. See `synthesis/scaling-thread.md`.

## Connections

**Neural networks** (`concepts/computation/neural-networks.md`) — the transformer is built on the base neural network architecture; attention replaces recurrence but the training machinery (backpropagation, gradient descent, residual connections) is the same.

**Scaling thread** (`synthesis/scaling-thread.md`) — LLM scaling laws are power law relationships; the question of whether they reflect the same universality as biological and urban scaling is open.

**Computation and dynamics thread** (`synthesis/computation-and-dynamics-thread.md`) — where the dynamical systems framing of neural networks meets its limits in the transformer architecture; the thread addresses this directly.

**Information theory** (`concepts/information/INDEX.md`) — attention weights can be interpreted informationally: the entropy of the attention distribution at a head measures how diffuse or concentrated its context aggregation is. Mechanistic interpretability work uses mutual information to characterize what information flows through the residual stream.

## Sources

- Vaswani et al. (2017), "Attention Is All You Need" — the original transformer paper; not in vault sources yet
- Kaplan et al. (2020), "Scaling Laws for Neural Language Models" — the power law characterization
- Hoffmann et al. (2022), "Training Compute-Optimal Large Language Models" (Chinchilla) — revised scaling law recipe

## Open Questions

- Is the residual stream perspective the right dynamical framing for transformers? What mathematical structure best captures what the depth dimension is doing?
- Do the scaling laws reflect deep universality (same mechanism as biological scaling) or are they coincidental power laws from a different mechanism?
- What is the relationship between attention head specialization (syntactic, semantic, positional heads) and the concepts of functional modules in CAS agents?
- At what scale do qualitatively new capabilities emerge, and is this emergence in the complexity science sense — a phase transition — or something else?
- Does mechanistic interpretability (decomposing transformer computations into interpretable circuits) generalize to larger models, or is the residual stream too high-dimensional to decompose?
