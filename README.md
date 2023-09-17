# Decision Tree from scratch

### Node_cls class
This class defines a Node constructor for DT classification and regression problems. It stores and initializes:

* Feature index used for best split: feature = None
* Left child node: left_spl = None
* Right child node: right_spl = None
* Node splitting threshold value: spl_val = None
* Information Value gain: info_gain = None
* Output value of the node: out_val = None
The is_leaf_node() function checks whether a node is a leaf node or not.

## Decision Tree Classifier

The DecisionTreeClassifier is a class that builds a decision tree model for classification problems. It is implemented in Python and uses NumPy library for computations.



### DecisionTreeClassifier class
This class initializes a DecisionTree constructor for classification problems. It stores and initializes:

* Maximum tree depth: max_depth = 100
* Minimum samples required for splitting nodes: min_samples_split = 2
* Number of features to be used for the tree: n_features = None
* Cost function/Loss criterion for splitting nodes: criterion = 'entropy'
* root: stores the root node of the decision tree
* tree: stores the tree structure to generate a tree graph visualization
The train() method of the DecisionTreeClassifier class takes two inputs:

1. X, a matrix of input features.
2. y, a vector of output labels.
It uses the _build_tree function to proceed with growing the decision tree structure.

The _dominant_class function defines the most common class/label, which takes input y, a vector of output labels and returns the class with the highest frequency.

The _split function defines the node splitting function, which takes as input:

* data: the subset input data based on a feature index.
* split_thresh: specified split threshold to split the tree into left and right child nodes.
The function returns the indices of the left and right child nodes.

The information_gain function takes as input:

y_parent: Parent node data for labels.
The DecisionTreeClassifier class builds a decision tree model for classification problems. It uses the _build_tree function to recursively grow the decision tree by finding the best split at each node based on a specified loss criterion. It then generates the tree structure and returns the root node of the decision tree.

## Decision Tree Regressor
This code implements a Decision Tree Regressor algorithm for regression problems. The algorithm is implemented in Python and uses NumPy library.

### DecisionTreeRegressor class
The DecisionTreeRegressor class is used to initialize the Decision Tree constructor for regression problems, which stores and initializes the following:


* max_depth: Maximum tree depth. Default value is set to 100.
* min_samples_split: Minimum samples required for splitting nodes. Default value is set to 2.
* n_features: Number of features to be used for tree. Default is set to None.
* criterion: Cost function or Loss criterion for splitting nodes. Default is set to 'mse'.
The train() method of the DecisionTreeRegressor class is used to build the decision tree structure. It takes two inputs:

1. X: a matrix of input features
2. y: a vector of output labels


The Node_reg class constructor initializes the tree nodes for the regression problem, which stores and initializes the following:

* feature: Feature index used for best split.
* left_spl: Left child node.
* right_spl: Right child node.
* spl_val: Node splitting threshold value.
* var_redn: Variance loss value.
* out_val: Output value of the node.
The is_leaf_node() method of the Node_reg class is used to check whether a node is a leaf node or not.

The _build_tree() method is a recursive function that builds the decision tree structure. It takes two inputs:

1. X: a matrix of input features
2. y: a vector of output labels

The function returns tree nodes after each iteration.

The _calculate_node_mean() method computes the leaf node value which is the mean of the output labels.

The _split() method is used to split the data into left and right child nodes.

The DecisionTreeClassifier & DecisionTreeRegressor classes also have a tree attribute that stores the tree structure to generate **tree graph visualization**.

## Performance and comparison with SKlearn DT:

| Dataset                        	| Our DT (time)    	| Our DT (accuracy or r2) 	| SKlearn DT (time) 	| SKlearn DT (accuracy or r2) 	|
|--------------------------------	|------------------	|-------------------------	|-------------------	|-----------------------------	|
| Breast Cancer (Classification) 	| 0.6694 seconds   	| 0.937                   	| 0.6808 seconds    	| 0.958                       	|
| Iris (Classification)          	| 0.0662 seconds   	| 0.973                   	| 0.0682 seconds    	| 1                           	|
| Diabetes (Regression)          	| 0.0547 seconds   	| 0.485                   	| 0.0596 seconds    	| -0.22                       	|
| Airbnb (Regression)            	| 168.0722 seconds 	| 0.567                   	| 168.9311 seconds  	| 0.274                       	|

As seen from these 4 experiments, the execution time of our DT is very close to the execution time of the SKlearn DT. Our DT has almost the same performace (measured by **accuracy**) in classification experiments, while our DT overperforms the SKlearn DT in regression (as measured by **r2 loss**).

## Next Steps

* Impelement pruning to prevent overfitting.
* Optimise for parallel processing so that this DT can be used for bagging and random forest implementations efficiently.
