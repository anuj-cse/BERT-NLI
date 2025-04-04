# BERT-NLI
Natural Language Inference using BERT model

## Clone the Repository
To get started with the project, you first need to clone the repository using the following command:

```bash
git clone https://github.com/anuj-cse/BERT-NLI.git
cd BERT-NLI
```

## Set Up the Conda Environment
To ensure that all dependencies are installed, create a new virtual environment using conda. This can be done by running the following command:

```bash
conda env create -f environment.yml
conda activate NLI
```

## Dataset
This project uses the Natural Language Inference (NLI) dataset, which contains pairs of sentences labeled as either "entailment," "contradiction," or "neutral." The model aims to predict whether the second sentence logically follows from the first. Sentences are stored in PCFG parsed tree format. First we have extracted raw sentences from this format.

Example:

```bash
PCFG parsed sentence:(ROOT (S (NP (CD Two) (NNS women)) (VP (VBP are) (VP (VBG embracing) (SBAR (IN while) (S (NP (VBG holding)) (VP (TO to) (VP (VB go) (NP (NNS packages)))))))) (. .)))
Extracted raw sentence: two women are embracing while holding to go packages .
```
    

Entailment: The second sentence follows logically from the first.
Contradiction: The second sentence contradicts the first.
Neutral: The second sentence neither entails nor contradicts the first.

The dataset is used to train, evaluate and test a BERT-based model for Natural Language Inference.
Dataset Format is:
```bash
\dataset
  \train.tsv
  \dev.tsv
  \test.tsv
```
You can file the dataset in this [link](https://drive.google.com/file/d/14kplogWzU2JsIB04ENeLtgtYTt0kYyxU/view)


