![](LongBench/misc/logo.gif)
# 📚 Short-LongBench (Powered by Promptfoo)
### Deeper Understanding and Reasoning on Realistic Long-context Multitasks

<p align="center">
    🌐 <a href="https://longbench2.github.io" target="_blank">Original Project Page</a> • 📚 <a href="https://arxiv.org/abs/2412.15204" target="_blank">LongBench v2 Paper</a> • 📊 <a href="https://huggingface.co/datasets/THUDM/LongBench-v2" target="_blank">LongBench v2 Dataset</a>
</p>

## 🛠 About Short-LongBench
**Short-LongBench** is a specialized fork of the LongBench v2 dataset. While the original benchmark relied on multiple-choice questions (A, B, C, D) for reliability, **Short-LongBench** transitions these tasks into **open-ended generative evaluations**. 

By removing the multiple-choice constraints, we test the model's ability to extract and synthesize answers directly from long contexts without being "guided" by provided options. To maintain evaluation rigour, we utilize **Promptfoo** for semantic similarity testing against the original ground-truth answers.

## 🚀 Key Changes in this Version
- **Open-Ended Evaluation**: Models are no longer provided with A/B/C/D options. They must generate the answer from the context.
- **Promptfoo Integration**: Switched from custom inference scripts to `promptfoo` for side-by-side model comparison.
- **Semantic Scoring**: Evaluation is performed using semantic vector similarity (embeddings) rather than exact string matching, allowing for natural variations in model phrasing.
- **OpenRouter Support**: Configured to evaluate next-generation models like **MiMo**, **Qwen 2.5**, and **MiniMax** via OpenRouter.

## ⚙️ How to Evaluate with Promptfoo

### 1. Installation
Ensure you have Node.js installed, then install Promptfoo:
```bash
npm install -g promptfoo
```

### 2. Prepare the Data
The dataset is transformed from the original LongBench v2 JSON format into Promptfoo test cases. A transformation script maps the original `answer` key (e.g., "B") to the corresponding text in `choice_B` to create a ground-truth reference for semantic comparison.

### 3. Run Evaluation
Set your API key and run the eval:
```bash
export OPENROUTER_API_KEY=your_key_here
promptfoo eval
```

To view the results in a web-based matrix:
```bash
promptfoo view
```

## 📊 Current Results (Updating...)
*The table below will be updated with performance metrics comparing MiMo, Qwen, and MiniMax on the open-ended Short-LongBench tasks.*

| Model | Avg. Semantic Similarity | Hard Tasks | Easy Tasks |
| :--- | :--- | :--- | :--- |
| **MiniMax-Text-01** | TBD | TBD | TBD |
| **Qwen-2.5-72B** | TBD | TBD | TBD |
| **MiMo (Preview)** | TBD | TBD | TBD |

---

## 📝 Original Research & Citation
This project is built upon the incredible work of the LongBench v2 researchers. If you use this dataset or benchmark, please cite the original authors:

```
@article{bai2024longbench2,
  title={LongBench v2: Towards Deeper Understanding and Reasoning on Realistic Long-context Multitasks}, 
  author={Yushi Bai and Shangqing Tu and Jiajie Zhang and Hao Peng and Xiaozhi Wang and Xin Lv and Shulin Cao and Jiazheng Xu and Lei Hou and Yuxiao Dong and Jie Tang and Juanzi Li},
  journal={arXiv preprint arXiv:2412.15204},
  year={2024}
}
```

<div style="text-align: center;">
  <img src="misc/length.png" width="600" />
</div>
<div style="text-align: center;">
  <img src="misc/table.png" width="700" />
</div>
