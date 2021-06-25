# POS Tagging

Build a multiclass classifier to predict the POS tag of each word. Use a sliding window, i.e. represent each word by the concatenation of the embeddings of 5 words, i.e. the word, two preceding and two following words. Add a special padding word to the embeddings to represent words close to the beginning or end of a sentence.
## Split into train and test
Use all but the last 1000 sentences to train the classifier. (It should be better to choose them randomly).
## Build dictionary of words and tags

Vocabularies of words and tags.
## Data representation

We will use a NN classifier for POS tagging.

In order to provide some context for the classifer, we represent each token as an n-gram of 5 tokens, considering 2 tokens on the left and 2 on the right.
## Build the data set of n-grams
## NN Classifier

The NN classifier will produce a probability distribution for each tag.

The predicted output will be the tag with the highest probability.

The output of the classifier should be a vector of size as the number of possible tags.
We can obtain this using function `to_categorical`, to turn tag indices into a one-hot representation.
  * Build the model
  * Train the model
  * Evaluate the tagger
    `predict_classes` returns the `argmax` of the predicted `softmax` scores.
   
  * Show the confusion matrix
## POS Tagger with Conv1D
Instead of creating the ngrams explicitly, one could use a `Conv1D` layer to group tokens. 

* Build the model

## Classification report
## POS Tagger based on Maximum Entropy Memory Model 
### The feature extractor
The MaxEnt classifiers relies on hand crafted feature representations for the input words.

The features we use:
<ul>
    <li>morphological aspects of English words, e.g. words ending in 'ed', 'ing', or 'ly'</li>
    <li>capitalization, not at the beginning of a sentence</li>
    <li>presence of the word in a list of closed POS categories, e.g. 'CONJ', 'DET', 'PRON', 'PRT</li>
    <li>aspects of the previos word: e.g capitalization, particle</li>
</ul>
You can think of many such features.

Until a few years ago, the SoTA POS taggers were using a rich feature set. See for example:

Giménez, J., and Márquez, L. 2004. [SVMTool: A general POS tagger generator based on Support Vector Machines](https://www.cs.upc.edu/~nlp/SVMTool/lrec2004-gm.pdf]). Proceedings of LREC'04. Lisbon, Portugal.

### MaxEntropy Memory Model Tagger
### Train the Maximum Entropy Memory Model

<b>Warning</b>: training is quite slow.

## Conclusions
