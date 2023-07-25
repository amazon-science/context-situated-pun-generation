## Context-Situated Pun Generation


## Overview

This repository includes the collected dataset from "Context-Situated Pun Generation" appearing at EMNLP 2022 (paper available on [amazon.science](https://www.amazon.science/publications/context-situated-pun-generation) or [arXiv](https://arxiv.org/abs/2210.13522)).

The original SemEval 2017 Task 7 dataset (Miller et al., 2017) contains puns that are either homographic (exploiting polysemy) or heterographic (exploiting phonological similarity to another word). 
We sample puns that contain both sense annotations and pun word annotations
from SemEval Task 7. From this set, we sample from the 500 most
frequent pun word/alter word pairs *(p<sub>w</sub>, a<sub>w</sub>)* and randomly sample 100
unique context words *C*. Combining the sampled pun pairs and context words, we collect 4,552
*(C, p<sub>w</sub>, a<sub>w</sub>)* instances for annotation.
Full details on the data collection can be found in the paper (see [Citation](README.md#citation) section).

## Sample Instance
The excerpt below shows a sample data instance:
```
context	        pun_word    alter_word	pun_word_sense	                                                                                        alter_word_sense	                                                                        new_pun     user_pun
25 cent,profit	charge	    charge	pay with a credit card; pay with plastic money; postpone payment by recording a purchase as a debt	energize a battery by passing a current through it in the direction opposite to discharge	yes	    The cashier said there was no charge for my battery.
```

## Description of Fields
- *context:* Context words *C*, represented as a comma-separated list of keyword phrases (our dataset).
- *pun_word:* Pun word *p<sub>w</sub>* (from SemEval 2017 Task 7).
- *alter_word:* Alter word *a<sub>w</sub>* (from SemEval 2017 Task 7).
- *pun_word_sense:* Word sense information for the pun word *S<sub>p<sub>w</sub></sub>* (retrieved from WordNet using SemEval annotated senses).
- *alter_word_sense:* Word sense information for the alter word *S<sub>a<sub>w</sub></sub>* (retrieved from WordNet using SemEval annotated senses).
- *new_pun:* whether the annotator could come up with a new pun using the given context keywords and pun/alter words (our dataset).
- *user_pun:* if *new_pun* is *yes*, the text of the human-written pun that incorporates both the context keywords and the pun word (our dataset).

## Data File
In this repository, we release the full dataset of 4,552 annotated instances in the <b>C</b>ontext-Sit<b>U</b>ated <b>P</b>un (<b>CUP</b>) dataset.
```
├── data
   └── context_situated_pun.csv (full dataset)
```
## Security

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.

## License

This library is licensed under the CC-BY-NC-4.0 License (see [LICENSE](LICENSE)).

## Citation

If using this dataset in any relevant work, please cite the following papers:
- The Context-SitUated Pun (CUP) dataset, [Context-Situated Pun Generation](https://www.amazon.science/publications/context-situated-pun-generation), EMNLP 2022
```
@inproceedings{sun2022context,
  title = {Context-Situated Pun Generation},
  author = {Sun, Jiao and Narayan-Chen, Anjali and Oraby, Shereen and Gao, Shuyang and Chung, Tagyoung and Huang, Jing and Liu, Yang and Peng, Nanyun},
  booktitle = {Proceedings of the 2022 Conference on Empirical Methods in Natural Language Processing (EMNLP)},
  year = {2022}
}
```
- The original SemEval-2017 Task 7 Dataset, [SemEval-2017 Task 7: Detection and Interpretation of English Puns](https://aclanthology.org/S17-2005/), SemEval 2017 (CC-BY-NC License)
```
@inproceedings{miller-etal-2017-semeval,
    title = "{S}em{E}val-2017 Task 7: Detection and Interpretation of {E}nglish Puns",
    author = "Miller, Tristan  and
      Hempelmann, Christian  and
      Gurevych, Iryna",
    booktitle = "Proceedings of the 11th International Workshop on Semantic Evaluation ({S}em{E}val-2017)",
    month = aug,
    year = "2017",
    address = "Vancouver, Canada",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/S17-2005",
    doi = "10.18653/v1/S17-2005",
    pages = "58--68",
    abstract = "A pun is a form of wordplay in which a word suggests two or more meanings by exploiting polysemy, homonymy, or phonological similarity to another word, for an intended humorous or rhetorical effect. Though a recurrent and expected feature in many discourse types, puns stymie traditional approaches to computational lexical semantics because they violate their one-sense-per-context assumption. This paper describes the first competitive evaluation for the automatic detection, location, and interpretation of puns. We describe the motivation for these tasks, the evaluation methods, and the manually annotated data set. Finally, we present an overview and discussion of the participating systems{'} methodologies, resources, and results.",
}
```