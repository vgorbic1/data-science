## Reinforcement Learning (Online Learning)

Reinforcement Learning is a branch of Machine Learning, also called Online Learning. It is used 
to solve interacting problems where the data observed up to time **t** is considered to decide which action 
to take at time **t + 1**. It is also used for Artificial Intelligence when training machines to perform tasks such as walking. 
Desired outcomes provide the AI with reward, undesired with punishment. Machines learn through trial and error.

### Comparison of two common algoriths for reinforcement learning
*Upper Confidence Bound (UCB)*
- algorithm has a deterministic approach.
- requires update at every round.

*Thompson Sampling*
- algorithm has probabiliatic approach.
- can accomodate delayed feedback. (you do not have to update algorithm all the time)
- better empirical evidence.
