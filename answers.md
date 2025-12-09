# CMPS 6610 Extra Credit Answers
  
In this extra credit assignment, we will test and review concepts you
   have learned since the midterm exam. Please add your written answers
   to `answers.md` which you can convert to a PDF using
   `convert.sh`. Alternatively, you may scan and upload written
   answers to a file named `answers.pdf`.



1. **Algorithmic Paradigms**
What is your favorite algorithmic paradigm, and why?

   - I personally like graph-based algorithms the most. Many real-world geometric and visual problems—such as navigation, clustering, image segmentation, and network optimization—can be naturally expressed as graph structures, making these algorithms both intuitive and widely applicable. I also enjoy that graph problems span a wide range of difficulty, including many NP-hard challenges, which makes the field intellectually rich and full of interesting open questions.


2. **Divide and Conquer**
Do problems that can be solved by a divide and conquer approach
necessarily satisfy the optimal substructure property? If so, provide
a proof. If not, provide a counterexample.

   - No, divide and conquer does NOT necessarily require optimal substructure. but if the problem had optimal substructure it could be solve with divide and conquer method.

For a counterexample, Given an array, find the element that occurs more than ⌊n/2⌋ times. in this case the global majority may not be the majority in either half and devide and conquer won't be applicable. Then the subproblems' optimal solutions do not determine the optimal global solution. Divide-and-conquer still works, but optimal substructure doesn’t hold.

3. **Randomization**
We learned in lecture that Quicksort takes $O(n \log n)$ expected
work. For a random
variable $X$, Markov's inequality states that:

$$\mathbf{P}[X \geq \alpha] \leq \frac{\mathbf{E}[X]}{\alpha}$$

- 3a. What is the probability that Quicksort does $\Omega({n^2})$
  comparisons?

    - Lets take $\alpha = c * n^2$ then
     $$\mathbf{P}[X \geq c * n^2] \leq \frac{O(n \log n)}{c * n^2}$$ $\to O(\frac{\log n}{n})$

      which shows that Quicksort is concentrated tightly around its expected O($n \log n$) work.
The probability of doing much more than the expected amount decays quickly.

- 3b. What is the probability that Quicksort does $10^c n \ln n$
comparisons, for a given $c>0$? What does this say about the
"concentration" of the expected work for Quicksort?

    - Just like the previous part lets take $\alpha = 10^c n \ln n$
      then
      $$\mathbf{P}[X \geq 10^c n \ln n] \leq \frac{O(n \log n)}{10^c n \ln n}$$ $\to O(\frac{1}{10^c})$

      which shows that Quicksort is concentrated tightly around its expected O($n \log n$) work. the probability of doing much more than the expected amount decays quickly.

4. **Greedy Algorithms**

5. **Dynamic Programming**

6. **Graphs**
