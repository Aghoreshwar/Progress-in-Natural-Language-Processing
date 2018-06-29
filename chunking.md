# Chunking

Chunking is a shallow form of parsing that identifies continuous spans of tokens that form syntactic units such as noun phrases or verb phrases.

Example:

| Vinken | , | 61 | years | old |
| --- | ---| --- | --- | --- |
| B-NLP| I-NP | I-NP | I-NP | I-NP |

### Penn Treebank

The [Penn Treebank](https://catalog.ldc.upenn.edu/LDC99T42) is typically used for evaluating chunking.
Sections 15-18 are used for training, section 19 for development, and and section 20
for testing. Models are evaluated based on F1.

| Model           | F1 score  |  Paper / Source |
| ------------- | :-----:| --- |
| Low supervision (Søgaard and Goldberg, 2016) | 95.57 | [Deep multi-task learning with low level tasks supervised at lower layers](http://anthology.aclweb.org/P16-2038) |
| Suzuki and Isozaki (2008) | 95.15 | [Semi-Supervised Sequential Labeling and Segmentation using Giga-word Scale Unlabeled Data](https://aclanthology.info/pdf/P/P08/P08-1076.pdf) | 

[Go back to the README](README.md)
