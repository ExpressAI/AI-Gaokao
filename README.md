# Gaokao Benchmark for AI
<p align="center">
<img src="https://user-images.githubusercontent.com/59123869/173433076-de9036e2-3383-4670-b142-c5f9c27f54ed.png" width="500"/>
</p>


Table of contents
=================

<!--ts-->
* [What is Gaokao Benchmark?](#what-is-gaokao-benchmark?)
* [How to download Gaokao datasets?](#how-to-download-gaokao-datasets?)
* [How to Evaluate your Gaokao AI systems (Single Task)?](#how-to-evaluate-your-gaokao-ai-systems-(single-task)?)
* [How to submit your AI to Gaokao Benchmark?](#how-to-submit-your-ai-to-gaokao-benchmark?)
* [Where to browse Gaokao leaderboard?](#where-to-browse-gaokao-leaderboard?)
* [Add more papers into Gaokao Benchmark?](#add-more-papers-into-gaokao-benchmark)
<!--te-->







## What is Gaokao Benchmark
Gaokao Benchmark aims to track how well we make progress towards human-level intelligence. It can not only provide a comprehensive evaluation of different tasks and domains that are practically useful in a real-world scenario, but also provide rich human performance so that AI systems can be
directly compared with humans over time.



## How to download Gaokao datasets

```
pip install --upgrade pip
pip install datalabs

from datalabs import load_dataset
dataset = load_dataset("gaokao2018_np1", "listening")
```
where 
* `gaokao2018_np1` is a dataset name that represents the version of Gaokao (e.g., year). You can find all dataset and subdataset names
  [here](https://explainaboard.inspiredco.ai/datasets) 
* `listening` is a subdataset name that represents question type in Gaokao. You can find all question types [here](xx)

Different types of questions in Gaokao English are formatted diversely. Below we will give detailed description. Example questions can be found in [INPUTS.md](INPUTS.md).
* **listening**: Given a piece of listening material, choose the correct option to answer the question based on what you have heard.
* **cloze-multiple-choice**: Given a text with a number of blank positions, for each blank position, choose the appropriate option from the given choices to fill in.
* **cloze-hint**: Given a text with a number of blank positions, for each blank position, generate an appropriate word or phrase to fill in based on some hints.
* **reading-multiple-choice**: Given a reading passage, choose the correct option to answer the question based on the content of the article.
* **reading-cloze**: Given a text with a number of blank positions, for each blank position, choose the correct sentence from the options to fill it.
* **writing-grammar**: Correct a number of grammatical errors in the provided text.
* **writing-essay**: Write an essay according to the requirements of the problem.


## How to Evaluate your Gaokao AI systems (Single Task)

### Preprocess system output for each question type
We have provided multiple ways for Gaokao system evaluation, before which, system outputs from different question types (i.e., `subdataset`) should be
processed into specific formats. Please see examples in [data/system_outputs](data/system_outputs).

* `listening`
* `cloze-multiple-choice`
* `cloze-hint`
* `reading-multiple-choice`
* `reading-cloze`
* `writing-grammar`
* `writing-essay`




### Method 1:  Using ExplainaBoard SDK
Install ExplainaBoard
```
pip install --upgrade pip  # recommending the newest version of pip.
pip install explainaboard
```

##### (1) Evaluate `listening`
```
explainaboard --task qa-multiple-choice --dataset gaokao2018_np1 --sub_dataset listening --system_outputs ./data/system_outputs/rst_2018_quanguojuan1_listening.json > report.json
```

##### (2) Evaluate `cloze-multiple-choice`
```
explainaboard --task cloze-multiple-choice --dataset gaokao2018_np1 --sub_dataset cloze-multiple-choice --system_outputs ./data/system_outputs/rst_2018_quanguojuan1_cloze_choice.json > report.json
```

##### (3) Evaluate `cloze-hint`
```
explainaboard --task cloze-generative --dataset gaokao2018_np1 --sub_dataset cloze-hint --system_outputs ./data/system_outputs/rst_2018_quanguojuan1_cloze_hint.json > report.json
```

##### (4) Evaluate `reading-multiple-choice`
```
explainaboard --task qa-multiple-choice --dataset gaokao2018_np1 --sub_dataset reading-multiple-choice --system_outputs ./data/system_outputs/rst_2018_quanguojuan1_reading_mc.json > report.json
```

##### (5) Evaluate `reading-cloze`
```
explainaboard --task cloze-multiple-choice --dataset gaokao2018_np1 --sub_dataset reading-cloze --system_outputs ./data/system_outputs/rst_2018_quanguojuan1_reading_dependent_cloze.json > report.json
```

##### (6) Evaluate `writing-grammar`
```
explainaboard --task grammatical-error-correction --dataset gaokao2018_np1 --sub_dataset writing-grammar --system_outputs ./data/system_outputs/rst_2018_quanguojuan1_gec.json > report.json
```

##### (7) Evaluate `writing-essay`
```
explainaboard --task conditional-generation --dataset gaokao2018_np1 --sub_dataset writing-essay --metrics bleu --system_outputs ./data/system_outputs/rst_writing_essay.tsv > report.json
```
**Notably, here we temporarily use the evaluation metric `bleu`. But if you want your generated essay being evaluated by human (high-school teachers), you can send us**
* the name of your submitted systems
* your explainaboard account (i.e., email)
Then we will find qualified evaluators for you.

 

### Method 2: Using ExplainaBoard Web Platform
An alternative way to test your Gaokao system w.r.t. each question type (e.g., listening) is using the ExplainaBoard web platform. Specifically,

* Access the explainaboard web - [dataset page](https://explainaboard.inspiredco.ai/datasets)
* Search Gaokao dataset and choose the one where system outputs are generated
* Click `test` in the `Leaderboard` column and then your will enter into a submission page for individual system
* Click `New`, fill in necessary information, and click `submit`

For your convenience, we detail how to fill in the submission form for each question type in Gaokao:

##### (1) Evaluate `listening`
* `System name`: whatever you like (but if different system outputs come from the same system, we suggest that you provide the same system name.
* `Task`: `qa-multiple-choice`
* `Use custom dataset?`: don't choose this
* `Dataset`: it depends on the dataset and subdataset name, for example: `gaokao2018_np1 writing-grammar`
* `Split`: test
* `Metrics`: `CorrectCount`
* `Make it private?`: it depends on your preference. But if it's set `private`, it will not be displayed in the public Gaokao Benchmark.
* `Shared Users`: Optional
* `Input Lang/Output Lang`: `en` (since so far, it only supports for English paper evaluation) 
* `System Details`: optional

For other types of questions (i.e., subdataset), ones can follow the above prompt to fill in the form, where the only differences exist in the 
`Task` and `Metrics`. We detail them below.

##### (2) Evaluate `cloze-multiple-choice`
* `Task`: `qa-multiple-choice`
* `Metrics`: `CorrectCount`


##### (3) Evaluate `cloze-hint`
* `Task`: `cloze-generative`
* `Metrics`: `CorrectCount`


##### (4) Evaluate `reading-multiple-choice`
* `Task`: `qa-multiple-choice`
* `Metrics`: `CorrectCount`

##### (5) Evaluate `reading-cloze`
* `Task`: `cloze-multiple-choice`
* `Metrics`: `CorrectCount`

##### (6) Evaluate `writing-grammar`
* `Task`: `grammatical-error-correction`
* `Metrics`: `SeqCorrectCount`

##### (7) Evaluate `writing-essay`
* `Task`: `conditional-generation`
* `Metrics`: `bleu`

Notably, **currently the generated essays are evaluated by the evaluation metric `bleu`. 
But if you want your generated essay being evaluated by human (high-school teachers),
you can send us**
* the name of your submitted systems
* your explainaboard account (i.e., email)
Then we will find qualified evaluators for you.




## How to submit your AI to Gaokao Benchmark
So far, the total number of subdatasets covered in Gaokao Benchmark is 70, it's troublesome if users process or upload them individually.
To further facilite users' evaluation, we provide an API that users can upload all 70 system outputs at one time. The general idea is:
* follow the [above description](https://github.com/ExpressAI/AI-Gaokao#preprocess-system-output-for-each-question-type) to preprocess system outputs for different question types and put all of them in a folder (e.g., `submission`) following
certain **order**
* run script provided below and then you can see your submission in ExplainaBoard web platform.


#### Check out detailed [documentation](https://github.com/neulab/explainaboard_client/tree/add_benchmark_submit/example/gaokao)


## Where to browse Gaokao leaderboard
* [here](https://explainaboard.inspiredco.ai/benchmark)


## Add more papers into Gaokao Benchmark
*  add dataset into DataLab following this [documentation](https://github.com/ExpressAI/DataLab/blob/main/docs/SDK/add_new_datasets_into_sdk.md)
*  update Gaokao benchmark config file and set up a pull request [here](https://github.com/neulab/explainaboard_web)
