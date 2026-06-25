In Jul-2016, a research team lead by Piatra Janowski at Facebook AI Research published their work on FastText.

# Concept
- Extension of [[Word2Vec]]
- Breaks the word into character sets of length n (n-grams):
	- `"amazon" => "a", "am", "ama", "amaz", "amazo", "amazon"`
- Embedding for a word is the aggregate of the embedding of each n-gram within the word
- Solves out of vocabulary issue of [[Word2Vec]]

# Implementation
- CBOW and skip-gram models
- increase the vocabulary size beyond the 3 Million
- Adds text classification