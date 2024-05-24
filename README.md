# LLM Experiments with Relation Extraction - SemEval 2010 Task 8


This project aims to use prompt engineering and vector search to improve the performance of LLMs on relation extraction.

SemEval 2010 Task 8 has 19 classes for classifying relations (9 two-way, 1 null class). If collapsing the two-way relations, there are 10.

The entire dataset has 8000 training examples and 2717 test examples.

I test several conditions:

* Zero-shot

    * Simply call the LLM with a description of the relation extraction task, and a query

* K-shot with random chain-of-though (COT) examples:

    * Ask the LLM to generate COT examples from the entire train dataset and save

    * Fetch k random examples from dataset

    * Call the LLM with task description, k-shot examples, and query

* K-shot with retrieved COT examples:

    * Same as above, but use vector search to fetch k most relevant examples from dataset (using FAISS)