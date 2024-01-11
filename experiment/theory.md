# Theory of Policy Iteration

## Introduction to Policy Iteration

Policy Iteration is a methodical algorithm used in reinforcement learning to determine the optimal policy within Markov Decision Processes (MDPs). By systematically refining actions taken in various states, it maximizes the expected cumulative reward over time, accounting for both certainty and randomness in decision outcomes.

## Markov Decision Processes (MDPs)

MDPs are mathematical models for decision-making situations where outcomes are subject to both stochastic events and strategic choices. An MDP is defined by:

- **States (S):** The set of all possible scenarios or conditions the decision-maker may encounter.
- **Actions (A):** The set of all actions available to the decision-maker.
- **Transition Probabilities (P(s'|s,a)):** The probability of transitioning from the current state s to a new state s' given action a.
- **Reward Functions (R(s,a,s')):** The immediate reward received after transitioning from state s to state s' due to action a.
- **Discount Factor (γ):** A value between 0 and 1 that represents the degree to which future rewards are discounted relative to immediate rewards.

The aim is to establish a policy (π), mapping states to actions, that maximizes the total expected return over time.

## Components of Policy Iteration

Policy Iteration comprises two phases:

- **Policy Evaluation:** Calculates the value function V(s) for a policy π, estimating the total expected return starting from state s and subsequently following π.
- **Policy Improvement:** Modifies the policy π by selecting actions that lead to the highest expected return, as indicated by the value function V(s).

## Mathematical Framework of Policy Iteration

### Step-by-Step Explanation

1. **Initialization:**
   - Assign an arbitrary initial value function V(s) and policy π(s) for all states s ∈ S.

2. **Policy Evaluation:**
   - Set Δ to zero.
   - For each state s ∈ S:
     - Temporarily hold the current value V(s).
     - Update V(s) by calculating the expected return for all possible next states s':
       `V(s) = Σ P(s'|s,π(s)) [ R(s,π(s),s') + γV(s') ]`
     - Adjust Δ to the largest difference between the new and old values of V(s).
   - Continue this loop until Δ is smaller than a predefined small threshold θ, indicating convergence.

3. **Policy Improvement:**
   - Begin with the policy assumed to be stable (policy-stable = true).
   - For each state s ∈ S:
     - Identify the best action a based on the current value function V(s):
       `π(s) = argmax_a Σ P(s'|s,a) [ R(s,a,s') + γV(s') ]`
     - If the chosen action is different from the current policy's action, mark the policy as not stable (policy-stable = false).
   - If the policy is stable, terminate the iteration and return V and π; otherwise, proceed to the next iteration of Policy Evaluation.

### Convergence and Optimality

Policy Iteration converges to the optimal policy π* and corresponding value function V* within a finite number of steps, as long as the MDP has a finite number of states and actions. The final policy π* is guaranteed to satisfy the Bellman optimality equation, ensuring it is the most advantageous policy.

## Significance in Reinforcement Learning

Policy Iteration is a foundational tool in reinforcement learning. Its ability to systematically find optimal strategies across well-defined state and action spaces makes it invaluable for complex applications such as autonomous robotics, strategic gameplay, and efficient resource allocation.

## Conclusion

A thorough grasp of Policy Iteration's theoretical underpinnings and its mathematical execution is indispensable for effectively solving intricate decision-making problems. The algorithm's rigorous process ensures the derivation and optimization of decision-making strategies, leading to the best possible outcomes in probabilistic environments.



## Code-Snippet:
![Policy Iteration](./images/policy-iteration.png)
