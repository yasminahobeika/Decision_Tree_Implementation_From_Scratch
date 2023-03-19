# Decision Tree from scratch

## Decision Tree Classifier

The DecisionTreeClassifier is a class that builds a decision tree model for classification problems. It is implemented in Python and uses NumPy library for computations.

### Node_cls class
This class defines a Node constructor for classification problems. It stores and initializes:

* Feature index used for best split: feature = None
* Left child node: left_spl = None
* Right child node: right_spl = None
* Node splitting threshold value: spl_val = None
* Information Value gain: info_gain = None
* Output value of the node: out_val = None
The is_leaf_node() function checks whether a node is a leaf node or not.

### DecisionTreeClassifier class
This class initializes a DecisionTree constructor for classification problems. It stores and initializes:

*Maximum tree depth: max_depth = 100
*Minimum samples required for splitting nodes: min_samples_split = 2
*Number of features to be used for the tree: n_features = None
*Cost function/Loss criterion for splitting nodes: criterion = 'entropy'
*root: stores the root node of the decision tree
*tree: stores the tree structure to generate a tree graph visualization
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


