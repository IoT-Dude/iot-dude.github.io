# JAAP (Jung Archetypes Analytical Project Text-Mining-III-III) 


Jung Archetypes Analytical Project Text Mining III-III, a continuation of a ML project, building context…


### Text Classification with Python and Scikit-Learn

In the progress to build a text classification tool (filter) for my Jung Archetypes Analytical Projet I need to build context for my own understanding as well as for others understanding of how it works.

Text classification is one of the most commonly used NLP tasks. This is an example of sentimental analysis of movie reviews, a common text classification task being performed using Python, Sklearn, Numpy, Pandas etc.

### Machine Learning

Scikit-learn, (also known as sklearn), is a free software machine learning library for the Python programming language. It features various classification, regression and clustering algorithms including support-vector machines, random forests, gradient boosting, k-means and DBSCAN, and is designed to interoperate with the Python numerical and scientific libraries NumPy and SciPy.


## Random Forest algorithm (Demo III-III)

Another demo of how the basics of text analysis works by using ipynb, Python and Scikit-Learn

----


### Introduction

The Random Forest algorithm is one of the most flexible, powerful and widely-used algorithms for classification and regression, built as an ensemble of Decision Trees.

If you aren not familiar with these - no worries, we will cover all of the concepts.

In this in-depth hands-on guide, we will build an intuition on how decision trees work, how ensembling boosts individual classifiers and regressors, what random forests are and build a random forest classifier and regressor using Python and Scikit-Learn, through an end-to-end mini-project, and answer a research question.

Consider that you are are currently part of a research group that is analysing data about women. The group has collected 100 data records and wants to be able to organize those initial records by dividing the women into categories: being or not pregnant, and living in rural or urban areas. The researchers want to understand how many women would be in each category.

There is a computational structure that does exactly that, it is the tree structure. By using a tree structure, you will be able to represent the different divisions for each category.
Decision Trees


### How do you populate the nodes of a tree? (This is where decision trees come into focus)

First, we can divide the records by pregnancy, after that, we can divide them by living in urban or rural areas. Notice, that we could do this in a different order, dividing initially by what area the women live and after by their pregnancy status. From this, we can see that the tree has an inherent hierarchy. Besides organizing information, a tree organizes information in a hierarchical manner - the order that the information appears matters and leads to different trees as a result.

Below, is an example of the tree that has been described:

In the tree image, there are 7 squares, the one on top that accounts for the total of 100 womem, this top square is connected with two squares below, that divide the women based on their number of 78 not pregnant and 22 pregnant, and from both previous squares there are four squares; two connected to each square above that divide the women based on their area, for the not pregnant, 45 live in an urban area, 33 in a rural area and for the pregnant, 14 live in a rural area and 8 in an urban area. Just by looking a the tree, it is easy to understand those divisions and see how each "layer" is derived from previous ones, those layers are the tree levels, the levels describe the depth of the tree:

Observe in the image above that the first tree level is level 0 where there is only one square, followed by level 1 where there are two squares, and level 2 where there are four squares. This is a depth 2 tree.

In level 0 is the square that originates the tree, the first one, called root node, this root has two child nodes in level 1, that are parent nodes to the four nodes in level 2. See that the "squares" we have been mentioning so far, are actually called nodes; and that each previous node is a parent to the following nodes, that are its children. The child nodes of each level that have the same parent are called siblings, as can be seen in the next image:

In the previous image, we also display the level 1 as being the interior nodes, once they are between the root and the last nodes, which are the leaf nodes. The leaf nodes are the last part of a tree, if we were to say from the 100 initial women, how many are pregnant and living in rural areas, we could do this by looking at the leaves. So the number at the leaves would answer the first research question.

If there were new records of women, and the tree that was previously used to categorize them, was now used to decide if a woman could or couldn't be part of the research, would it still function? The tree would use the same criteria, and a woman would be ellegible to participate if pregnant and living in a rural area.

By looking at the image above, we can see that the answers to the questions of each tree node - "is she a participant?", "is she pregnant?", "does she live in a rural area?"- are yes, yes, and yes, so it seems that the tree can ideed lead to a decision, in this case, that the woman could take part in the research.

This is the essense of decision trees in, done in a manual manner. Using Machine Learning, we can construct a model that constructs this tree automatically for us, in such a way to maximize the accuracy of the final decisions.

Note: there are several types of trees in Computer Science, such as binary trees, general trees, AVL trees, splay trees, red black trees, b-trees, etc. Here, we are focusing on giving a general idea of what is a decision tree. If it depends on the answer of a yes or no question for each node and thus each node has at most two children, when sorted so that the "smaller" nodes are on the left, this classifies decision trees as binary trees.

In the previous examples, observe how the tree could either classify new data as participant or non participant, or the questions could also be changed to - "how many are participants?", "how many are pregnant?", "how many live in a rural area?"- leading us to find the quantity of pregnant participants that live in a rural area.

When the data is classified, this means the tree is performing a classification task, and when the quantity of data is found, the tree is performing a regression task. This means that the decision tree can be used for both tasks - classification and regression.

Now that we understand what a decision tree is, how can it be used, and what nomenclature is used to describe it, we can wonder about its limitations.


### Understanding Random Forests

What happens to the decision if some participant lives on the division between urban and rural areas? Would the tree add this record to rural or urban? It seems hard to fit this data into the structure we currently have, since it's fairly clear cut.

Also, what if a woman that lives on a boat participates in the research, would it be considered rural or urban? In the same way as the previous case, it is a challeging data point to classify considering the available options in the tree.

By thinking a bit more about the decision tree example, we are able to see it can correctly classify new data considering it already follows a pattern the tree already has - but when there are records that differ from the initial data that defined the tree, the tree structure is too rigid, making the records not classifiable.

This means that the decision tree can be strict and limited in its possibilities. An ideal decision tree would be more flexible and able to accomodate more nuanced unseen data.

Solution: Just as "two pairs of eyes see better than one", two models typically come up with a more accurate answer than one. Accounting for the diversity in knowledge representations (encoded in the tree structure), the rigidity of the sligtly different structures between multiple similar trees aren't as limiting anymore, since the shortcomings of one tree can be "made up for" by another. By combining many trees together, we get a forest.

Regarding the answer to the initial question, we already know that it will be encoded in the tree leaves - but what changes when we have many trees instead of one?

If the trees are combined for a classification, the result will be defined by the majority of answers, this is called majority voting; and in the case of a regression, the number given by each tree in the forest will be averaged.
Ensemble Learning and Model Ensembles

This method is known as ensemble learning. When empliying ensemble learning, you can mix any algorithms together, as long as you can ensure that the output can be parsed and combined with other outputs (either manually, or using existing libraries). Typically, you ensemble multiple models of the same type together, such as multiple decision trees, but you're not limited to just join same-model type ensembles.

Ensembling is a practically guaranteed way to generalize better to a problem, and to squeeze out a slight performance boost. In some cases, ensembling models yields a significant increase in predictive power, and sometimes, just slight. This depends on the dataset you're training and evaluating on, as well as the models themselves.

Joining decision trees together yields significant performance boosts compred to individual trees. This approach was popularized in the research and applied machine learning communities, and was so common that the ensemble of decision trees was colloquially named a forest, and the common type of forest that was being created (a forest of decision trees on a random subset of features) popularized the name random forests.

Given wide-scale usage, libraries like Scikit-Learn have implemented wrappers for RandomForestRegressors and RandomForestClassifiers, built on top of their own decision tree implementations, to allow researchers to avoid building their own ensembles.


### How the Random Forest Algorithm Works

The following are the basic steps involved when executing the random forest algorithm:

Pick a number of random records, it can be any number, such as 4, 20, 76, 150, or even 2.000 from the dataset (called N records). The number will depend on the width of the dataset, the wider, the larger N can be. This is where the random part in the algorithm's name comes from!
Build a decision tree based on those N random records;
According to the number of trees defined for the algorithm, or the number of trees in the forest, repeat steps 1 and 2. This generates more trees from sets of random data records;
After step 3, comes the final step, which is predicting the results:
In case of classification: each tree in the forest will predict the category to which the new record belongs. After that, the new record is assigned to the category that wins the majority vote.
In case of regression: each tree in the forest predicts a value for the new record, and the final prediction value will be calculated by taking an average of all the values predicted by all the trees in the forest.

Each tree fit on a random subset of features will necessarily have no knowledge of some other features, which is rectified by ensembling, while keeping the computational cost lower.

Advice: Since Random Forest use Decision Trees as a base, it is very helpful to understand how Decision Trees work and have some practice with them individually to build an intuition on their structure. When composing random forests, you'll be setting values such as the maximum depth of a tree, the minimum number of sampels required to be at a leaf node, the criteria to bet determine internal splits, etc. to help the ensemble better fit a dataset, and generalize to new points. In practice, you'll typically be using Random Forests, Gradient Boosting or Extreme Gradient Boosting or other tree-based methodologies, so having a good grasp on the hyperparameters of a single decision tree will help with building a strong intuition for tuning ensembles.

With an intuition on how trees work, and an understanding of Random Forests - the only thing left is to practice building, training and tuning them on data!



fkfkfkfkfkfkfkf


v1.2
