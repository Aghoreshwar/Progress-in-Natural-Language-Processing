# Constituency parsing

Consituency parsing aims to extract a constituency-based parse tree from a sentence that 
represents its syntactic structure according to a [phrase structure grammar](https://en.wikipedia.org/wiki/Phrase_structure_grammar).

Example:

                 Sentence (S)
                     |
       +-------------+------------+
       |                          |
     Noun (N)                Verb Phrase (VP)
       |                          |
     John                 +-------+--------+
                          |                |
                        Verb (V)         Noun (N)
                          |                |
                        sees              Bill

[Recent approaches](https://papers.nips.cc/paper/5635-grammar-as-a-foreign-language.pdf)
convert the parse tree into a sequence following a depth-first traversal in order to
be able to apply sequence-to-sequence models to it. The linearized version of the
above parse tree looks as follows: (S (N) (VP V N)).
 
### Penn Treebank

The Wall Street Journal section of the [Penn Treebank](https://catalog.ldc.upenn.edu/LDC99T42) is used for 
evaluating constituency parsers. Section 22 is used for development and Section 23 is used for evaluation.
Models are evaluated based on F1. Most of the below models incorporate external data or features.
For a comparison of single models trained only on WSJ, refer to [Kitaev and Klein (2018)](https://arxiv.org/abs/1805.01052).

| Model           | F1 score  |  Paper / Source |
| ------------- | :-----:| --- |
| Self-attentive encoder + ELMo (Kitaev and Klein, 2018) | 95.13 | [Constituency Parsing with a Self-Attentive Encoder](https://arxiv.org/abs/1805.01052) |
| Model combination (Fried et al., 2017) | 94.66 | [Improving Neural Parsing by Disentangling Model Combination and Reranking Effects](https://arxiv.org/abs/1707.03058) |
| In-order (Liu and Zhang, 2017) | 94.2 | [In-Order Transition-based Constituent Parsing](http://aclweb.org/anthology/Q17-1029) |
| Semi-supervised LSTM-LM (Choe and Charniak, 2016) | 93.8 | [Parsing as Language Modeling](http://www.aclweb.org/anthology/D16-1257) | 
| Stack-only RNNG (Kuncoro et al., 2017) | 93.6 | [What Do Recurrent Neural Network Grammars Learn About Syntax?](https://arxiv.org/abs/1611.05774) |
| RNN Grammar (Dyer et al., 2016) | ﻿93.3 | [Recurrent Neural Network Grammars](https://www.aclweb.org/anthology/N16-1024) |
| Transformer (Vaswani et al., 2017) | 92.7 | [Attention Is All You Need](https://arxiv.org/abs/1706.03762) |
| Semi-supervised LSTM (Vinyals et al., 2015) | 92.1  | [Grammar as a Foreign Language](https://papers.nips.cc/paper/5635-grammar-as-a-foreign-language.pdf) |
| Self-trained parser (McClosky et al., 2006) | 92.1 | [Effective Self-Training for Parsing](https://pdfs.semanticscholar.org/6f0f/64f0dab74295e5eb139c160ed79ff262558a.pdf) |

[Go back to the README](README.md)
