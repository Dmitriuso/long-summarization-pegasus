# Long Summarization PEGASUS

## Short Introduction

PEGASUS model by Google was open sourced in July 2020: you can find more information about it in [Google AI blog](https://ai.googleblog.com/2020/06/pegasus-state-of-art-model-for.html), in the corresponding [academic paper](https://arxiv.org/pdf/1912.08777.pdf) and in [PEGASUS GitHub repository](https://github.com/google-research/pegasus).

If you use PEGASUS code or models published, please cite the paper:

```
@misc{zhang2019pegasus,
    title={PEGASUS: Pre-training with Extracted Gap-sentences for Abstractive Summarization},
    author={Jingqing Zhang and Yao Zhao and Mohammad Saleh and Peter J. Liu},
    year={2019},
    eprint={1912.08777},
    archivePrefix={arXiv},
    primaryClass={cs.CL}
}
```

PEGASUS release on GitHub was not initially destined for an arbitrary text summarization, but rather for evaluation testing. That is why one of fellow enthusiast researchers, [TheRockXu](https://github.com/TheRockXu), [forked](https://github.com/TheRockXu/pegasus-demo) the PEGASUS GitHub repository and made it work on arbitrary text.

[TheRockXu](https://github.com/TheRockXu) fine-tuned PEGASUS on `cnn_dailymail` dataset for news texts and on `gigaword` dataset for short texts.

## Our Contribution

We continue [TheRockXu's](https://github.com/TheRockXu) endeavour to fine-tune PEGASUS and make it work for arbitrary text. 

We are excited to hereby present the PEGASUS model fine-tuned for the abstract summarization of long arbitrary scientific/technical texts. We fine-tuned it in English on datasets `scientific_papers/arxiv`, `scientific_papers/pubmed` and `big_patent/d`.

*NB*: BIG_PATENT dataset is very costly in terms of conversion into training data, we didn't manage to prepare the whole dataset and opted for fine-tuning on its parts. We are currently looking for a compute that would be enough to fine-tune on such big datasets.

## Getting started

Our goal was to make the project as simple as possible. All you need to do are the following 3 steps: 

* run the command: `pip3 install -r requirements.txt`
* download the fine-tuned models for [arxiv](https://drive.google.com/drive/folders/1y_kyLwdSyuDML721ZncdkKcmTbwxtPyb?usp=sharing), [pubmed](https://drive.google.com/drive/folders/14dDE8TVH2StZY70wBIeRDmmbaRCIyZLG?usp=sharing) and/or [big_patent/d](https://drive.google.com/drive/folders/1PvY2uDqiWxCHTJQ5UdOGTgX2symH6LK2?usp=sharing)
* put the files into `model_arxiv`, `model_pubmed` and `model_big_patent_d` respecively.

You are all set, time to choose your text to summarize!

## Using fine-tuned PEGASUS for arbitrary text

Just enter the text you want to summarize into `example_article` and launch the following bash command:

`python3 test_example.py --article /example_article --model_dir /model_arxiv --model_name arxiv` 

`arxiv` can of course be substituted with `pubmed` or `big_patent`. 

The following article was chosen as an example by default: [link](https://www.theguardian.com/news/2020/oct/15/dangerous-rise-of-military-ai-drone-swarm-autonomous-weapons)

Launching `test_example.py` with the parameters indicated above, you should get the following output: `PREDICTION >>`

