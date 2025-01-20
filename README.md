# Kimi k1.5: Scaling Reinforcement Learning with LLMs


<div align="center" style="line-height: 1;">
  <a href="https://kimi.moonshot.com/" target="_blank" style="margin: 2px;">
    <img alt="Chat" src="https://img.shields.io/badge/%F0%9F%A4%96-Kimi_k1.5-blue" style="display: inline-block; vertical-align: middle;"/>
  </a>
</div>


<p align="center">
  <a href="k1_5.pdf"><b>Paper Link</b></a>
</p>

Language model pretraining with next token prediction has proved effective for scaling compute but is limited to the amount of available training data. Scaling reinforcement learning (RL) unlocks a new axis for the continued improvement of artificial intelligence, with the promise that large language models (LLMs) scale their training data by learning to explore with rewards, and thus also scaling compute. However, prior published work has not produced competitive results. In light of this, we report on the training practice of Kimi k1.5, our latest multi-modal LLM trained with RL, including RL training techniques, multi-modal data recipes, and infrastructure optimization. We study the training and test time scaling properties of RL with LLMs. Our approach is simplistic and shows that strong performance can be achieved without complex techniques such as Monte Carlo tree search, value functions, and process reward models. Notably, our system achieves state-of-the-art reasoning performance across multiple benchmarks and modalities---e.g., xx on AIME, xx on Codeforces, xx on MathVista---matching OpenAI's o1. The models can be accessed from https://kimi.ai.

## Model Performances


## Algorithms & Infrastructures


## Citation

```
@article{MoonshotAI,
  author = {Kimi Development Team},
  title = {Kimi k1.5: Scaling Reinforcement Learning with LLMs},
  year = {2025},
}
```
