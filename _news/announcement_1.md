---
layout: post
title: I completed my Master's degree with a Cum Laude distinction!
date: 2020-12-15 16:11:00-0400
inline: false
---

My thesis was titled: "Credit Assignment for Surrogate Gradient Learning Rules in Spiking Neural Networks".

***

I was supervised by [Prof. dr. Lambert Schomaker](https://www.ai.rug.nl/~lambert/) and [Prof. dr. Tamalika Banerjee](https://www.rug.nl/staff/t.banerjee/cv?lang=en). The thesis was graded with a 9. You can find the abstract below.

***

Spiking Neural Networks (SNNs) offer the potential to compute using sparse binary signals in a biologically plausible fashion. Training SNNs is difficult because their output, a spike train, is non-differentiable. Recently, learning rules with surrogate gradients have been developed to overcome this. However, in the absence of an exact gradient that can be backpropagated, credit assignment for hidden layers becomes a complex problem.

To solve this, we draw on the idea of asymmetric backpropagation, where the non-locality constraint on traditional backpropagation is relaxed by using a feedback matrix instead of the transpose of the feedforward matrix during the backward pass. We choose the Kolen-Pollack algorithm \cite{kolen_pollack} and derive the equivalent feedback update rule for SuperSpike \cite{superspike}, giving rise to an adaptive feedback mechanism called Lambda Feedback. We also draw inspiration from Uniform Sign-concordant Feedback \cite{backward-wts-1} and propose two extensions to Lambda Feedback. As a baseline comparison, we use five static feedback mechanisms that have appeared in the literature. Here, the feedback weights are fixed at the start of the training and are not learned. To test the comparative performances of the different feedback methods, we use a combination of tasks from Machine Learning (XOR, MNIST) and Computational Neuroscience (spike train reproduction).

The results indicate that Lambda Feedback and its extensions outperform all static feedback mechanisms at higher learning rates for spike train reproduction. For the case of MNIST, the adaptive feedback regimes and symmetric feedback have stable training error profiles at higher learning rates, unlike the other static feedback mechanisms, which exhibit highly unstable behaviour and, thus, collapsed accuracies on the testing set. We also design several extensions to our baseline simulations for MNIST and show that our networks are robust to noise. Further, we demonstrate that using early stopping and rethinking the readout mechanism can help improve performance.