# Principle Component Analysis

Principle Component Analysis is a statistical procedure that uses an *orthogonal transformation* to of possibly correlated variables into a set of linearly uncorrelated variables called principle components (PC). The first PC would respresent the variable that shows as much variability in the data as possible, and each i-th principle component would represent the variable with the i-th largest variability.

In order to understand Principle Component analysis, let's first investigate *why it even exists*. What's the goal of Principle Component Analysis, and why even invent it in the first place?

## Why is Principle Component Analysis used?
Imagine you have a dataset that has many independent variables. For example, let's say you wanted to calculate the GDP of a nation. When investigating this topic, you have to consider many different variables. GDP is dependent on the unemployment rates, the employment numbers in every industry, inflation rate, and so on. This becomes very tedious to deal with, and hence Principle Component Analysis.

There are typically a couple ways of going about simplifying a large dataset that has many independent variables. 

### Feature Elimination

As the name suggests, Feature Elimination is when you simply eliminate the features you believe are not conducive to the topic you're trying to investigate. For example, if you're trying to calculate the GDP of a nation, you probably could probably eliminate many variables that may not contribute to the nation GDP very much. The problem with this is that you've basically _entirely_ removed any benefits that these variables will bring.

### Feature Extraction

Feature Extraction does not face the same problem that Feature Elimination does. 

Suppose we have ten independent variables for a dataset. In feature extraction, we create ten _new_ indpendent variables, where each new variable is a combination of the ten old variables. These new independent variables are what we can call Principle Components, and can be ordered on the range of variability they have.

The act of doing this is called dimensionality reduction. We're reducing the feature space in which the dataset relies on.

But why are they ordered in terms of variability? Well, the highly variable ones are the ones that would affect our results the most. The more variable, the better they predict our dependent variable. Each of Principle Components are independent of each other.

This goes back to the idea that Principle Components are basically linearly uncorrelated. You can't really interpret them.

## Terminology

When you initially have data, you generally have a matrix containing rows and columns. The rows, in this case, are the subjects, and the columns are the samples. When graphing this initially, the subjects are on the axes. If you have 4 subjects, then you'll have a 4D graph.

To get the PCA, you typically draw a line of best fit through all the data points. The first line of best fit would be Principle Component 1 (which represents the data best). PC2 will be perpendicular to it, PC3 will be perpendicular to 1 and 2, and so on. The eigenvector is the unit vector for the line of best fit.

Loading scores mean the proportions of each subject in regards to the variance they have. The line of best fit is done using projection, which is the sum of the squares of all the distances from the line of best fit to the data points. The eigenvalue is the square of the sum of squares. Rotation is another word for loading scores.