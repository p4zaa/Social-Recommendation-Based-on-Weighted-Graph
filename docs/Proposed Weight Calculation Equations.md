# Proposed Weights Calculation
## Weight on User Influence Graph
> Weight between user and user connected with relationship edges <br/>

<p align='center'>
  <img src='https://github.com/p4zaa/Social-Recommendation-Based-on-Weighted-Graph/blob/3979835c288b1e8df945d9ae7a8234bacf8c73a5/resources/senior%20project%20for%20portfolio-influence%20graph.png' width='30%' />
</p>

The weighted user-user graph can interpreted edge weight as the 'power of influenced' to eachother. The weight can be calculation by using many information from the graph such as node degree, mutual information or [recommendation power](https://ieeexplore.ieee.org/document/4770004).
<br/>
<br/>
In this example I will using only node degree to compute the edge weight in every connection edges by computing individual weight for each user nodes with the following equation:

`Every nodes must be having in-degree and out-degree atleast 1`

$$w_a = \frac{E_a}{\sum_{b\in a's neighbors} E_b}$$

Where:
|Symbols|Description|
|-------|-----------|
|$w_a$|User $a$'s weight|
|$E_a$|Number of user $a$'s edges (in degree)|
|$E_b$|Number of user $a$'s neighbor edges (in+out degree)|
|$b$|Every user $a$'s friends(neighbors)|

---

And the weight between each edges relationship with the following equation:

$$w_{ab} = \frac{\frac{E_a}{\sum_{b\in a's neighbors}E_b}}{\frac{E_b}{\sum_{c\in b's neighbors}E_c}} = \frac{w_a}{w_b}$$

Where:
|Symbols|Description|
|-------|-----------|
|$w_{ab}$|Influence weight from user $a$ to user $b$ ( $a$ --> $b$ )|
|$w_a$|User $a$'s weight|
|$w_b$|User $b$'s weight|

## Weight on User Interest Graph
> Weight between user and item connected with relationship edges <br/>

<p align='center'>
  <img src='https://github.com/p4zaa/Social-Recommendation-Based-on-Weighted-Graph/blob/3979835c288b1e8df945d9ae7a8234bacf8c73a5/resources/senior%20project%20for%20portfolio-interest%20graph.png' width='30%' />
</p>

`Every nodes must be having in-degree and out-degree atleast 1`

$$w_{ai} = \frac{r_{ai}}{\sum_{k\in R_a} r_{ak}}$$

Where:
|Symbols|Description|
|-------|-----------|
|$w_{ai}$|Relation weight between user $a$ and item $i$|
|$r_{ai}$|User $a$'s rating given to item $i$|
|$k\in R_a$|Items $k$ where $k$ are the items given rating by user $a$|
