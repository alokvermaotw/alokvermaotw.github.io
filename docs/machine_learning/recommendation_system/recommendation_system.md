# Recommendation System
- to make intelligent recommendations without any specific knowledge about the customer is referred to as the _cold-start problem_.
- Techniques
	- [[Popularity Based]]
	- [[content-based recommender systems]]
	- [[clustering-based recommendation systems]]
	- [[Collaborative Filtering]]

# interaction matrix
- represents information about interactions between users and items.

| Item    | user0 | user1 | user2 | user3 | user4 |
| ------- | ----- | ----- | ----- | ----- | ----- |
| item0   | 1     |   1    | 0      |  1     | 1      |
| `item1` | 1     |     0  |   1    |    1   |   0    |
| item2   | 1     |     1  |   0    |    1   |   1    |
| item3   | 1     |      0 |    1   |     0  |    1   |
| item4   | 1      |      1 |    0   |     0  |    1   |



# Cold-Start Problem
- One reasonable thing to do is recommend the most popular item. if something is popular across the people it might appeal to any new customer.

