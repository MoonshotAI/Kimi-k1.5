<p align="center">
  <img width="80%" src="images/Kimi_k1.5.svg">
</p>

# Kimi k1.5: Scaling Reinforcement Learning with LLMs

<p align="center">
  <b>the Kimi Team</b></a>
</p>


<p align="center">
  <a href="https://kimi.ai/"><img src="logo/logo.png" height="16" width="16" style="vertical-align:middle"> <b> Chat   </b></a>
  <a href="k1_5.pdf"><img src="logo/report.png" height="16" width="16" style="vertical-align:middle"><b> Report</b></a>
</p>

Language model pretraining with next token prediction has proved effective for scaling compute but is limited to the amount of available training data. Scaling reinforcement learning (RL) unlocks a new axis for the continued improvement of artificial intelligence, with the promise that large language models (LLMs) scale their training data by learning to explore with rewards, and thus also scaling compute. However, prior published work has not produced competitive results. In light of this, we report on the training practice of Kimi k1.5, our latest multi-modal LLM trained with RL, including RL training techniques, multi-modal data recipes, and infrastructure optimization. We study the training and test time scaling properties of RL with LLMs. Our approach is simplistic and shows that strong performance can be achieved without complex techniques such as Monte Carlo tree search, value functions, and process reward models. Notably, our system achieves state-of-the-art reasoning performance across multiple benchmarks and modalities---e.g., xx on AIME, xx on Codeforces, xx on MathVista---matching OpenAI's o1. The models can be accessed from https://kimi.ai.

## Model Performances


## Algorithms & Infrastructures

## Test Model by API
You can test Kimi k1.5 through the Kimi OpenPlatform. Fill out the test application form in [this link](https://forms.gle/TqZ9XQnPiJPddzhV8). We will contact you via email to provide a test account later.

Here's an example of calling Kimi k1.5
```python
cli = Client(
    api_key="$YOUR_KIMI_KEY",
    base_url="https://api.moonshot.ai/v1",
)

messages = [
    {
        "role": "user",
        "content": "The lengths of the two legs of a right triangle are 3 cm and 4 cm respectively. Find the length of the hypotenuse of this right triangle.",
    },
]

resp = cli.chat.completions.create(
    model="kimi-k1.5-preview",
    messages=messages,
    temperture=0.3,
    stream=True,
    max_tokens=8192,
)

for chunk in resp:
    print(chunk.choices[0].delta.content, end="")
```


## Citation

```
@article{MoonshotAI,
  author = {the Kimi Team},
  title = {Kimi k1.5: Scaling Reinforcement Learning with LLMs},
  year = {2025},
}
```
