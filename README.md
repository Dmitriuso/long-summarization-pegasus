# Long Summarization PEGASUS

## Short Introduction

PEGASUS model by Google was open sourced in July 2020: you can find more information about it in [Google AI blog](https://ai.googleblog.com/2020/06/pegasus-state-of-art-model-for.html), in the corresponding [academic article](https://arxiv.org/pdf/1912.08777.pdf) and in [PEGASUS GitHub repository](https://github.com/google-research/pegasus).

## Our Contribution

We are excited to hereby present the PEGASUS model fine-tuned for the abstract summarization of long arbitrary texts. We fine-tuned it in English on datasets `scientific_papers/arxiv`, `scientific_papers/pubmed` and `big_patent/d`.

* Unfortunately, BIG_PATENT dataset is very costly in terms of conversion into training data, we didn't manage to prepare the whole dataset and opted for fine-tuning on its parts.

## Using fine-tuned PEGASUS for arbitrary text

It's quite simple. You just enter the text you want to summarize into `example_article` and launch the following bash command:

`python3 test_example.py --article /example_article --model_dir /model_arxiv --model_name arxiv` 

`arxiv` can of course be substituted with `pubmed` or `big_patent`. 
