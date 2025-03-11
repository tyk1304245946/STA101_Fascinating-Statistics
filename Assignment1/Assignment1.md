# Assignment 1

## Problem 1

**Solution:**

Given:
- Probability of motherboard (MB) problems, $ P(MB) = 0.4 $
- Probability of hard drive (HD) problems, $ P(HD) = 0.3 $
- Probability of both MB and HD problems, $ P(MB \cap HD) = 0.15 $

To find the probability that a computer has **no MB or HD problems**, we first calculate the probability of having **at least one problem** using the principle of inclusion-exclusion:
$$
P(MB \cup HD) = P(MB) + P(HD) - P(MB \cap HD)
$$
$$
P(MB \cup HD) = 0.4 + 0.3 - 0.15 = 0.55
$$

The probability of **no problems** is the complement of the union:
$$
P(\text{No MB/HD problems}) = 1 - P(MB \cup HD)
$$
$$
P(\text{No MB/HD problems}) = 1 - 0.55 = 0.45
$$

**Answer:**
The probability of a fully functioning MB and HD is $\boxed{0.45}$.

## Problem 2

**Solution:**

Given:
- Probability a programmer knows Java, $ P(J) = 0.7 $
- Probability a programmer knows Python, $ P(P) = 0.6 $
- Probability a programmer knows both, $ P(J \cap P) = 0.5 $

---

**1. Probability of not knowing Python and not knowing Java:**

First, calculate the probability of knowing *at least one language* using inclusion-exclusion:
$$
P(J \cup P) = P(J) + P(P) - P(J \cap P)
$$
$$
P(J \cup P) = 0.7 + 0.6 - 0.5 = 0.8
$$

The probability of knowing **neither** language is the complement:
$$
P(\text{Neither}) = 1 - P(J \cup P) = 1 - 0.8 = 0.2
$$

**Answer:**
$\boxed{0.20}$

---

**2. Probability of knowing Java but not Python:**

This is the probability of knowing Java *minus* the overlap with Python:
$$
P(J \setminus P) = P(J) - P(J \cap P)
$$
$$
P(J \setminus P) = 0.7 - 0.5 = 0.2
$$

**Answer:**
$\boxed{0.20}$

---

**3. Probability of knowing Java given they know Python:**

Use the definition of conditional probability:
$$
P(J \mid P) = \frac{P(J \cap P)}{P(P)}
$$
$$
P(J \mid P) = \frac{0.5}{0.6} \approx 0.8333
$$

**Answer:**
$\boxed{\frac{5}{6}} \quad (\text{or approximately } 0.8333)$

## Problem 3

**Solution:**

When selecting $ k $ elements from $ n $ distinct elements **with replacement**, the number of permutations and combinations are derived as follows:

---

**1. Permutations (Order Matters):**

Each selection is ordered, and elements can be repeated. For each of the $ k $ positions, there are $ n $ choices. Thus:
$$
\text{Number of permutations} = n \times n \times \cdots \times n = n^k
$$

**Example:**
For $ n = 3 $, $ k = 2 $:
Permutations = $ 3^2 = 9 $ (e.g., AA, AB, AC, BA, BB, BC, CA, CB, CC).

---

**2. Combinations (Order Does Not Matter):**

Elements can repeat, but order is irrelevant. This is equivalent to distributing $ k $ identical items into $ n $ distinct bins (stars and bars method). The formula is:
$$
\text{Number of combinations} = \binom{n + k - 1}{k} = \frac{(n + k - 1)!}{k! \ (n - 1)!}
$$

**Example:**
For $ n = 3 $, $ k = 2 $:
Combinations = $ \binom{3 + 2 - 1}{2} = \binom{4}{2} = 6 $ (e.g., {AA, AB, AC, BB, BC, CC}).

---

**Final Answer:**
- Permutations with replacement: $\boxed{n^k}$
- Combinations with replacement: $\boxed{\binom{n + k - 1}{k}}$

## Problem 4

**Solution:**

We need to compute the probability that **at least one couple** is paired together when 4 male-female couples are randomly paired for a dance.

---

**Total Pairings:**
There are $ 4! = 24 $ ways to pair 4 males with 4 females.

---

**Using the Principle of Inclusion-Exclusion:**

Let $ A_i $ be the event that the $ i $-th couple is paired together. The probability of at least one $ A_i $ is:
$$
P\left(\bigcup_{i=1}^4 A_i\right) = \sum P(A_i) - \sum P(A_i \cap A_j) + \sum P(A_i \cap A_j \cap A_k) - P(A_1 \cap A_2 \cap A_3 \cap A_4)
$$

1. **Single Couple Pairing:**
   - $ \binom{4}{1} $ ways to choose 1 couple.
   - Probability: $ \frac{3!}{4!} = \frac{1}{4} $.
   - Total: $ 4 \cdot \frac{1}{4} = 1 $.

2. **Two Couples Paired:**
   - $ \binom{4}{2} = 6 $ ways to choose 2 couples.
   - Probability: $ \frac{2!}{4!} = \frac{1}{12} $.
   - Total: $ 6 \cdot \frac{1}{12} = 0.5 $.

3. **Three Couples Paired:**
   - $ \binom{4}{3} = 4 $ ways to choose 3 couples.
   - Probability: $ \frac{1!}{4!} = \frac{1}{24} $.
   - Total: $ 4 \cdot \frac{1}{24} = \frac{1}{6} $.

4. **All Four Couples Paired:**
   - Probability: $ \frac{1}{4!} = \frac{1}{24} $.

Combining these:
$$
P(\text{At least one couple}) = 1 - 0.5 + \frac{1}{6} - \frac{1}{24} = \frac{15}{24} = \frac{5}{8}.
$$

---

**Alternative Derangement Approach:**
The number of derangements (no couple paired) for $ n = 4 $ is $ !4 = 9 $. Thus:
$$
P(\text{No couples}) = \frac{9}{24} = \frac{3}{8} \implies P(\text{At least one couple}) = 1 - \frac{3}{8} = \frac{5}{8}.
$$

---

**Final Answer:**
$\boxed{\dfrac{5}{8}}$

## Problem 5

**Solution:**

We need to find the probability that the sum of two randomly chosen numbers $ X $ and $ Y $ from the interval $[0, 1]$ is less than $\frac{7}{5} = 1.4$.

---

**Geometric Interpretation:**
The problem is equivalent to finding the area of the region $ X + Y < \frac{7}{5} $ within the unit square $[0,1] \times [0,1]$.

1. **Breakdown of the Region:**
   - For $ 0 \leq X \leq 0.4 $, $ Y $ can range from $ 0 $ to $ 1 $ (since $ \frac{7}{5} - X \geq 1 $).
   - For $ 0.4 < X \leq 1 $, $ Y $ can range from $ 0 $ to $ \frac{7}{5} - X $.

2. **Area Calculation:**
   - **First Region (Rectangle):**

     $$
     \text{Area}_1 = 0.4 \times 1 = 0.4
     $$

   - **Second Region (Integral):**
     $$
     \text{Area}_2 = \int_{0.4}^1 \left(\frac{7}{5} - X\right) dX
     $$

     $$
     = \left[\frac{7}{5}X - \frac{1}{2}X^2\right]_{0.4}^1
     $$

     $$
     = \left(\frac{7}{5}(1) - \frac{1}{2}(1)^2\right) - \left(\frac{7}{5}(0.4) - \frac{1}{2}(0.4)^2\right)
     $$

     $$
     = \left(1.4 - 0.5\right) - \left(0.56 - 0.08\right) = 0.9 - 0.48 = 0.42
     $$

3. **Total Area:**
   $$
   \text{Total Area} = 0.4 + 0.42 = 0.82
   $$

---

**Probability:**
The probability is the total area divided by the unit square area ($1$):
$$
P\left(X + Y < \frac{7}{5}\right) = \frac{41}{50} = 0.82
$$

**Final Answer:**
$\boxed{\dfrac{41}{50}}$

## Problem 6

See screenshot after the `Problem 7` solution.

## Problem 7

1. Satisfy the requirements of the `Introductory Course`

2. Review the theroy of `Probability` and `Combinatorics`

3. Our teacher is beautiful and kind !!!
