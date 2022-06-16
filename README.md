# Gaokao Benchmark for AI
<p align="center">
<img src="https://user-images.githubusercontent.com/59123869/173433076-de9036e2-3383-4670-b142-c5f9c27f54ed.png" width="500"/>
</p>

## Introduction

### Q: What is Gaokao Benchmark?
Gaokao Benchmark aims to track how well we make progress towards human-level intelligence. It can not only provide a comprehensive evaluation of different tasks and domains that are practically useful in a real-world scenario, but also provide rich human performance so that AI systems can be
directly compared with humans over time.



### Q: How to download Gaokao datasets?

```
pip install --upgrade pip
pip install datalabs

from datalabs import load_dataset
dataset = load_dataset("gaokao2018_np1", "listening")
```
where 
* `gaokao2018_np1` is a datasetname that represents the version of Gaokao (e.g., year). You can find all dataset and subdataset names
  [here](https://explainaboard.inspiredco.ai/datasets) 
* `listening` is a subdataset name that represents question type in Gaokao. You can find all question types [here](xx)

Different types of questions in Gaokao English are formatted diversely. Below we will give detailed description.
* **listening**: Given a piece of listening material, choose the correct option to answer the question based on what you have heard.
* **cloze-multiple-choice**: Given a text with a number of blank positions, for each blank position, choose the appropriate option from the given choices to fill in.
* **cloze-hint**: Given a text with a number of blank positions, for each blank position, generate an appropriate word or phrase to fill in based on some hints.
* **reading-multiple-choice**: Given a reading passage, choose the correct option to answer the question based on the content of the article.
* **reading-cloze**: Given a text with a number of blank positions, for each blank position, choose the correct sentence from the options to fill it.
* **writing-grammar**: Correct a number of grammatical errors in the provided text.
* **writing-essay**: Write an essay according to the requirements of the problem.


<img width="800" alt="image" src="https://user-images.githubusercontent.com/50064641/173987806-49fc25ed-0b9c-4297-8f5d-560b19b5b3a8.png">


### Q: How to get scores of (i.e., evaluate) your AI systems?

#### 1. Using ExplainaBoard SDK


#### 2. Using ExplainaBoard Web Platform




### Q: How to submit your AI to Gaokao Benchmark?
* check out [documentation](https://github.com/neulab/explainaboard_client/tree/add_benchmark_submit/example/gaokao)


### Q: Where to browse Gaokao leaderboard?
* [here](https://explainaboard.inspiredco.ai/benchmark)


### Q: Add more papers into Gaokao Benchmark?
*  add dataset into DataLab following this [documentation](https://github.com/ExpressAI/DataLab/blob/main/docs/SDK/add_new_datasets_into_sdk.md)
*  update Gaokao benchmark config file and set up a pull request [here](https://github.com/neulab/explainaboard_web)

## Gaokao Robot - QIN
<img width="200" alt="image" src="https://user-images.githubusercontent.com/50064641/173988036-350ff126-3b3c-4e05-a9a6-d4d35245d32c.png">
We develop a Gaokao robot QIN.
