**** CS224D Lecture 3 Notes.

 Working of the word2vec with exaple:


 "Today I am teaching a lecture"  window size is one.

 Center word now: I
 u=left Today, v=right am
 use the formula.


 We mostly define the set of all params in model i terms of a one long vector

 in our case,
 d: dimensional vector
 v: vmany words

 Thetw will a vector with , each word has two probabilities inside and outside


 Gradient decent:


 To minimize out theta, over full batch the entire training data would require us to compute gradients for all windows.


 update would be for each of element from theta

 So for corpus data there will be huge number of tokens hence windows, it will take


 So we use stochastic gradient decent (SGD):


 thetaNew=theta old -Alpha*(Jt(theta))

But update at each window, we have at most 2c-1 words so we end up updating three values, one inside gradient and two outside gradients

So it will be sparse matrix we can do optimization in this process, by just keeping the hash of the word vectors or update only columns of full embedding matrix U and V.


Normalization factor denom is computationally intensive, so we use skip gram have a softmax. So we look for couple of other say ten wordsets and penalzie random them for not having curr words.


Sigmoid function: take any number and map it to one!


we maximize the log probabilities of two words occurring together and penalize the random words not co-occuring.


Continuous Bag of words model:
Here we do the process in reverse way,
so predict center word given surrounding words.
