# Theoretical Background

This document outlines the theoretical foundations that underpin the algorithms and decisions used in this project. Understanding these principles is essential for interpreting algorithm behavior and performance.

---

## Multi-Armed Bandit Problem

The Multi-Armed Bandit problem is a foundational framework in online learning and reinforcement learning. An agent repeatedly selects from multiple actions (arms), each associated with an unknown reward distribution.

At each time step:
1. An arm is selected
2. A reward is observed
3. The agent updates its knowledge

The objective is to maximize cumulative reward over time.

---

## Exploration–Exploitation Trade-Off

A core challenge in bandit problems is deciding between:
- **Exploration**: selecting less-known arms to gain information
- **Exploitation**: selecting arms believed to yield high reward

Optimal strategies balance both to avoid premature convergence and long-term regret.

---

## Regret Minimization

Regret quantifies the performance loss due to uncertainty:

\[
\text{Regret}(T) = \sum_{t=1}^{T} \left( r^* - r_t \right)
\]

Where:
- \( r^* \) is the reward of the optimal arm
- \( r_t \) is the reward obtained at time \( t \)

Effective bandit algorithms aim to minimize regret over time.

---

## Upper Confidence Bound (UCB)

The UCB algorithm selects arms based on optimism in the face of uncertainty:

\[
UCB_i(t) = \bar{x}_i + \sqrt{\frac{2 \ln t}{n_i}}
\]

Where:
- \( \bar{x}_i \) is the empirical mean reward
- \( n_i \) is the number of times arm \( i \) has been selected
- \( t \) is the current time step

This formulation ensures systematic exploration of uncertain arms.

---

## Thompson Sampling

Thompson Sampling is a Bayesian approach to the bandit problem:

- Rewards are modeled probabilistically
- Posterior distributions represent belief about each arm’s reward
- Arms are selected by sampling from these distributions

For binary rewards, Beta distributions are used due to conjugacy with Bernoulli likelihoods.

---

## Application to CTR Optimization

CTR optimization aligns naturally with the bandit framework:
- Ads correspond to arms
- Click events correspond to rewards
- User interactions arrive sequentially

Bandit algorithms provide principled, real-time solutions for adaptive ad allocation.

---

## Theoretical Significance

These algorithms form the foundation of:
- Online recommendation systems
- Real-time bidding platforms
- Adaptive experimentation systems

Understanding their theory is critical for building scalable and reliable decision-making systems.

---

## Conclusion

The theoretical concepts presented here justify the use of Multi-Armed Bandit algorithms for CTR optimization and explain the performance improvements observed in adaptive strategies over static approaches.
