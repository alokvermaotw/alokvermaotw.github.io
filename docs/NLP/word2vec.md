# Concept
- Convert text into vectors called "embeddings"
- 300-dimensional vector space
- perform machine learning on that vectors
# Model architecture to create the embeddings
- Continuous Bag of Words (CBOW)
	- predicts the current word for the window of surrounding word
- Continuous skip-gram
	- uses the current words to predict the surrounding window of context words.
- Architecture is based upon shallow 2 layers neural network 

# Challenge with Word2Vec
- tends to run into output of vocabulary issues because its vocabulary only contain 3 Million words.