# Metacognitive Prompting Improves Understanding in Large Language Models
This repository contains datasets, full set of prompting used in experiments, and corresponding experimental results.

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

Here, QA stands for question answering, NLI is natural language inference, WSD is word sense disambiguation, and coref. is coreference resolution. 

## Prompting
Metacognitive Prompting (MP) is inspired by human introspective reasoning processes. It consists of five main stages: 1) understanding the input text, 2) making a preliminary judgment, 3) critically evaluating this preliminary analysis, 4) reaching a final decision accompanied by an explanation of the reasoning, and 5) evaluating the confidence level in the entire process. A sample question chosen from the Quora Question Pair (QQP) dataset demonstrates the overall MP process:
<div align="center">
    <img width="90%" alt="image" src="https://github.com/EternityYW/Metacognitive-Prompting/blob/main/metacognitive_prompting_illustration.pdf">
</div>


## Experimental Results





