# Methodology

This project adopts a structured, experiment-driven methodology to study **Click-Through Rate (CTR) optimization** using **Multi-Armed Bandit (MAB)** algorithms. The methodology is designed to reflect **real-world online decision systems**, where learning and action occur simultaneously under uncertainty.

The overall workflow is divided into four progressive analytical stages, each implemented as an independent notebook while contributing to a unified project pipeline.

---

## 1. Problem Formulation

The ad selection task is modeled as a **Multi-Armed Bandit problem**, where:

- Each advertisement represents an *arm*
- Each user interaction represents a *round*
- A reward of `1` is received if the ad is clicked, otherwise `0`
- The objective is to maximize **cumulative reward (total clicks)**

This formulation naturally captures the **exploration–exploitation trade-off** present in online advertising systems.

---

## 2. Data Understanding and Exploration

Before applying learning algorithms, exploratory data analysis is conducted to:

- Examine click distributions across ads
- Identify variance in ad performance
- Understand baseline CTR behavior

This step is purely diagnostic and does not influence model decisions, ensuring that learning remains unbiased and online in nature.

---

## 3. Baseline Observed-Data Strategy

A simple observed-data approach is implemented as a reference baseline:

- Ads are selected based on historical click counts
- No uncertainty modeling is applied
- Exploration is minimal or absent

This strategy highlights the shortcomings of static or greedy decision systems and provides a benchmark for adaptive algorithms.

---

## 4. Upper Confidence Bound (UCB) Algorithm

The UCB algorithm introduces uncertainty-aware decision-making by:

- Combining empirical mean rewards with confidence bounds
- Encouraging exploration of less-sampled ads
- Gradually shifting toward exploitation as uncertainty decreases

Key characteristics:
- Deterministic selection
- Strong theoretical regret guarantees
- Suitable for explainable decision systems

---

## 5. Thompson Sampling (Bayesian Bandits)

Thompson Sampling adopts a probabilistic, Bayesian framework:

- Each ad’s CTR is modeled using a Beta distribution
- Posterior distributions are updated after each interaction
- Ads are selected by sampling from posterior beliefs

This approach provides a natural balance between exploration and exploitation and adapts efficiently to uncertainty.

---

## 6. Evaluation Strategy

Algorithms are evaluated using:

- Total cumulative clicks
- Ad selection frequency
- Learning dynamics over time

Comparative visualizations are used to analyze:
- Convergence speed
- Exploration behavior
- Stability of decision-making

---

## 7. Methodological Principles

The methodology emphasizes:
- Online learning over offline fitting
- Interpretability over black-box models
- Statistical reasoning over heuristic tuning

This ensures the project remains relevant to both academic study and industry applications.

---

## Summary

Through a progressive, modular methodology, this project demonstrates how bandit algorithms outperform naive strategies in CTR optimization tasks, offering a scalable and interpretable solution for real-time ad allocation systems.
