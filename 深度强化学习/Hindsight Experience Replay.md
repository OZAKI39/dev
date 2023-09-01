### Hindsight Experience Replay

（1）Universal Value Function Approximators (UVFA)

令G为可能的目标空间，每个目标g∈G对应奖励函数rg : S×A→R。每回合从分布p(s0,g)中随机采样一个状态-目标对，在整个回合中g保持不变。每个时间步中，智能体同时接收当前状态与当前目标作为输入，以此输出动作，即策略可表示为Π：S×G→A，得到奖励rt=rg(st, at)。

（2）A motivate example

考虑一个回合，该回合有一个状态序列 s1, s2, ..., sT与一个目标g≠s1, s2, ... , sT，并且在每个时间步内智能体获得-1的奖励。HER方法的核心在于用一个不同的目标点重新审视该条轨迹——该轨迹可能无法帮助学习如何到达状态g，但它确实告诉我们如何到达状态sT。我们可以将经验池中的g用sT替代，以更好地利用该信息。

（3）Multi-goal RL

在本问题中，研究如何训练智能体学习到达多个不同的目标点。我们使用状态s∈S和目标点g∈G训练策略函数与价值函数。

（4）Algorithm