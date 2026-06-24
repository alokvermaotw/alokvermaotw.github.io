- enables us to make unique, personalized recommendations for each customer and each product.
- There are two types of Collaborative Filtering
	- _Item based_
	- _User based_

# Measure Vector Similarity
- When comparing vectors, we often refer to the cosine similarity of the two vectors (the cosine of the angle between the vectors). Similar vectors will have high cosine similarity, and different vectors will have low cosine similarity. because cos(0) is 1 and cos(90) is 0.
- we calculate cosine similarity of two point vector using $$sim(A,B) = \cos(\theta)=\frac{A.B}{||A||.||B||}$$
- Upper is dot product of the vector and lower is vector norm of the vectors
```python
def dot_product(vector1,vector2):
	thedotproduct=np.sum([vector1[k]*vector2[k] for k in range(0,len(vector1))])
	return(thedotproduct)

def vector_norm(vector):
	thenorm=np.sqrt(dot_product(vector,vector))
	return(thenorm)

def cosine_similarity(vector1,vector2):
	thedotproduct=dot_product(vector1,vector2)
	thecosine=thedotproduct/(vector_norm(vector1)*vector_norm(vector2))
	thecosine=np.round(thecosine,4)
	return(thecosine)

def get_item_recommendations(interaction,itemname):
  otherrows=[rowname for rowname in interaction.index if rowname!=itemname]
  otheritems=interaction.loc[otherrows,:]
  theitem=list(interaction.loc[itemname,:])
  similarities=[]
  for items in otheritems.index:
    similarities.append(cosine_similarity(theitem,list(otheritems.loc[items,:])))
  
  otheritems['similarities']=similarities
  return list(otheritems.sort_values(by='similarities',ascending=False).index)


def get_similar_users(interaction,username):
  othercolumns=[columnname for columnname in interaction.columns if columnname!=username]
  otherusers=interaction[othercolumns]
  theuser=list(interaction[username])
  similarities=[]
  for users in otherusers.columns:
    similarities.append(cosine_similarity(theuser,list(otherusers.loc[:,users])))
  
  otherusers.loc['similarities',:]=similarities
  return list(otherusers.sort_values(by='similarities',axis=1,ascending=False).columns)

  
  

def get_user_recommendations(interaction,username):
  similar_users=get_similar_users(interaction,username)
  purchase_history=interaction[similar_users[0]]
  purchased=list(purchase_history.loc[purchase_history==1].index)
  purchased2=list(interaction.loc[interaction[username]==1,:].index)
  recs=sorted(list(set(purchased) - set(purchased2)))
  return(recs)

get_user_recommendations(interaction,'user2')
```

# Item based collaborative filtering
- Item-based collaborative filtering is relatively simple to implement, and it can be used to make “warm” recommendations even if we know only one fact about a potential customer (a single item that they’re interested in). You can see that it can be implemented with just a few lines of code, and the only input data that’s needed is an interaction matrix.
- It’s filtering because instead of recommending every item to users, we filter and show only the most relevant. 
- It’s collaborative because we’re using information related to all items and all users, so it’s as if the users and items are collaborating to help us determine relevance. 
- It’s item-based because our recommendations are based on the similarity between items’ purchase histories, rather than similarity between users or anything else.

# User-Based Collaborative Filtering
- This approach is based on the idea that people who are similar may be interested in the same items. If we need to make recommendations for a particular customer, we find the customers who are most similar to that customer and recommend items that those similar customers purchased.
- This time, instead of thinking of the rows as vectors related to items, we think of the columns as vectors related to customers.
- 