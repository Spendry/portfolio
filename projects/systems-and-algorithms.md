# Systems and Algorithms

Low-level algorithm design with a focus on correctness, adaptivity, and honest benchmarking.

---

## Sieve Sort

An adaptive sorting algorithm in C. A window detector inspects the input and routes it to counting sort or a natural merge sort based on what it finds.

- **Repo:** _add link_
- **Shows:** algorithm design that responds to input shape, plus benchmarking against pdqsort and qsort rather than claims alone.

## Confirmed Position Detection

An O(n) global correctness certificate. It uses prefix-max and suffix-min bounds to confirm which elements sit in their final sorted position in a single pass.

- **Repo:** _add link_
- **Shows:** original algorithm work and clear complexity reasoning, refined across several iterations.

---

_Both entries reward a reader who runs the benchmarks. Include a one-command build and a results table in each repo README so they do not have to take the numbers on faith._
