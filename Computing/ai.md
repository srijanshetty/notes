# Bag of words
------------------------
Represent any paragraph as a distribution of the words occurring in it.
In this case, we have a predefined list of possible words in our
language.

# Laplace smoothing
------------------------
In case of estimation of the probabilities of words from a corpus, we can
assign a one to every word. This accounts for any word not occurring in the
corpus.

# Naive Bayes
------------------------
You assume conditional independence.
For example: In the spam labelling problem, naive Bayes will allow us to
assume that the probability of a word occurring on a document is
ndependent of any other words.

## References
- [stackoverflow](http://stackoverflow.com/questions/10059594/a-simple-explanation-of-naive-bayes-classification)

# PCA
-----
The idea is given a particular matrix which contains information about a 
process, we want to transform it such that we get only the important 
information.
This problem can be transformed as follows, we have to a transform a matrix
X into a matrix Y (rows of each denote the measurements of a particular kind
like voltage etc; while a column denotes a vector of measurement at a particular
time).
To start out with, we assume that this transformation is linear and is given by
the matrix P.

    PX = Y

So now this is a change of basis problem and rows of P (p_i) are the basis of the
new vector space. (Note: now, a column vector of Y corresponds to the quantity
p_j.x_i, viz., the components of ith vector x along the new basis).

We further assume that we only want to minimize noise (given by the SNR ratio) and
redundancy (given by the covariance matrix). This tacitly assumes that the 
distribution is Gaussian in each measurement, since the only distribution which
is completely described by variance is the Gaussian distribution.

Solving PCA now requires diagonalizing the covariance matrix of Y. This requires
finding the eigenvectors of XX'' and these are the directions of maximum variance.

# Best Fit Line
---------------
The best fit line is the line of maximum variance in the PCA coordinate system,
this is because, the variances are now orthogonal to the best fit line and lead
to the least sum.
In case of normal least square solution, the best fit line is some curve and the
variances are measured relative to this curve along the given coordinate system.
This will not lead to minimum variance since the measurements of variance are not
orthogonal to the curve.

# Topology
----------
Rubber sheet geometry, we dont care about distances, all we care about is the 
connectedness of points. For example: a circle and square have the same topology
because the connectedness is the same.
A topological space consists of a set of points and a set of open sets called 
a topology. The open sets define the topology. Some common topologies are 
torus, sphere, euclidean, circle.
We can consider topology to represent the connectedness of the figure.

# Manifold Learning
-------------------
Every problem in ML deals with closeness in some sense; in clustering we want 'close'
data to be in the same cluster; in dimensionality reduction, we want to preserve the
'closeness' of different vectors; in classification, we want 'close' data to have the
same label.
Manifold learning tasks, compute the k nearest neighbours and then use these neighbours
to form a network. So, locally we are considering a flat, smooth euclidean surface; but
the extrinsic manifold is something completely different. So, manifolds arise naturally.
We assume that the data lies in some low dimensional manifold and then learn the manifold.

It is called manifold learning because we are learning a manifold, which is a subspace with 
local distances being Euclidean and we are not worried about the global picture. 
(Most methods, take 'k' nearest points and the Euclidean distance between them and use some 
kind of nearest neighbours approach.) The idea is given a high dimensional data, we have reason
to believe that there exists a low dimensional manifold where in the data can have a continuous 
representation, i.e, every point in this low dimensional manifold corresponds to a unique point. 
The reasoning is simple, most of the phenomena we see are continuous and so every point must
correspond to some configuration of the object. In the obtained data set, this is not so and 
therefore we try to find a manifold where this assumption is true.

# Linear Model
--------------
A linear model is one in which the dependent variable is linearly dependent on the independent variables, like

    y = mx + c

Here the dependent variable 'y' depends on the independent variable 'x'. This concept then can be extended to 
multivariate linear models.
