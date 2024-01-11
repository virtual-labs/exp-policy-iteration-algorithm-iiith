# Theory of Policy Iteration

## Introduction to Policy Iteration

Policy Iteration is an algorithm in reinforcement learning used within the context of Markov Decision Processes (MDPs). It is a structured method for finding the optimal policy - a strategy dictating the best actions in a given state - to maximize cumulative rewards in a stochastic decision-making environment.

### Markov Decision Processes (MDPs)

MDPs are a mathematical framework for sequential decision-making scenarios where outcomes are influenced by both randomness and the actions of a decision-maker. MDPs consist of:
- A set of states (S)
- A set of actions (A)
- Transition probabilities (P(s'|s,a))
- Reward functions (R(s,a,s'))
- Where *s* is the current state, *a* is the action taken, and *s'* is the next state

The objective in MDPs is to devise a policy (π) that optimizes the expected cumulative reward over time.

## Components of Policy Iteration

Policy Iteration involves two primary components:

1. **Policy Evaluation:** Computing the value function V(s) for a given policy π. This value function estimates the expected return starting from state s and following policy π thereafter.

2. **Policy Improvement:** Updating the policy π by choosing actions that yield higher returns based on the evaluated value function V(s).

## Mathematical Framework of Policy Iteration

### Step-by-Step Explanation

1. **Initialization:** Start with an arbitrary policy π₀ (typically random).

2. **Policy Evaluation:**
   - For each state s in S, calculate the value function V(s) under π₀.
   - V(s) is found by solving the Bellman equation:
     \[ V(s) = \sum_{s'} P(s'|s,π(s)) [R(s,π(s),s') + γV(s')] \]
   - γ is the discount factor, determining the importance of future rewards.

3. **Policy Improvement:**
   - Update the policy π₁ by choosing the action a in each state s that maximizes the expected utility:
     \[ π'(s) = \argmax_a \sum_{s'} P(s'|s,a) [R(s,a,s') + γV(s')] \]
   - If π'(s) = π(s) for all s, then π is the optimal policy. Otherwise, set π₀ = π' and return to Policy Evaluation.

### Convergence and Optimality

- **Convergence:** Policy Iteration is guaranteed to find the optimal policy in a finite number of iterations, given the finiteness of states and actions in MDP.

- **Optimality:** Upon convergence, the resulting policy is the optimal policy π*, and the corresponding value function V* is the solution to the Bellman optimality equation.

## Significance in Reinforcement Learning

Policy Iteration is a fundamental algorithm in reinforcement learning, especially suited for environments with well-defined states and actions. Its precision and efficiency in identifying optimal strategies make it invaluable in various applications, including robotics, strategic game design, and resource allocation strategies.

## Conclusion

Understanding the theory and mathematics behind Policy Iteration is crucial in applying it to solve complex decision-making problems effectively. It provides a systematic approach to iteratively refine policies, leading to optimal decision-making in stochastic environments.



7. Code-Snippet:
![Policy Iteration](./images/policy-iteration.png)
