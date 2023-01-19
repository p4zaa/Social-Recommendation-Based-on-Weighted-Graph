# Social Recommendation Based on Weighted Graph
## Weight between users and users connected with relationship edges
The weighted user-user graph can interpreted edge weight as the 'power of influenced' to eachother. The weight can be calculation by using many information from the graph such as node degree, mutual information or [recommendation power](https://ieeexplore.ieee.org/document/4770004).
<br/>
<br/>
In this example I will using only node degree to compute the edge weight in every connection edges by computing individual weight for each user nodes with the following equation:

## $$w_a = \frac{E_a}{\sum_{b\in a's neighbors} E_b}$$

Where:
|Symbols|Description|
|-------|-----------|
|$w_a$|User a's weight|
|$E_a$|Number of user a's edges (in degree)|
|$E_b$|Number of user a's neighbor edges (in+out degree)|
|$b$|Every user a's friends(neighbors)|

---

And the weight between each edges relationship with the following equation:

## $$w_{ab} = \frac{\frac{E_a}{\sum_{b\in a's neighbors}E_b}}{\frac{E_b}{\sum_{c\in b's neighbors}E_c}} = \frac{w_a}{w_b}$$

Where:
|Symbols|Description|
|-------|-----------|
|$w_{ab}$|Influence weight from user a to user b (a-->b)|
|$w_a$|User a's weight|
|$w_b$|User b's weight|

## Weight between users and items connected with relationship edges
