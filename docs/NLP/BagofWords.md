- How any time a given word present in the sentence.

# Steps:
- collect data
- design vocabulary
- Create document vectors
- managing vocabulary
- Scoring words


# Limitations of BOW
- **Vocabulary**: The vocabulary requires careful design, most specifically in order to manage the size, which impacts the sparsity of the document representations.
- **Sparsity**: Sparse representations are harder to model both for computational reasons (space and time complexity) and also for information reasons, where the challenge is for the models to harness so little information in such a large representational space.
- **Meaning**: Discarding word order ignores the context, and in turn meaning of words in the document (semantics). Context and meaning can offer a lot to the model, that if modeled could tell the difference between the same words differently arranged (“this is interesting” vs “is this interesting”), synonyms (“old bike” vs “used bike”), and much more.

```python
import nltk
import re
import numpy as np
# execute the text here as :`
# text = """ # place text here  """`
dataset = nltk.sent_tokenize(text)
for i in range ( len (dataset)):
    dataset[i] = dataset[i].lower()
    dataset[i] = re.sub(r'\W',' ', dataset[i])
    dataset[i] = re.sub(r'\s'+','+dataset[i])=
```