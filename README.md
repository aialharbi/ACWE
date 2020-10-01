# Motivation
Word representation models have been successfully applied in many natural language processing tasks, including sentiment analysis. However, these models do not always work effectively in some social media contexts. When considering the use of Arabic in microblogs like Twitter, it is important to note that a variety of different linguistic domains are involved. This is mainly because social media users employ various dialects in their communications. While training word-level models with such informal text can lead to words being captured that have the same meanings, these models cannot capture all words that can be encountered in the real world due to out-of-vocabulary (OOV) words. The inability to identify words is one of the main limitations of this word-level model. In contrast, character-level embeddings can work effectively with this problem through their ability to learn the vectors of character n-grams or parts of words.
**In our work,** we take advantage of both **character-level (CE)** and **word-level (WE)** models to discover more effective means of representing Arabic affect in tweets, which we call **Affect Character and Word Embeddings (ACWE)**.

# Data Collection
One of the main factors in improving the quality of word embeddings is associated with the training dataset size and its richness. We collected a large number of tweets (10M) containing various affect-associated words of different Arabic dialects.

# Word-level Embeddings (WE)
To learn individual words with their embeddings from our collected data, we used the Word2Vec algorithm  to generate affect word embeddings by training the models on a massive number of tweets that we retrieved. We used the Gensim Library to implement the Word2Vec models. We assumed that each tweet is a sentence, so the input of the word-level model was a list of pre-processed tweets that were tokenised into words on whitespace.

# Character-level Embeddings (CE)
To learn morphological features found in each word, we used a character n-grams model (FastText). FastText differs from Word2Vec in its ability to learn the vectors of character n-grams or parts of words. This feature enables the model to capture words that have similar meanings but different morphological word formations. We assumed that each tweet was a sentence, so the input of the character-level model was a list of characters for each tweet.

# Download Models
  - Word Model: [Click here](https://dl.orangedox.com/XXCr6SYm9eGeqtFHb3) Size: 2GB
  - Char Model: [Click here](https://dl.orangedox.com/AcFYHa27ijympcpJ0E) Size: 822MB
  
  
# How to use downloaded Models by Python:
Firstly, unzip the models and locate them in your envioment work.
Then..
For the Word Model:

```sh
from gensim.models import KeyedVectors
word_model = KeyedVectors.load_word2vec_format('.../WordModel.txt')
```

For the Char Model
```sh
from gensim.models import FastText
char_model = FastText.load('.../CharModel')
```

We will (soon) give a complete example for text classification using these models.

# Citation
For more details, please review our paper. If you use our models, please cite [our paper](https://link.springer.com/chapter/10.1007/978-3-030-51310-8_20):

@inproceedings{alharbi2020combining,
  title={Combining Character and Word Embeddings for Affect in Arabic Informal Social Media Microblogs},
  author={Alharbi, Abdullah I and Lee, Mark},
  booktitle={International Conference on Applications of Natural Language to Information Systems},
  pages={213--224},
  year={2020},
  organization={Springer}
  }

