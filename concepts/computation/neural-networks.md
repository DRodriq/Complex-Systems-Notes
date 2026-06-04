---
type: concept
domain: computation
related_domains: [dynamics, complexity]
provenance: mixed
status: developing
relates_to:
  - target: transformers-and-attention
    relation: foundation-for
  - target: neuroevolution
    relation: overlaps
  - target: concepts/dynamics/chaos-theory
    relation: overlaps
  - target: concepts/complexity/edge-of-chaos
    relation: overlaps
tags: [neural-networks, deep-learning, backpropagation, connectionism, core]
---

# Neural Networks

> Parameterized function approximators built from layered compositions of linear transformations and nonlinearities, trained by gradient descent on a loss function — the dominant computational substrate of modern AI and the starting point for all contemporary deep learning architectures.

## Orientation

The neural network is the central computational object of the current AI wave and a connecting point between this vault's complexity science concerns and the engineering practice of machine learning. Understanding the classical feedforward network and its training is prerequisite for understanding every modern architecture — transformers, recurrent networks, convolutional networks — which are all variations on or extensions of this base.

For this vault, neural networks are significant in two directions: as the practical technology connecting to modern AI, and as dynamical systems whose behavior can be analyzed using the tools of nonlinear dynamics and complexity theory. The two framings are not always in contact in the literature; connecting them is part of the vault's synthesis agenda.

## Core

### The Basic Architecture

A feedforward neural network maps an input vector to an output vector through a sequence of layers. Each layer computes a linear transformation of its input (a matrix multiplication plus bias) followed by a pointwise nonlinear activation function. Composed across many layers, this produces a highly nonlinear function with the capacity to approximate arbitrary continuous functions (universal approximation theorem) given sufficient width or depth.

The expressiveness of deep networks relative to shallow ones is a major empirical finding: a function that requires exponentially many neurons in a shallow network may require only polynomially many in a deep one. This depth advantage is the basic motivation for deep learning.

**Activation functions** have evolved through the history of the field. Sigmoid and tanh were standard through the 1990s and 2000s, saturating at their extremes and causing vanishing gradients in deep networks. The ReLU (rectified linear unit) — f(x) = max(0, x) — solved this by having a constant gradient for positive inputs, enabling much deeper networks to be trained effectively. Modern architectures use variants (GELU, SiLU, Swish) that are smooth approximations to ReLU with better empirical performance.

### Training by Backpropagation

Training a neural network means finding weights that minimize a loss function measuring the discrepancy between network outputs and target outputs on a training set. The gradient of the loss with respect to the weights is computed by **backpropagation** — an application of the chain rule of calculus that efficiently propagates error signals from the output back through the layers.

Backpropagation gives the gradient; **gradient descent** uses it. The weights are iteratively updated in the direction that decreases the loss. In practice, **stochastic gradient descent** (SGD) computes gradients on random minibatches rather than the full dataset, providing regularization through noise and making training tractable at scale. Modern optimizers (Adam, AdaGrad, RMSprop) adapt the learning rate per-parameter based on the history of gradients.

The loss landscape — the hypersurface of loss values over weight space — is high-dimensional and non-convex. Understanding why gradient descent finds good solutions in such landscapes is an active research area. Key empirical findings: the landscape has many saddle points but few poor local minima in high dimensions; overparameterized networks (more parameters than training points) generalize better than classical theory would predict; flat minima tend to generalize better than sharp ones.

### The Vanishing Gradient Problem

In deep networks, gradients propagated through many layers tend to shrink (vanish) or grow (explode) exponentially. A gradient that vanishes means early layers receive no learning signal — the network cannot be trained end-to-end. This was the primary obstacle to deep learning through the 1990s.

The modern solution is architectural: **residual connections** (ResNets) add skip connections that allow gradients to flow directly from output to early layers, bypassing the intermediate transformations. **Layer normalization** and **batch normalization** control the scale of activations at each layer, keeping gradients in a productive range. These architectural innovations — not algorithmic changes — enabled the deep networks that power modern AI.

The vanishing gradient problem has a dynamical systems interpretation: it is the network's Jacobian having eigenvalues less than one, causing the gradient signal to contract as it propagates backward. The productive training regime requires eigenvalues near one — criticality in the dynamical systems sense. This connects to the edge-of-chaos training hypothesis. See `synthesis/computation-and-dynamics-thread.md`.

### Generalization and Overfitting

A network that memorizes the training set perfectly but fails on new data is overfitting — it has learned the noise in the training data rather than the underlying pattern. Classical statistical learning theory predicts that generalization improves with more data relative to parameters, and worsens as the model becomes more complex.

Modern deep learning violates the classical picture. Very large overparameterized networks generalize well, even after fitting the training data exactly. This **double descent** phenomenon — where test error initially increases with model size, then decreases again past a threshold — suggests that the classical bias-variance tradeoff does not fully describe deep learning. The implicit regularization properties of SGD, the inductive biases built into specific architectures, and the geometry of overparameterized loss landscapes all play roles that are not yet fully understood.

## Connections

**Transformers and attention** (`concepts/computation/transformers-and-attention.md`) — the transformer is a specialized neural network architecture. Understanding the base architecture is prerequisite; attention is the key architectural innovation on top of it.

**Neuroevolution** (`concepts/computation/neuroevolution.md`) — gradient-free alternative to backpropagation; evolves network architectures and weights using evolutionary algorithms. Most useful when gradients are unavailable or when architecture search is the problem.

**Neural networks as dynamical systems** (`synthesis/computation-and-dynamics-thread.md`) — the dynamical systems framing of neural computation; Lyapunov analysis, attractor geometry, edge-of-chaos training.

**Chaos theory** (`concepts/dynamics/chaos-theory.md`) — provides the mathematical tools for the dynamical systems framing of neural networks; eigenvalue analysis of the Jacobian is the direct application.

**Edge of chaos** (`concepts/complexity/edge-of-chaos.md`) — the hypothesis that neural networks at criticality train best is a direct application of the edge-of-chaos framework to deep learning.

## Sources

- `sources/papers/zhang-edge-of-chaos-nn-2021.md` — edge of chaos as guiding principle for modern NN training
- `sources/papers/nn-as-dynamical-system-shlizerman-2023.md` — neural networks as a new type of dynamical system

## Open Questions

- Why do overparameterized networks generalize? The double descent phenomenon is empirically robust but theoretically underdetermined.
- What is the geometry of trained network representations — how does structure in the weight space relate to structure in the data distribution?
- Is the edge-of-chaos training hypothesis empirically robust across architectures and scales, or specific to certain regimes?
- At what point does the dynamical systems framing of neural networks break down — specifically, does it apply to attention-based architectures?
