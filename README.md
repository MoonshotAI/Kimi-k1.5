<p align="center">
  <img width="80%" src="images/kimi_k1.5.jpeg">
</p>

# Kimi k1.5: Scaling Reinforcement Learning with LLMs

<p align="center">
  <b>Kimi Team</b></a>
</p>


<p align="center">
  <!-- <a href="https://kimi.ai/"><img src="logo/logo.png" height="16" width="16" style="vertical-align:middle"> <b> Chat   </b></a> -->
  <a href="k1_5.pdf"><img src="logo/logo.png" height="16" width="16" style="vertical-align:middle"><b> Report</b></a>
</p>

Language model pretraining with next token prediction has proved effective for scaling compute but is limited to the amount of available training data. Scaling reinforcement learning (RL) unlocks a new axis for the continued improvement of artificial intelligence, with the promise that large language models (LLMs) can scale their training data by learning to explore with rewards. However, prior published work has not produced competitive results. In light of this, we report on the training practice of Kimi k1.5, our latest multi-modal LLM trained with RL, including its RL training techniques, multi-modal data recipes, and infrastructure optimization. Long context scaling and improved policy optimization methods are key ingredients of our approach, which establishes a simplistic, effective RL framework without relying on more complex techniques such as Monte Carlo tree search, value functions, and process reward models. Notably, our system achieves state-of-the-art reasoning performance across multiple benchmarks and modalities---e.g., 77.5 on AIME, 96.2 on MATH 500, 94-th percentile on Codeforces, 74.9 on MathVista---matching OpenAI's o1. Moreover, we present effective long2short methods that use long-CoT techniques to improve short-CoT models, yielding state-of-the-art short-CoT reasoning results---e.g., 60.8 on AIME, 94.6 on MATH500, 47.3 on LiveCodeBench---outperforming existing short-CoT models such as GPT-4o and Claude Sonnet 3.5 by a large margin (up to +550\%). 

<p align="center">
  <img width="100%" src="images/benchmark-long.jpeg">
</p>

<p align="center">
  <img width="100%" src="images/benchmark-short.jpeg">
</p>


## Algorithm & Infrastructure

<div style="display: flex; justify-content: space-between;">
  <img src="images/rlllm.jpeg" alt="The Reinforcement Learning Training System for LLM" style="width: 48%;">
  <img src="images/dividerollout.jpeg" alt="图像2" style="width: 48%;">
</div>

### Policy Optimization for RL-LLM

- Objective: Train a policy model $\pi_\theta$ to solve problems using a sequence of intermediate steps (Chain of Thought, CoT).
- Policy Optimization: Apply online policy mirror descent to iteratively improve the policy by solving a relative entropy regularized optimization problem.

### Large Scale RL-LLM System
- Iterative Process: Each iteration involves a rollout phase and a training phase.
  - Rollout Phase: Rollout workers generate trajectories by interacting with the model and store them in a replay buffer.
  - Training Phase: Trainer workers use the stored trajectories to update the model's weights.
- Partial Rollout Technique: Manage long and short trajectories by setting a fixed token budget for each rollout. Unfinished long trajectories are saved and continued in the next iteration, ensuring efficient use of computational resources.


<!-- ## Test Model by API
You can test Kimi k1.5 through the Kimi OpenPlatform. Fill out the test application form in [this link](https://forms.gle/TqZ9XQnPiJPddzhV8). We will contact you via email to provide a test account later.

Here's an example of calling Kimi k1.5
```python
from openai import Client

client = Client(
    api_key="YOUR_KIMI_KEY",
    base_url="https://api.moonshot.ai/v1",
)

messages = [
    {
        "role": "user",
        "content": "The lengths of the two legs of a right triangle are 3 cm and 4 cm respectively. Find the length of the hypotenuse of this right triangle.",
    },
]

stream = client.chat.completions.create(
    model="kimi-k1.5-preview",
    messages=messages,
    temperature=0.3,
    stream=True,
    max_tokens=8192,
)

for chunk in stream:
    if chunk.choices[0].delta:
        if chunk.choices[0].delta.content:
            print(chunk.choices[0].delta.content, end="")

``` -->


## Citation

```
@article{MoonshotAI,
  author = {Kimi Team},
  title = {Kimi k1.5: Scaling Reinforcement Learning with LLMs},
  year = {2025},
}
```
