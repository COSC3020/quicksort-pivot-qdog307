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

A good pivot is one that splits the array into two reasonably balanced partitions, with neither partition being larger than $3n/4$. Balanced partitions lead to better performance in quicksort, while extreme pivots create highly unbalanced partitions, increasing the depth of recursion and degrading efficiency.
When using the leftmost element as the pivot, there is a significant chance of selecting an extreme value, leading to unbalanced partitions. The median-of-three method, on the other hand, reduces the likelihood of selecting extreme values by considering three elements and choosing the middle one. This approach increases the probability of selecting a good pivot.

Probabilities for Choosing a Good Pivot
Leftmost Element
When the leftmost element is used as the pivot, the probability of selecting a good pivot is $\frac{1}{2}$ (50%). This is because there is an equal chance that the pivot falls in either a balanced or unbalanced position (Lecture 01 Sorting - slide 34).
Median-of-Three Method
The median-of-three method evaluates three elements: the first, middle, and last elements of the array. The pivot is chosen as the median of these three values. For this method to select a good pivot, the chosen median must split the array into partitions that satisfy the $3n/4$ condition.
Let:
•	L = an element less than the good pivot,
•	E = the good pivot (median element),
•	H = an element greater than the good pivot.
Possible Configurations
The three elements can form the following configurations:
•	$(LLL), (LLE), (LLH), (LEE), (LEH), (LEL), (LHL), (LHH), (LHE)$
•	$(EEE), (EEL), (EEH), (ELH), (EHL), (ELL), (EHH), (EHE), (ELH)$
•	$(HHH), (HHL), (HHE), (HLL), (HEE), (HEL), (HLE), (HLH), (HHE)$
Each combination has an equal probability, and the median-of-three method calculates the middle value. We compute the probabilities based on these configurations:
1.	All three values are less than, equal to, or greater than the good pivot:
o	Probability: $(1/2)^3 = 1/8$.
2.	Two values are the good pivot, one is extreme:
o	Probability: $(1/2)^2 \cdot (1/4) \cdot 3 = 3/16$.
o	This applies to both "less than" and "greater than" cases, so total probability: $2 \cdot 3/16 = 3/8$.
3.	One good pivot and two extreme values:
o	Probability: $(1/2) \cdot (1/4)^2 \cdot 6 = 3/16$.
Total Probability
Summing these probabilities gives:
P(good pivot)=18+38+316=1116≈68.75%P(\text{good pivot}) = \frac{1}{8} + \frac{3}{8} + \frac{3}{16} = \frac{11}{16} \approx 68.75\%P(good pivot)=81+83+163=1611≈68.75%

Comparison
•	Leftmost Element: $50%$ probability of selecting a good pivot.
•	Median-of-Three Method: $68.75%$ probability of selecting a good pivot.
The median-of-three method significantly increases the likelihood of choosing a good pivot compared to the leftmost element strategy. This improvement reduces the chances of unbalanced partitions, making quicksort more efficient. 

Sources. For this I used word doc to format my READme. I used lecture slides for the left most element. I went to office hours with Proffesor Lars to get a better understanding of a setup up for the proability statement. 

Add your answer to this markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.

"I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models. All of the work is my own, except where stated otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice."
