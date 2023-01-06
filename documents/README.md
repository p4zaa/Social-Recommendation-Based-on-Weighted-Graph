# Project Documents
## Graph Convolutional Networks 

From ['Semi-supervised Classification with Graph Convolutional Networks'](https://arxiv.org/abs/1609.02907) paper
> Kipf, T. N., & Welling, M. (2017). Semi-supervised classification with graph convolutional networks. In International Conference on Learning Representations (ICLR).

### **$H^{l+1} = \sigma (\hat{D}^{-\frac{1}{2}}\hat{A}\hat{D}^{-\frac{1}{2}}H^{l}W^{l})$**
or
### **$H^{l+1} = \sigma (A^{*}W^{l}H^{l})$**
**Where** <br/>
|`Symbol`|`Description`|
|---|---|
|$H^{l+1}$|Feature representation at layer ${l+1}$|
|$\sigma$|Activation function|
|$\hat{D}^{-\frac{1}{2}}$|Inverse square root of the diagonal degree matrix|
|$\hat{A}$|Adjacency matrix with self-loops *where* $\hat{A} = A + I$|
|$H^{(l)}$|Feature representation at layer $l$|
|$W^{(l)}$|Weight matrix at layer $l$|

|`Term`|`Description`|
|---|---|
|$A^{*}=\hat{D}^{-\frac{1}{2}}\hat{A}\hat{D}^{-\frac{1}{2}}$|Normalizing term|

**Ref:**
> Mayachita, I. (n.d.). Understanding Graph Convolutional Networks for Node Classification. Towards Data Science. Retrieved January 7, 2023, from https://towardsdatascience.com/understanding-graph-convolutional-networks-for-node-classification-a2bfdb7aba7b

---
### Node Degree
The degree of a node in a graph is the number of edges that are incident to the node. It is a measure of the local connectivity of the node and reflects how many other nodes it is directly connected to.

The node degree is an important concept in graph theory and has a number of applications. For example, in a social network, the node degree can be used to measure the popularity or influence of a user. In a recommendation system, the node degree can be used to measure the importance or centrality of an item.

In addition, the node degree can be used to define the graph Laplacian matrix, which is a matrix that encodes the structure of a graph. The graph Laplacian has elements $L_{ij}$ that are equal to the degree of node $i$ if $i = j$, and -1 if there is an edge between nodes $i$ and $j$, and 0 otherwise. The graph Laplacian encodes the local connectivity of the graph, and it has a number of properties that make it useful for various graph analysis tasks, such as graph partitioning and community detection.

The node degree can also be used to define graph convolutions, which are a way of learning node representations in a graph that take into account the relationships between the nodes. Graph convolutions using the graph Laplacian can be used to learn features that are invariant to the node ordering and that respect the graph structure.

---
### Laplacian matrix
The graph Laplacian matrix is a matrix that encodes the structure of a graph. It is defined as the difference between the degree matrix (a diagonal matrix with the degree of each node on the diagonal) and the adjacency matrix. The graph Laplacian has elements $L_{ij}$ that are equal to the degree of node $i$ if $i = j$, and -1 if there is an edge between nodes $i$ and $j$, and 0 otherwise.

The graph Laplacian matrix can be constructed from the adjacency matrix of a graph as follows:

1. Compute the degree of each node in the graph. The degree of a node is the number of edges it is connected to.
2. Construct the degree matrix $D$, which is a diagonal matrix with the degree of each node on the diagonal.
3. Construct the graph Laplacian matrix $L$ as the difference between the degree matrix and the adjacency matrix:

$L = D - A$

Here is an example of how to construct the graph Laplacian matrix for the graph in the previous example:

```python
Graph:
   1
   |
2--3--4
   |
   5
```
```python
Adjacency matrix:
  0  0  1  0  0
  0  0  1  0  0
  1  1  0  1  1
  0  0  1  0  0
  0  0  1  0  0

Degree of each node:
  1
  1
  4
  1
  1

Degree matrix:
  1  0  0  0  0
  0  1  0  0  0
  0  0  4  0  0
  0  0  0  1  0
  0  0  0  0  1

Graph Laplacian matrix:
  1  0 -1  0  0
  0  1 -1  0  0
 -1 -1  4 -1 -1
  0  0 -1  1  0
  0  0 -1  0  1

```
---
### Inverse Square Root Diagonal Degree Matrix
$\hat{D}^{-\frac{1}{2}}$ is the inverse square root of the degree matrix of a graph. The degree matrix of a graph is a diagonal matrix with the degree of each node on the diagonal. The inverse square root of a matrix is defined as the matrix that satisfies the equation:

$$A^{-\frac{1}{2}} \cdot A^{-\frac{1}{2}} = A^{-1}$$

For example, if the degree matrix of a graph is:

$$D = \begin{bmatrix} 2 & 0 & 0 \\\ 0 & 3 & 0 \\\ 0 & 0 & 4 \end{bmatrix}$$

then the inverse square root of the degree matrix is:

$$\hat{D}^{-\frac{1}{2}} = \begin{bmatrix} \frac{1}{\sqrt{2}} & 0 & 0 \\\ 0 & \frac{1}{\sqrt{3}} & 0 \\\ 0 & 0 & \frac{1}{\sqrt{4}} \end{bmatrix}$$

Note that the inverse square root of a matrix is not necessarily unique, and there may be multiple valid solutions.

---
### $\hat{D}^{-\frac{1}{2}}\hat{A}\hat{D}^{-\frac{1}{2}}$ Term
The term $\hat{D}^{-\frac{1}{2}}\hat{A}\hat{D}^{-\frac{1}{2}}$ is a way of normalizing the adjacency matrix of a graph. It is often used in graph convolutional networks to improve the performance and stability of the model.

Here, $\hat{A}$ is the adjacency matrix of the graph, and $\hat{D}^{-\frac{1}{2}}$ is the inverse square root of the degree matrix of the graph. The degree matrix of a graph is a diagonal matrix with the degree of each node on the diagonal.

The term $\hat{D}^{-\frac{1}{2}}\hat{A}\hat{D}^{-\frac{1}{2}}$ can be interpreted as a "normalized" version of the adjacency matrix, where the connections between the nodes are weighted by the degree of the nodes. This normalization helps to balance the influence of the nodes in the graph and can improve the performance and stability of the model.

For example, consider a graph with two nodes, A and B, connected by an edge with weight $w$. If the degree of node A is $d_A$ and the degree of node B is $d_B$, then the term $\hat{D}^{-\frac{1}{2}}\hat{A}\hat{D}^{-\frac{1}{2}}$ would weight the connection between A and B by: $$\frac{w}{\sqrt{d_Ad_B}}$$ This normalization helps to balance the influence of the nodes and can improve the performance and stability of the model.
