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
   Set an initial value function V(s) and policy π(s) for all states s in S.

2. **Policy Evaluation:**
   - Set Δ to zero.
   - For each state s in S:
     - Save the current value V(s).
     - Update V(s) by summing over all possible next states s':
       `V(s) = Σ P(s'|s,π(s)) [ R(s,π(s),s') + γV(s') ]`
     - Update Δ to the maximum difference between the new and old V(s).
   - Continue this process until Δ is smaller than a small positive number θ, indicating convergence.

3. **Policy Improvement:**
   - Start with the assumption that the policy is stable (policy-stable = true).
   - For each state s in S:
     - Find the best action a given the current value function V(s):
       `a = π(s)`
       `π(s) = argmax_a Σ P(s'|s,a) [ R(s,a,s') + γV(s') ]`
     - If the updated policy π(s) differs from the previous one, the policy is not yet stable (policy-stable = false).
   - If the policy is stable, end the process and return V and π; otherwise, go back to Policy Evaluation.

### Convergence and Optimality

- **Convergence:** Policy Iteration is guaranteed to find the optimal policy in a finite number of iterations, given the finiteness of states and actions in MDP.

- **Optimality:** Upon convergence, the resulting policy is the optimal policy π*, and the corresponding value function V* is the solution to the Bellman optimality equation.

## Significance in Reinforcement Learning

Policy Iteration is a fundamental algorithm in reinforcement learning, especially suited for environments with well-defined states and actions. Its precision and efficiency in identifying optimal strategies make it invaluable in various applications, including robotics, strategic game design, and resource allocation strategies.

## Conclusion

Understanding the theory and mathematics behind Policy Iteration is crucial in applying it to solve complex decision-making problems effectively. It provides a systematic approach to iteratively refine policies, leading to optimal decision-making in stochastic environments.



## Code-Snippet:
![Policy Iteration](./images/policy-iteration.png)
