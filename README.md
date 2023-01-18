# Social Recommendation Based on Weighted Graph

## What is social graph
A social graph is a representation of the relationships and connections between individuals in a social network. It is typically visualized as a graph or network, with nodes representing individuals and edges representing the relationships or connections between them. Social graph can be used to represent a variety of different types of connections, such as friendships, familial relationships, professional connections, or shared interests. The infirmation stored in a social graph can be used to power a variety of social networking features, including social recommendations, content filtering, and personalized search results.

<p align='center'>
  <img src='https://github.com/p4zaa/Social-Recommendation-Based-on-Weighted-Graph/blob/7ec26d7607a2ee1321cd054d667d335142b1f1f8/resources/user-user%20matrix-u-u%20facebook.drawio.png' width='70%' />
</p>

> Image of an example of the social network where users are connected with relationships. <br/>
> Icons designed by [Freepik from Flaticon](https://www.flaticon.com/authors/freepik)

## What is social recommendation
Social recommendation refers to a type of recommendation system that utilizes information about the **social connections** and **interactions** of users to generate personalized recommendations. This can include recommendations for products, content, or other items that are **influenced** by the actions and preferences of a user's friends, family, or other connections on a social network. Social recommendation systems can be used in a variety of contexts, such as online shopping, social media, and online communities.

<p align='center'>
  <img src='https://github.com/p4zaa/Social-Recommendation-Based-on-Weighted-Graph/blob/595ac3951879e430bb6dfe496da6fdf49947a44e/resources/user-user%20matrix-U-U%20influenced.drawio.png' width='70%' />
</p>

> Image of an example of how user can be influenced by non-relationship user through user's close friends. <br/>
> Icons designed by variety of creators from [Flaticon](https://www.flaticon.com/)

## Why graph-based instead of matrix-based
Graphs are well suited for modeling relationships between entities, which is key aspect of social networks. They provide a **more flexible and expressive** way to **represent complex relationships** than traditional matrix-based methods. 
<br/>
<br/>
One of the main advantages of using graph is that it can easily handle relationships that are not symetric, such as one-way friendships or directed edges representing 'following' or 'mentioning'. In contrast, matrix-based representations can only handle symetric relationships. 
<br/>
<br/>
Graphs also have the ability to handle sparse data and the ability to scale. Graph algorithms are efficient for traversing large and sparse data sets, making it possible to analyze and make sense of large social networks. 
<br/>
<br/>
Also, graph can easily handle the dynamic nature of social networks where relationships are constantly changing, whereas matrices need to be rebuild every time chages occur. 
<br/>
<br/>
In summary, graph-based representation are well suited for modeling social networks because they provide a flexible and expressive way to present complex relationships and can handle the dynamic nature of social networks, sparse data and scale better than traditional matrix-based methods <br/>

<p align='center'>
  <img src='https://developers.google.com/machine-learning/recommendation/images/Matrixfactor.svg' width='100%' />
</p>

> Image visualization of how matrix factorization work. <br/>
> Image by [Google Developers](https://developers.google.com/machine-learning/recommendation/collaborative/matrix)
