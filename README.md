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

The dataset is used to train, evaluate and test a BERT-based model for Natural Language Inference. Dataset is valanced alonged all the classes.
Dataset Format is:
```bash
\dataset
  \train.tsv
  \dev.tsv
  \test.tsv
```
You can file the dataset in this [link](https://drive.google.com/file/d/14kplogWzU2JsIB04ENeLtgtYTt0kYyxU/view)


## Model Evaluation Metrics
After training the model, we evaluate it on the test set. Here are the results from the evaluation:

Accuracy: The accuracy of the model on the test dataset.
F1 Score (Macro): The F1 score calculated by taking the average of F1 scores for each class, treating each class equally.
F1 Score (Micro): The F1 score calculated by counting the total number of true positives, false positives, and false negatives across all classes.

Example:

```bash
Accuracy: 90.20%
F1 Score (Macro): 0.8909
F1 Score (Micro): 0.9020
```
These scores indicate the performance of the BERT model on the NLI task.

## Predictions

Below are some examples of predictions made by the trained model. The model takes a pair of sentences and outputs one of the following labels: entailment, contradiction, or neutral.

```bash

premise is: A woman within an orchestra is playing a violin .
hypothesis is: A woman is playing the violin .
Prediction Label is:      entailment       and True Label is:      entailment
-----------------------------------------------------------------
-----------------------------------------------------------------
premise is: Two men climbing on a wooden scaffold .
hypothesis is: Two sad men climbing on a wooden scaffold .
Prediction Label is:      neutral       and True Label is:      neutral
-----------------------------------------------------------------
-----------------------------------------------------------------
premise is: A man in a black shirt , in a commercial kitchen , holding up meat he took out of a bag .
hypothesis is: A man in a black shirt , in a commercial kitchen , holding up the old meat he took out of a bag .
Prediction Label is:      neutral       and True Label is:      neutral
-----------------------------------------------------------------
-----------------------------------------------------------------
premise is: a woman in a black shirt looking at a bicycle .
hypothesis is: A woman dressed in black shops for a bicycle .
Prediction Label is:      neutral       and True Label is:      neutral
-----------------------------------------------------------------
-----------------------------------------------------------------
premise is: many children play in the water .
hypothesis is: The children are playing mini golf .
Prediction Label is:      contradiction       and True Label is:      contradiction
-----------------------------------------------------------------
-----------------------------------------------------------------

```


