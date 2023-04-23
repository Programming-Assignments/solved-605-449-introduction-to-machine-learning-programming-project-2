Download Link: https://assignmentchef.com/product/solved-605-449-introduction-to-machine-learning-programming-project-2
<br>
The purpose of this assignment is to give you an introduction to unsupervised learning by implementing feature selection with a clustering algorithm. Specifically, you will implement StepwiseForwardSelection, or SFS (introduced in Module 03). For extra credit, you may also implement GeneticAlgorithmSelection, or GAS (also introduced in Module 03). Since these are wrapper methods, you will need to test these algorithms using another algorithm as well. Normally, these two feature selection methods are used with a classifier; however, in this assignment, we will use the results of clustering to evaluate the features. You will choose to implement one of the following two clustering algorithms — <em>k</em>-Means and HAC — both of which were introduced in Module 04. For extra credit, you may implement both. To evaluate HAC, grow the tree until you get <em>k </em>clusters. You should evaluate these algorithms for <em>k </em>= the number of classes in the data set. Specifically, the Silhouette Coefficient should be used for your evaluation. The silhouette coefficient is calculated for each point in the data set as follows.

<ol>

 <li>For data point <strong>x</strong><em><sub>i </sub></em>in cluster <strong>c</strong><em><sub>j</sub></em>, calculate the average distance to all other objects in <strong>c</strong><em><sub>j</sub></em>.</li>

</ol>

<h1>1       X</h1>

<em>a<sub>i </sub></em>=    <em>            δ</em>(<strong>x</strong><em><sub>i</sub>,</em><strong>x</strong><em><sub>k</sub></em>)<em>.</em>

<em>m</em><em>i </em><strong>x</strong><em>k</em>∈<strong>c</strong><em>j</em>

<ol start="2">

 <li>For data point <strong>x</strong><em><sub>i </sub></em>and any cluster <strong>c</strong><em><sub>j </sub></em>that does not contain <strong>x</strong><em><sub>i</sub></em>, find the average distance to all of the points in that other cluster. Then return the minimum such value over all of the clusters. For this, denote the cluster containing <strong>x</strong><em><sub>i </sub></em>as <strong>c</strong>(<strong>x</strong><em><sub>i</sub></em>).</li>

</ol>

<em> .</em>

<ol start="3">

 <li>For data point <strong>x</strong><em><sub>i </sub></em>calculate the silhouette coefficient.</li>

</ol>

<em>.</em>

<ol start="4">

 <li>To evaluate the overall clustering of the data, find the average silhouette for the data set.</li>

</ol>

<em>.</em>

This provides a measure between −1 and +1 where a negative value indicates the average distance to points within the cluster is greater than the minimum average distance to point in other clusters. This indicates the clusters are not well separated. Ideally, we would like all silhouette coefficients to be positive (<em>a<sub>i </sub>&lt; b<sub>i</sub></em>), and we would like <em>a<sub>i </sub></em>to be as close to zero as possible. When this occurs, the coefficient approaches 1.0.

For this assignment, you will use three datasets that you will download from the UCI Machine Learning Repository, namely:

<ol>

 <li>Glass — https://archive.ics.uci.edu/ml/datasets/Glass+Identification</li>

</ol>

The study of classification of types of glass was motivated by criminological investigation.

<ol start="2">

 <li>Iris — https://archive.ics.uci.edu/ml/datasets/Iris</li>

</ol>

The data set contains 3 classes of 50 instances each, where each class refers to a type of iris plant.

<ol start="3">

 <li>Spambase — https://archive.ics.uci.edu/ml/datasets/Spambase</li>

</ol>

This collection of spam e-mails came from a postmaster and individuals who had filed spam. This is a two-class problem with a large number of attributes and a large number of instances.

1

As with the prior assignment, some of the data sets have missing attribute values. When this occurs in low numbers, you may simply edit the corresponding values out of the data sets. For more occurrences, you should do some kind of “data imputation” where, basically, you generate a value of some kind. This can be purely random, or it can be sampled according to the conditional probability of the values occurring, given the underlying class for that example. The choice is yours, but be sure to document your choice.

Our ability to handle large data sets is becoming more and more important, and one of the data sets has been selected to get you thinking about how to handle such data. Specifically, for the Spambase data set, some attention should be given to optimizing the feature selection process. One approach is to apply the feature selection on a subset of the data, rather than the full data set. While there is some risk associated with missing cluster boundaries this way, it can greatly speed up the feature selection process. Note that you still need to apply the final set of features for clustering the entire data set. For this project, the following steps are required:

<ul>

 <li>Download the three (3) data sets from the UCI Machine Learning repository. You can find this repository at http://archive.ics.uci.edu/ml/. All of the specific URLs are also provided above.</li>

 <li>Pre-process each data set as necessary to handle missing data.</li>

 <li>Implement either <em>k</em>-means or HAC so you can use them for the wrapper feature selection methods.</li>

 <li>Implement SFS with the loss function defined above.</li>

 <li>Extra Credit:

  <ul>

   <li>For up to 15 additional points, implement both <em>k</em>-means and HAC.</li>

   <li>For up to 15 additional points, implement GAS for feature selection, in addition to SFS.</li>

   <li>Run experiments on all relevant combinations of algorithms.</li>

  </ul></li>

 <li>Run your algorithms on each of the data sets. These runs should output the feature sets and best clusters in a way that can be interpreted by a human. There is no need to separate the data into training and test sets. Be sure to test your algorithms with the Silhouette Coefficient given above, <em>not </em>classification accuracy!</li>

 <li>Write a very brief paper that incorporates the following elements, summarizing the results of your experiments. You should also output the summary statistics on clustering performance.

  <ol>

   <li>Title and author name</li>

   <li>A brief, one paragraph abstract summarizing the results of the experiments</li>

   <li>Problem statement, including hypothesis, projecting how you expect each algorithm to perform</li>

   <li>Brief description of algorithms implemented</li>

   <li>Brief description of your experimental approach</li>

   <li>Presentation of the results of your experiments</li>

   <li>A discussion of the behavior of your algorithms, combined with any conclusions you can draw</li>

   <li>Summary</li>

   <li>References (you should have at least one reference related to each of the algorithms implemented,a reference to the data sources, and any other references you consider to be relevant)</li>

  </ol></li>

</ul>


