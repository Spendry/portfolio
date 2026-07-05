# Systems and Algorithms

Low-level algorithm design with a focus on correctness, adaptivity, and honest benchmarking.

---

## Pendry Sort

Twelve sorting algorithms developed from one observation about disorder, consolidated into a single paper with standalone implementations and reproducible benchmark suites. The capstone adaptive sort completes a 35-pattern benchmark at 1M elements 4.6x faster than introsort in aggregate. The family includes Sieve Sort, the type-agnostic branch, which pairs a window detector with natural merge sort and handles anything comparable. Every rediscovery along the way is named in the paper, and every benchmark ran against introsort, qsort, radix-256, and heapsort rather than claims alone.

- **Repo:** https://github.com/Spendry/pendry-sort
- **Shows:** algorithm design, benchmarking rigor, and honest accounting.

## Confirmed Position Detection

An O(n) global correctness certificate. It uses prefix-max and suffix-min bounds to confirm which elements sit in their final sorted position in a single pass.

- **Repo:** _add link_
- **Shows:** original algorithm work and clear complexity reasoning, refined across several iterations.

---
