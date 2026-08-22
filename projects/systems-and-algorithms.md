# Systems and Algorithms

Low-level algorithm design, built to adapt and benchmarked honestly.

---

## Pendry Sort

Twelve sorting algorithms developed from one observation about disorder, consolidated into a single paper with standalone implementations and reproducible benchmark suites. The capstone adaptive sort completes a 35-pattern benchmark at 1M elements 4.6x faster than introsort in aggregate. The family includes Sieve Sort, the type-agnostic branch, which pairs a window detector with natural merge sort and handles anything comparable. Every rediscovery along the way is named in the paper, and every benchmark ran against introsort, qsort, radix-256, and heapsort rather than claims alone.

- **Repo:** https://github.com/Spendry/pendry-sort
- **Shows:** algorithm design, benchmarking rigor, and honest accounting.

## Confirmed Position Detection

An O(n) certificate for which elements of an array already sit in their final sorted position, provable without sorting. Two linear passes, a running max and a running min, find the shortest window that still needs work; everything outside it is confirmed correct. The underlying scan is a known technique, disclosed as such; the contribution is reframing it as a certificate and putting it to work as the front end of Sieve Sort, where a nearly sorted input pays almost nothing.

- **Repo:** https://github.com/Spendry/confirmed-position-detection
- **Shows:** reframing a known linear scan as a correctness certificate, clear complexity reasoning, and honest accounting of convergent work.

---
