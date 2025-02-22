Model Generalizability
======================

* Write blogs / book??

# Chapter Ideas
* What we desire is generalizable models; models that perform well on unseen/inference data. [link](https://people.csail.mit.edu/delimitrou/papers/2024.cal.generalizability.pdf), [link](https://www.rudderstack.com/learn/machine-learning/generalization-in-machine-learning/), [link](https://pmc.ncbi.nlm.nih.gov/articles/PMC9885377/), [link](https://www.cs.toronto.edu/~lczhang/321/notes/notes09.pdf), [link](https://www.computer.org/csdl/journal/ca/2024/01/10488711/1VORtAtSeuA), [link](https://arxiv.org/pdf/2202.01337)
* Most underappreciated concept in Machine Learning
* Write up case-studies of it going well and poorly
* [link](https://pmc.ncbi.nlm.nih.gov/articles/PMC8637230/), [link](https://www.thelancet.com/journals/landig/article/PIIS2589-7500(20)30186-2/fulltext)
* Bias and variance. Under- and over-fitting
* How do we use ttv to debug and improve model performance
* Learning and validation curves
* How do diff model learning algorithms utilize data
* Early stopping based on validation set
* DL epochs and continual learning on previously seen training data
* ITTV
* (I)nference data is critically overlooked in ML education. Every decision you make must be for the sake of desired behavior/performance on inference data. If the cost of having a bad model in production is low and it is easy to get new Test data (or it's easy to run inference) then you could consider production to be your Test data.q
* (T)est data is there *only* to measure the performance of your model on unseen data. This is of value to the customer of your model. Test data must *not* be used to feedback to the model training. If it does, the resulting performance on said data *cannot* be used to quote performance to your customer.

  * When the thought enters your mind that you are ready to run the model on Test data, you should be ready to have go back out into the world and find new Test data if you are unhappy with performance on the original Test data. If you are not willing to do that, then the moment you checked performance on the original Test data *you are done* with model training.
* Test data *only* tells you about the performance of a model after you are *done* training. You could segment the Test data such that you get a distribution of results.
* Cross-Validation
* K-Fold Cross-Validation
* Chronology obeying Cross-Validation
* [Nested Cross-Validation](https://scikit-learn.org/stable/auto_examples/model_selection/plot_nested_cross_validation_iris.html)
