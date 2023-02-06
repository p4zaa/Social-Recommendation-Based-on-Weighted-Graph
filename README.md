# Social Recommendation Based on Weighted Graph
> December 2020 - May 2022

**Keywords:** `Social Recommendation` `Graph Neural Network` <br/>
**Tools/Frameworks:** `Python` `TensorFlow` `Pandas` <br/>
**Dataset:** [Yelp Open Dataset](https://www.yelp.com/dataset)

## Objective
The project “Social Recommendation Based on Weighted Graph” was conducted with the aim of developing a social recommendation method by using the weighted graph from two data sources: <br/>
  1. **Data source from user influence graph** <br/>
  which contains the relationship between each user by replacing the weight on the user-user relationship with the value that represents the level of influence affecting one user to another which calculated by comparing the user’s weight values between two users. The user’s weight is calculated by comparing the ratio between the total number of connections of the user and the total number of connections of every user’s neighbors.
  2. **Data source from user interest graph** <br/>
  which contains the relationship between user and item by replacing the weight on the user-item relationship with the value that represents the level of interest the item has to the user, which is calculated by comparing the ratios between the rating that user given to particular item and the sum of all ratings that user has given to every interacted item. <br/>
  
## Scope
The scope of the project is to compare the experimental evaluation with the “A Neural Influence and Interest Diffusion Network for Social Recommendation” or [DiffNet++](https://arxiv.org/abs/2002.00844) method on the Yelp dataset only, with a minimum of 5,000 users and a minimum of 40,000 items. The experimental evaluation method was measured using the Hit Ratio and Normalized Discounted Cumulative Gain method. The experimental results on a real-world dataset show that the social recommendation based on weighted graph can improve the effectiveness. <br/>

---

> DiffNet++: A Neural Influence and Interest Diffusion Network for Social Recommendation <br/>
>> Wu, L., Li, J., Sun, P., Hong, R., Ge, Y., & Wang, M. (2020). DiffNet++: A Neural Influence and Interest Diffusion Network for Social Recommendation. ArXiv. https://doi.org/10.48550/arXiv.2002.00844
