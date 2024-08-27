# decision-trees

## Making Predictions
Decison Trees require very little data preparation, they don't require feature scaling or centering at all.

![images/gini.png](images/gini.jpg)

p(i,k) is the ratio of class k instances among the training instances in the ith node.

## The CART Training Algorithm
Scikit-Learn uses the CART(Classification and Regression Tree) algorithm, which produces only binary trees. However, other algorithms, such as ID3, can produce decision trees with nodes that have more than two children.

CART cost function for classification

J(k, t_k) = m_left/m G_left + m_right/m G_right

it searches for the pair (k, t_k), k is the feature and t_k is the threshold (e.g., "petal length <= 2.45 cm").

The tree stops recursing onces it reaches max_depth or cannot find a split that will reduce impurity or other stopping conditions like min_samples_split, min_samples_leaf, min_weight_fraction_leaf, and max_leaf_nodes.

CART is a greedy algorithm. It does not check whether or not the split will lead to the lowest possible impurity several levels down and is not guaranteed to be optimal. finding the optimal tree is known to be an NP-complete problem. It requires O(exp(m)) time.

## Computational Complexity
n: number of features
m: number of samples

Traversing decision tree: O(log(m))
Training decision tree: O(n * m * log(m))
