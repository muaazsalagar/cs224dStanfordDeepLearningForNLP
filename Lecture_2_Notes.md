WordNet:
Similar to image net, maintains the word DAG as relationships

****But problem with discrete representation.

1) as words are added, language evolvs
2) words have meaning subjective
3) requires human labor to create and adapt
4) Hard to capture word similarity

Second Solution : One Hot presentation:

Problem with this is text corpus gets larger, presentaion gets larger and it is inefficient in making relationships


Distributional similarity based representation:
words and their neighbors

One of most successful ideas of modern NLP techniques

Co-occurence Matrix:

2 options:  
  1) Word-Doc co-occurence Matrix
  2) Word windows length 1 (more common 5-10  ot the left or right)
    Symmetric irrelevant whether left or right context


Problme with Co-occurence vectors:

As size of vocab increases we need to add a column each time and upadte the whoel doc based on that

High dimensional: More storage

Models are less robust



Solutions:

Use low dim vectors:

Idea: Store most imp info data , small num a dense vect we get

use SVD: Single value decomposition for the co-variance Matrix


Problesm with SVD:
Computational cost for Matrix increases O(mn2) flops when n<m
it ll be very huge computation for just million words
SVD optimization is also different problem set  



Paper1:PaperL NLP almost from scratch- 2008
Paper2: word2vec

Discussion on word2vec:

instead of capturing co-occurence matrix .
predict  surrounding words in a window of length  m of every word.


and we can derive the equation with derivatives.

and ultimately we get the prob model which is computationally very expensive. SO we focus on improving two probabilities only.



Observations from paper2:

analogies derived by substractions are:
apple-apples, car-cars and family and families etc. are almost same.



**** Count Based vs Direct prediction

  In count based we use methods like PCA, COALS, LSA , HAL, SVD methods etc.

  it is fast, efficient usage of stat,

  but disproportionate to Primarily large imp to large counts.
  but can be fixed by caping the max count to some of the value.


  Now, with new methods,
  it sclaes with corpus data size.
  i efficient usage of stats: we hope that after enough training exaples we will get some patterns

But it does capture complex patters beyond word similarity.



The best of two methods is GloVE

in this method. we run the method on the co-occurence matrix instead of word windows.
So it has fast training and scalable for huge corpus data sizeand also with good performanc ewith small corpus and small vectors.
