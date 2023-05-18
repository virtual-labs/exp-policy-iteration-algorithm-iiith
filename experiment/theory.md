# Policy Iteration

##  What is Policy Iteration?

Policy Iteration is a classic reinforcement learning algorithm used to find an optimal policy for Markov Decision Processes (MDPs). This theory document provides a concise overview of Policy Iteration, its key components, and the iterative process involved. We outline the steps involved in Policy Iteration and discuss its convergence properties, highlighting its significance in solving complex decision-making problems.

1. Introduction: Markov Decision Processes (MDPs) provide a framework for modeling decision-making problems in uncertain environments. The goal of MDPs is to find an optimal policy that maximizes the expected cumulative reward over time. Policy Iteration is an iterative algorithm that aims to discover this optimal policy.

2. Components of Policy Iteration: Policy Iteration consists of two main steps:

    2.1. Policy Evaluation: The first step is to evaluate the given policy's value function, which measures the expected cumulative reward when following that policy. The value function represents the expected utility or quality of being in a particular state. Policy evaluation involves solving a set of linear equations or performing iterative updates until convergence is reached.

    2.2. Policy Improvement: Once the value function of the current policy is obtained, the next step is to improve the policy. Policy improvement involves selecting actions that lead to higher value states based on the current value function. This step ensures that the policy becomes increasingly more optimal with each iteration. 
3. Iterative Process of Policy Iteration: Policy Iteration consists of iteratively performing policy evaluation and policy improvement until an optimal policy is obtained. The algorithm begins with an initial policy and repeats the following steps:

    3.1. Policy Evaluation: Given the current policy, evaluate the value function using either iterative methods or solving linear equations. Update the value function until convergence is achieved.

    3.2. Policy Improvement:Based on the updated value function, update the policy by selecting actions that maximize the expected cumulative reward. Repeat until the policy remains unchanged or convergence is reached.
    
4. Convergence of Policy Iteration: Policy Iteration is guaranteed to converge to an optimal policy as long as the number of states and actions is finite. The algorithm is guaranteed to converge in a finite number of iterations, where each iteration involves a complete policy evaluation and improvement. The number of iterations required to converge depends on the number of states and actions in the MDP.

5. Significance of Policy Iteration: Policy Iteration is a fundamental algorithm in reinforcement learning, providing a systematic and rigorous approach to find optimal policies for MDPs. Its ability to handle large state and action spaces makes it applicable to various real-world decision-making problems, including robotics, game playing, and resource allocation.

6. Conclusion: Policy Iteration is a powerful algorithm that combines policy evaluation and policy improvement to find optimal policies for MDPs. By iteratively refining the policy, it converges to a policy that maximizes the expected cumulative reward. Understanding the theoretical foundations and iterative process of Policy Iteration is crucial for applying this algorithm effectively to solve complex decision-making problems.

7. Code-Snippet:
![Policy Iteration](./images/policy-iteration.png)
