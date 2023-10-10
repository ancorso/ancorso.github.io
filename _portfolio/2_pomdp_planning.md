---
title: "POMDP Planning"
excerpt: "Innovations in solving POMDPs with large state, action, and observation spaces<br/><br/><img src='/images/pomdps/betazero.jpg'>"
collection: portfolio
---

<style>
    .image-container {
        text-align: center;
    }
</style>

Partially observable Markov decision processes (POMDPs) can be used to model a wide range of real world problems from robotics, to games, to critical resource projects necessary for the green transition. Although studied since the 1960s, scalability of POMDP solvers is still a major challenge. Offline solvers often use some form of value iteration to compute optimal policies over a (limited) discrete set of states. They can handle long time horizons but don't scale well to larger problems, especially those with continuous states actions and observations. Online solvers often employ forward tree search from a root belief and can naturally scale to high dimensional problems, as well as incorporate non-Markov constraints. Their drawback is that they are typically limited to a shorter planning horizon due to the exponential expansion of the search tree. Since we primarily work on very large POMDPs, we have recently focused on improving forward-search methods. 


BetaZero: Combining Planning and Learning for Solving POMDPs
----
The key insight of our recent [paper](https://arxiv.org/abs/2306.00249), is that reinforcement learning can be used to estimate the value of unexplored states in a tree search. The insight is an extension of the popular [AlphaZero](https://www.deepmind.com/blog/alphazero-shedding-new-light-on-chess-shogi-and-go) algorithm to the partially observed setting. The algorithm is depicted below. We first convert the POMDP into a belief-state MDP and use a double progressive widening form of Monte Carlo tree search (MCTS). Then, through repeated interactions with the environment, we learn a value function and an approximately optimal policy from the data. These are used to improve the next round of MCTS planning by using the policy to select new actions and to approximate the value of unexplored states. The process is repeated until the performance of the algorithm converges. Check out the code [here](https://github.com/sisl/BetaZero.jl). 

<div class="image-container">
    <img src="/images/pomdps/betazero_summary.jpg" alt="BetaZero Depiction" class="single-image" width="90%" />
</div>

Below is a comparison to other state of the art POMDP solvers.
<div class="image-container">
    <img src="/images/pomdps/betazero_results.jpg" alt="BetaZero Results" class="single-image" width="90%" />
</div>

Constrained POMDP Planning
----
When planning in safety-critical settings, it is often preferable to formulate safety requirements as hard constraints on the planner, rather than penalizing violations in the reward function. Our recent [paper](https://arxiv.org/abs/2212.12154) extends the popular [POMCPOW and PFT](https://arxiv.org/abs/1709.06196) algorithms to incorporate constraints through dual ascent. The approach is depicted below. The planner maintains a lagrange multiplier parameter that is increased or decreased depending on the expected cost observed in the search tree. The reward is augmented with the lagrange-multipler-scaled cost to ensure constraint satisfaction. 

<div class="image-container">
    <img src="/images/pomdps/cpft.jpg" alt="C-PFT" class="single-image" width="40%" />
</div>

Rather than having to select a penalty parameter a priori, we can instead specify a hard constraint and the planner will maximize the reward subject to that constraint. We compare the approach to a penalty approach with various values of the penalty parameter and show that the constrained planner produces a solution at the pareto-optimal point. 

<div class="image-container">
    <img src="/images/pomdps/pareto_frontier.jpg" alt="C-PFT" class="single-image" width="40%" />
</div>

We are currently working on an extension of the algorithm that works with [options](https://people.cs.umass.edu/~barto/courses/cs687/Sutton-Precup-Singh-AIJ99.pdf), allowing us to search over longer planning horizons.  

<div class="image-container">
    <img src="/images/pomdps/cobets.jpg" alt="CoBeTs" class="single-image" width="40%" />
</div>


Ongoing Work
----
We are currently extending the work on POMDP planning a few directions
* Developing value-iteration-based solvers for large POMDPs in order to better handle long time horizons
* Dimensionality reduction of POMDPs using data-driven representation learning
* Incorporating constraints into offline solvers
 
