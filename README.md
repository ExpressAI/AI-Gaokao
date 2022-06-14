# Gaokao Benchmark for AI
<p align="center">
<img src="https://user-images.githubusercontent.com/59123869/173433076-de9036e2-3383-4670-b142-c5f9c27f54ed.png" width="500"/>
</p>


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
* listening
* cloze-multiple-choice
* cloze-hint
* reading-multiple-choice
* reading-cloze
* writing-grammar
* writing-essay




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

