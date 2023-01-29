
# Accounting Gym-Env 智能会计强化学习虚拟环境

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
```

## Accounting Envs 主要会计环境
1. Moral_Hazard 道德风险
```python
env = gym.make("Moral_Hazard-v1")
observation, info = env.reset(seed=2)
n_steps = 10
for _ in range(n_steps):
    action = env.action_space.sample()
    observation, reward, terminated, truncated, info = env.step(action)
    print(observation, reward, terminated, truncated, info )
    if terminated or truncated:
        observation, info = env.reset()
```
2. AsymmetricInfo 信息不对称
```python
env = gym.make("AsymmetricInfo-v1")
observation, info = env.reset(seed=2)
n_steps = 20
for _ in range(n_steps):
    action = env.action_space.sample()
    observation, reward, terminated, truncated, info  = env.step(action)
    print(observation, reward, terminated, truncated, info )
    if terminated or truncated:
        observation, info = env.reset()
```
3. Inventory 存货管理
```python
env = gym.make("Inventory-v1")
observation, info = env.reset(seed=2)
n_steps = 30
#plot demand
env.plot_demand()        
for _ in range(n_steps):
    action = env.action_space.sample()
    observation, reward, terminated, truncated, info  = env.step(action)
    print(observation, reward, terminated, truncated, info )
    if terminated or truncated:
        observation, info = env.reset()
```
## 配套智能会计包CPANLP
<a href="https://pypi.org/project/cpanlp/">
<img src="https://raw.githubusercontent.com/accounting-intelligent-ai/cpanlp/main/cpanlp.png" width = "320" height = "120" alt="logo" align=center />
</a>

Check out: https://cpanlp.com/reinforcement