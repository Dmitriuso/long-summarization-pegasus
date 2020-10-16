# Long Summarization PEGASUS

I'm excited to hereby present the PEGASUS model fine-tuned for the abstract summarization of arbitrary long texts. We fine-tuned it in English on datasets `scientific_papers/arxiv`, `scientific_papers/pubmed` and `big_patent/d`.

* Unfortunately, BIG_PATENT dataset is very costly in terms of conversion into training data, we didn't manage to prepare the whole dataset and opted for fine-tuning on its parts.

## Using fine-tuned PEGASUS for arbitrary text

It's quite simple. You just enter the text you want to summarize into `example_article` and launch the following bash command:

`python3 test_example.py --article /example_article --model_dir /model_arxiv --model_name arxiv` 

`arxiv` can of course be substituted with `pubmed` or `big_patent`. 
