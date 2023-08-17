# Metacognitive Prompting Improves Understanding in Large Language Models
This repository contains datasets, model descriptions, the full set of prompts used in experiments, and corresponding experimental results.

## Datasets
We utilize multiple natural language understanding datasets for our experiments, selected from [GLUE](https://gluebenchmark.com) and [SuperGLUE](https://super.gluebenchmark.com/). For evaluation purposes, we utilize the development set corresponding to each task. The overview of datasets is shown below:

| **Task**    | **Dataset**      | **Input**                  | **Output**       | **Metric**                    |
|-------------|------------------|----------------------------|------------------|-------------------------------|
| Sentiment   | SST-2            | Single sentence            | Binary           | Accuracy                      |
| Similarity  | STS-B            | Sentence pair              | Continuous       | Pearson/Spearman Correlation  |
| Paraphrase  | QQP              | Question pair              | Binary           | F1/Accuracy                   |
| QA/NLI      | QNLI             | Question + passage         | Binary           | Accuracy                      |
| NLI         | WNLI, RTE, CB    | Sentence pair              | Binary/Ternary | F1/Accuracy                   |
| WSD         | WiC              | Sentence pair + target word| Binary           | Accuracy                      |
| coref.      | WSC              | Passage + pronouns         | Binary           | Accuracy                      |
| QA          | COPA             | Question + choices         | Binary           | Accuracy                      |

Here, QA stands for question answering, NLI is natural language inference, WSD is word sense disambiguation, and coref. is coreference resolution. Datasets can be obtained in "[./datasets](./datasets/)".

## Models 
In our evaluation, we consider five popular large language models (LLMs): the open-source models [Llama-2-13b-chat](https://arxiv.org/pdf/2307.09288.pdf) and [Vicuna-13b-v1.1](https://lmsys.org/blog/2023-03-30-vicuna/), and the closed-source models [PaLM-bison-chat](https://arxiv.org/pdf/2305.10403.pdf), GPT-3.5-turbo, and [GPT-4](https://arxiv.org/pdf/2303.08774.pdf).
For all models, we apply greedy decoding (i.e., temperature = 0) for response generation.

## Prompts
Metacognitive Prompting (MP) is inspired by human introspective reasoning processes. The figure below shows the alignment between human metacognitive pro-
cesses and the stages of MP for LLMs:
<div align="center">
    <img width="75%" alt="image" src="https://github.com/EternityYW/Metacognitive-Prompting/blob/main/image_sources/human_LLM_metacognition.png">
</div>

MP consists of five main stages: 1) understanding the input text, 2) making a preliminary judgment, 3) critically evaluating this preliminary analysis, 4) reaching a final decision accompanied by an explanation of the reasoning, and 5) evaluating the confidence level in the entire process. A sample question chosen from the Quora Question Pair (QQP) dataset demonstrates the overall MP process:
<div align="center">
    <img width="90%" alt="image" src="https://github.com/EternityYW/Metacognitive-Prompting/blob/main/image_sources/MP_illustration.png">
</div>

The diagram features three columns, from left to right, representing the high-level metacognitive stages, specific metacognitive prompts fed into the LLM, and the LLM's corresponding outputs. Prompts in the middle column are collectively fed into the LLM as a single input during the experiments.

For our experiments, we compare our proposed MP with standard prompting (SP) and chain-of-thought (CoT) prompting. Each of these is conducted under zero-shot and 5-shot learning settings. For exemplars used under 5-shot learning settings, they are randomly selected from the training set of each dataset. Each dataset has its own set of exemplars, where exemplar answers are obtained through human annotation.

The full set of prompts used when applying MP, StP, and CoT under zero-shot and 5-shot learning paradigms can be found in "[./prompts](./prompts/)".

## Experimental Results
The experimental results for each dataset can be found in "[./results](./results/)".
For each dataset, we experiment with three prompting methods in zero-shot and 5-shot learning scenarios across five LLMs. We report the best result after multiple experimental iterations.

Please refer to our full [paper](https://arxiv.org/pdf/2308.05342.pdf) for more details. 

## Citation
If you find this work helpful, please consider citing as follows:  

```ruby
@article{wang2023metacognitive,
  title={Metacognitive Prompting Improves Understanding in Large Language Models},
  author={Wang, Yuqing and Zhao, Yun},
  journal={arXiv preprint arXiv:2308.05342},
  year={2023}
}
```
