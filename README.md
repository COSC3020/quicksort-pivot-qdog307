# Quicksort Pivots

in the lectures I only briefly mentioned strategies for determining a good pivot
for quicksort. The implementation on the slides simply picks the leftmost
element in the part of the array that we consider as a pivot. I also mentioned a
few other ways of picking a good pivot, e.g. randomly.

Median-of-three is also a good way of picking a pivot -- inspect the first,
middle, and last elements of the part of the array under consideration and
choose the median value. Using the probabilities for picking a pivot in a
particular part of the array (in the same way as we did on slide 34), argue
whether this method is more or less (or equally) likely to pick a good pivot
compared to simply choosing the first element. Assume that all permutations are
equally likely, i.e. the input array is ordered randomly.

Your answer must derive probabilities for choosing a good pivot and
quantitatively reason with them.

The definition of a good pivot is a point in an array where the array is split into two resonably sized parts that are somewhat balanced. The more balanced that they are the more effcient that the algorithm is. When looking at the method of leftmost gives us the probability of %50 it being a good pivot. When determining if its a good pivot the size of the split on both sides needs to be n/4 to 3n/4. With the leftmost we can do ((3n/4)-(n/4))/n, this is where we get the 50%. Then if we look at the medain of three method, the idea is that we have a better chance of picking a good pivot. When it comes to looking at a random array, when choosing three instead of one the probability increases close to 70%. From online readings the probability increases, so I belive that in a random array it is slightly better than just picking the leftmost. 


Add your answer to this markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.

"I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models. All of the work is my own, except where stated otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice."
