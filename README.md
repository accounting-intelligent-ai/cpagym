
# RL-Accounting  会计强化学习

<a href="https://pypi.org/project/cpagym/">
<img src="https://raw.githubusercontent.com/accounting-intelligent-ai/cpagym/main/cpagym.png" width = "300" height = "300" alt="logo" align=center />
</a>

Redefining [Accounting](https://cpanlp.com/)!
Developed by **Bfsu Ai-Accounting Team** (c) 2023
[Github](https://github.com/accounting-intelligent-ai/cpagym)

[![PyPI - Python Version](https://img.shields.io/static/v1?label=pypi&message=v0.0.21&color=blue)](https://pypi.org/project/cpagym/)
[![Downloads](https://static.pepy.tech/badge/cpagym/week)](https://pepy.tech/project/cpagym)

## Install & Import 安装和导入
For detailed installation instructions, see the
[documentation](https://cpanlp.com/documentation).
```python
pip install cpagym
import gymnasium as gym
import cpagym as cg 
import torch
```

## Accounting Envs 主要会计环境
### 1. Moral_Hazard 道德风险
```python
env = gym.make("Moral_Hazard-v1")#Instantiate the Environment载入道德风险环境
state, info = env.reset(seed=2)#初始化
n_steps = 10
for _ in range(n_steps):
    action = env.action_space.sample()#随机行动
    state, reward, terminated, truncated, info = env.step(action)
    print(observation, reward, terminated, truncated, info )
    if terminated or truncated:
        observation, info = env.reset()
```

## Accounting  RL-Algorithm 会计强化学习算法
### 1. Train the Agent with DQN
#### Accounting  RL-Agent 会计强化学习代理人
```python
agent=cg.Agent(state_size=1,action_size=2)#Instantiate the Agent载入会计智能体
env = gym.make("Moral_Hazard-v1")
state, info = env.reset(seed=2)
action = agent.act(state, eps)#最优化行动
next_state, reward, done, _,_ = env.step(action)
agent.step(state, action, reward, next_state, done)
print(agent.memory.memory)
```
## 配套智能会计包CPANLP
<a href="https://pypi.org/project/cpanlp/">
<img src="https://raw.githubusercontent.com/accounting-intelligent-ai/cpanlp/main/cpanlp.png" width = "320" height = "120" alt="logo" align=center />
</a>

Check out: https://cpanlp.com/reinforcement