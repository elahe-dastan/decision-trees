1. What is the approximate depth of a decision tree trained (without restrictions) on a training set with one million instances?
   
   log(1000000)
3. Is a node's Gini impurity generally lower or higher than its parents? Is it **generally** lower/higher, or **always** lower/higher?

   A node's Gini impurity is generally lower than its parent's. It's due to the CART training algorithm cost function, which splits each node in a way that minimizes the weighted sum of its children's Gini impurities. However it's possible for a node to have a higher Gini impurity than its parent, as long as this increase is more than compensated for by a decrease in the other child's impurity. For example:
   ![images/gini-impurity.png](../images/gini-impurity.jpg)
