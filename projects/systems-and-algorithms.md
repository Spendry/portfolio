# Systems and Algorithms

Low-level algorithm design with a focus on correctness, adaptivity, and honest benchmarking.

---

## Pendry Sort

Twelve sorting algorithms developed from one observation about disorder, consolidated into a single paper with standalone implementations and reproducible benchmark suites. The capstone adaptive sort completes a 35-pattern benchmark at 1M elements 4.6x faster than introsort in aggregate, and the paper names every rediscovery along the way.

- **Repo:** https://github.com/Spendry/pendry-sort
- **Shows:** algorithm design, benchmarking rigor, and honest accounting.

## Sieve Sort

An adaptive sorting algorithm in C. A window detector inspects the input and routes it to counting sort or a natural merge sort based on what it finds. Lives in the Pendry Sort repo as the type-agnostic branch of the family.

- **Repo:** https://github.com/Spendry/pendry-sort
- **Shows:** algorithm design that responds to input shape, plus benchmarking against introsort, qsort, radix-256, and heapsort rather than claims alone.

## Confirmed Position Detection

An O(n) global correctness certificate. It uses prefix-max and suffix-min bounds to confirm which elements sit in their final sorted position in a single pass.

- **Repo:** _add link_
- **Shows:** original algorithm work and clear complexity reasoning, refined across several iterations.

---
