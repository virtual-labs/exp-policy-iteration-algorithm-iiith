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

1. **Initialization:** 
   Assign an initial value function V(s) and policy π(s) for all states s in S.

2. **Policy Evaluation:**
   - Initialize Δ to 0.
   - Iterate over each state s in S:
     - Temporarily store the current value V(s).
     - Update V(s) using the expected return from policy π, considering all possible next states s':
       \[ V(s) \leftarrow \sum_{s'} P(s'|s,π(s)) \left[ R(s,π(s),s') + γV(s') \right] \]
     - Update Δ to the maximum difference between the new and old value of V(s).
   - Repeat until Δ is less than θ (a small positive number indicating convergence).

3. **Policy Improvement:**
   - Assume the policy is stable to begin with (policy-stable ← true).
   - For each state s in S:
     - Determine the best action a according to the current value function V(s):
       \[ a \leftarrow π(s) \]
       \[ π(s) \leftarrow \argmax_a \sum_{s'} P(s'|s,a) \left[ R(s,a,s') + γV(s') \right] \]
     - If this action is different from the current policy, the policy is not stable (policy-stable ← false).
   - If the policy is stable, stop and return V and π. Otherwise, return to Policy Evaluation.

### Convergence and Optimality

- **Convergence:** Policy Iteration is guaranteed to find the optimal policy in a finite number of iterations, given the finiteness of states and actions in MDP.

- **Optimality:** Upon convergence, the resulting policy is the optimal policy π*, and the corresponding value function V* is the solution to the Bellman optimality equation.

## Significance in Reinforcement Learning

Policy Iteration is a fundamental algorithm in reinforcement learning, especially suited for environments with well-defined states and actions. Its precision and efficiency in identifying optimal strategies make it invaluable in various applications, including robotics, strategic game design, and resource allocation strategies.

## Conclusion

Understanding the theory and mathematics behind Policy Iteration is crucial in applying it to solve complex decision-making problems effectively. It provides a systematic approach to iteratively refine policies, leading to optimal decision-making in stochastic environments.



7. Code-Snippet:
![Policy Iteration](./images/policy-iteration.png)
