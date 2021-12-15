# Reinforcement Learning

Contents of **Reinforcement Learning**

* [Image](): folder containing images used in README
* [Reinforcement_Learning_TaxiCab-3.ipynb](https://github.com/cissyyang1014/DataScience_and_MachineLearning/blob/main/ReinforcementLearning/Reinforcement_Learning_TaxiCab-3.ipynb): Jupyter notebook file, provided by Dr. Randy Davila, containing
  * a. Introduction of programming with the OpenAi gym environment
  * b. Introduction of Reinforcement Learning with the Q-Learning Algorithm
  * c. Implement using the example of the Taxi-v3 environment.

![image](https://github.com/cissyyang1014/DataScience_and_MachineLearning/blob/main/ReinforcementLearning/Image/Reinforcement-Learning-in-ML-TV.jpg)

### A Short Summary

# Reinforcement Learning

Unlike supervised and unsupervised learnings, reinforcement learning has a feedback type of algorithm. It is on the many research fields on a global scale, as it is a big help to technologies like AI. The reinforcement learning does not need labeled input/output pairs, it focuses on fiding a suitable action model that maximizes the total cumulative reward of the agent. It is a sequential decision making process (a Markov decision process), and the algorithm learns the labels through experience. 

![image](https://github.com/cissyyang1014/DataScience_and_MachineLearning/blob/main/ReinforcementLearning/Image/reinforcement-learning-fig1-700.jpg)

* State Space: <img src="https://latex.codecogs.com/svg.image?S_t&space;\in&space;S" title="S_t \in S" />
* Action Space: <img src="https://latex.codecogs.com/svg.image?A_t&space;\in&space;A" title="A_t \in A" />
* Reward Value: <img src="https://latex.codecogs.com/svg.image?R_t&space;\in&space;R" title="R_t \in R" />

Define the probabilibity of state <img src="https://latex.codecogs.com/svg.image?s'" title="s'" /> and reward <img src="https://latex.codecogs.com/svg.image?r" title="r" /> given state <img src="https://latex.codecogs.com/svg.image?s" title="s" /> and action <img src="https://latex.codecogs.com/svg.image?a" title="a" /> as <img src="https://latex.codecogs.com/svg.image?\mathbb{P}(s',r|s,a)" title="\mathbb{P}(s',r|s,a)" />

#### Episode

For <img src="https://latex.codecogs.com/svg.image?t=0,1,2,..." title="t=0,1,2,..." />, the episode is <img src="https://latex.codecogs.com/svg.image?S_0,&space;A_0,&space;R_1,&space;S_1,&space;A_1,&space;R_2,&space;...,&space;R_T" title="S_0, A_0, R_1, S_1, A_1, R_2, ..., R_T" />.

#### Agent Goal

Maximize the total amount of reward.

#### The Discounted Return:

For <img src="https://latex.codecogs.com/svg.image?0&space;\le&space;\gamma&space;\le&space;1" title="0 \le \gamma \le 1" />, 
<img src="https://latex.codecogs.com/svg.image?G_t=R_{t&plus;1}&plus;\gamma&space;R_{t&plus;2}&plus;\gamma^2&space;R_{t&plus;3}&plus;..." title="G_t=R_{t+1}+\gamma R_{t+2}+\gamma^2 R_{t+3}+..." />

When <img src="https://latex.codecogs.com/svg.image?r=0" title="r=0" />, it is the immediate return.

#### Policy

The policy is a mapping from states to probabilities of selecting each possible action.

Define the probability of action <img src="https://latex.codecogs.com/svg.image?a" title="a" /> if state <img src="https://latex.codecogs.com/svg.image?s" title="s" /> as <img src="https://latex.codecogs.com/svg.image?\pi&space;(a|s)" title="\pi (a|s)" />. 

Given a fixed policy <img src="https://latex.codecogs.com/svg.image?\pi" title="\pi" />,

* <img src="https://latex.codecogs.com/svg.image?V_{\pi}(s)=\mathbb{E}_{\pi}[G_t|S_t=s]" title="V_{\pi}(s)=\mathbb{E}_{\pi}[G_t|S_t=s]" />
* <img src="https://latex.codecogs.com/svg.image?q_{\pi}(s,a)=\mathbb{E}_{\pi}[G_t|S_t=s,A_t=a]" title="q_{\pi}(s,a)=\mathbb{E}_{\pi}[G_t|S_t=s,A_t=a]" />

## Q-Learning

1. Initialize <img src="https://latex.codecogs.com/svg.image?Q(s,a)=0" title="Q(s,a)=0" />
2. <img src="https://latex.codecogs.com/svg.image?\pi" title="\pi" /> is the policy of choosing <img src="https://latex.codecogs.com/svg.image?argmax_a&space;Q(s,a)" title="argmax_a Q(s,a)" /> in state <img src="https://latex.codecogs.com/svg.image?s" title="s" /> with probability <img src="https://latex.codecogs.com/svg.image?1-\epsilon" title="1-\epsilon" />
3. Experience the environment and collect episodes (relabeling->update <img src="https://latex.codecogs.com/svg.image?Q" title="Q" /> ->relabeling-> update <img src="https://latex.codecogs.com/svg.image?Q" title="Q" /> ->...)

<img src="https://latex.codecogs.com/svg.image?Q(S_t,&space;A_t)\leftarrow&space;Q(S_t,&space;A_t)&plus;\alpha[G_t-Q(S_t,&space;A_t)]" title="Q(S_t, A_t)\leftarrow Q(S_t, A_t)+\alpha[G_t-Q(S_t, A_t)]" />

<img src="https://latex.codecogs.com/svg.image?G_t=R_{t&plus;1}&plus;\gamma&space;R_{t&plus;2}&plus;\gamma^2&space;R_{t&plus;3}&plus;...=R_{t&plus;1}&plus;\gamma&space;(R_{t&plus;2}&plus;\gamma&space;R_{t&plus;3}&plus;...)" title="G_t=R_{t+1}+\gamma R_{t+2}+\gamma^2 R_{t+3}+...=R_{t+1}+\gamma (R_{t+2}+\gamma R_{t+3}+...)" />

Thus, <img src="https://latex.codecogs.com/svg.image?G_t=R_{t&plus;1}&plus;\gamma&space;G_{t&plus;1}" title="G_t=R_{t+1}+\gamma G_{t+1}" />.

So, <img src="https://latex.codecogs.com/svg.image?Q(S_t,&space;A_t)\leftarrow&space;Q(S_t,&space;A_t)&plus;\alpha[R_{t&plus;1}&plus;\gamma_{max}Q(S_{t&plus;1},A_{t&plus;1})-Q(S_t,A_t)]" title="Q(S_t, A_t)\leftarrow Q(S_t, A_t)+\alpha[R_{t+1}+\gamma_{max}Q(S_{t+1},A_{t+1})-Q(S_t,A_t)]" />.
