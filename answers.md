# CMPS 6610 Extra Credit Answers
  
In this extra credit assignment, we will test and review concepts you
   have learned since the midterm exam. Please add your written answers
   to `answers.md` which you can convert to a PDF using
   `convert.sh`. Alternatively, you may scan and upload written
   answers to a file named `answers.pdf`.

---

1. **Algorithmic Paradigms**
What is your favorite algorithmic paradigm, and why?

   - I personally like graph-based algorithms the most. Many real-world geometric and visual problems—such as navigation, clustering, image segmentation, and network optimization—can be naturally expressed as graph structures, making these algorithms both intuitive and widely applicable. I also enjoy that graph problems span a wide range of difficulty, including many NP-hard challenges, which makes the field intellectually rich and full of interesting open questions.

---

2. **Divide and Conquer**
Do problems that can be solved by a divide and conquer approach
necessarily satisfy the optimal substructure property? If so, provide
a proof. If not, provide a counterexample.

   - No, divide and conquer does NOT necessarily require optimal substructure. but if the problem had optimal substructure it could be solve with divide and conquer method.

For a counterexample, Given an array, find the element that occurs more than ⌊n/2⌋ times. in this case the global majority may not be the majority in either half and devide and conquer won't be applicable. Then the subproblems' optimal solutions do not determine the optimal global solution. Divide-and-conquer still works, but optimal substructure doesn’t hold.

---
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

---
4. **Greedy Algorithms**
Consider a scheduling problem where we are given $n$ jobs $j_1, j_2,
\ldots, j_n$,  each of which has a processing time $p_i$. A schedule $S$
is simply an ordering of jobs; each job will have a \textit{waiting
time} given by the sum of all processing times of jobs prior to
it. Let us define the  cost $C(S)$ of a schedule $S$ to be the average waiting
time over all jobs. Prove that scheduling jobs in order
of their processing times (i.e., shortest-job-first) results in an
optimal schedule.

    - Claim:
      Scheduling jobs in non-decreasing order of processing times minimizes the average waiting time.

      consider jobs with processing times $p_1, p_2, \cdots, p_n$. then for each task i the sum of $p_1, \cdots, p_i$ is the waiting time and the sumation of these wating time if C.
      
      For a job $j_i$ which is scheduled in schedule $S$, we can say that $W_i$ is the sum of all the processing times of the jobs before position k. now if we consider two adjacent jobs are out of order, by changing their order we can reduce total waiting time.
      $time difference = (p_j) - (p_i - p_j) = 2p_j - p_i < 0$
      Since $p_i > p_j$, we have $time difference < 0$.


---

5. **Dynamic Programming**
Problems that can be solved by dynamic programming require the optimal
substructure property. We showed that the optimal substructure
property induces a directed acyclic graph that can be used to derive
 the span of a dynamic programming algorithm. Give one example of an optimal
 substructure recurrence that has maximum span (i.e., no parallelism
 is possible) and one example that has polylogarithmic (i.e., ideal)
 span.

   - Problems with recurrent structure have chain of dependencies which cause maximum span. example could be Fibonacci (Naive DP Order) which ends up with span $\in O(n)$
   - With the balanced recurrence tree we can end up with polylogarithmic span like Parallel Prefix Sum (Scan) that has span $\in O(\log n)$


---

6. **Graphs**
You learned the cut property for minimum spanning trees. There
is another useful fact called the \textit{cycle property} for minimum
spanning trees which states the following:
Given a graph G that contains a cycle, then the largest weight cycle in that graph
cannot be contained in any minimum spanning tree.Prove the cycle property.

   - well the easist way to show that is methods like kruskal find the MST with greedy selection of minumum edges and avoiding to create any cycle which shows cycles can not be in ant MST. even if we consider these cycle in the MST since there is connected path     between all the nodes then we are able to remove the heaviest edge and still have a MST with a smaller cost which proves the cycle property.
