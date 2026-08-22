# Hardware and Architecture

Processor design from first principles, with the evidence standard stated before the results.

---

## The Temporal Generator Machine

A processor that computes its control, arithmetic, and addressing from time rather than
fetching instructions from memory. Every lane runs one operation forever,
`STATE <- (A*STATE + B*C + D) >> E`, with no opcode, no decoder, and no program counter.
The bet is that on a modern process the arithmetic is nearly free and the instruction
supply is the bill, so a machine that generates its schedule instead of storing it stops
paying that bill in the steady state. At equal transistor budget the design reaches
roughly 46x the multiply-accumulate throughput of an AVX-512 core; per core, the same
comparison goes the other way, and the paper gives both directions and says which one to
quote.

The work ships as a self-contained paper, a build guide across three tracks, an energy
measurement method, and the unedited worklog for all 23 versions. It is verified by five
reproducible test suites — 17/17 on the build target, 16/16 on TGM-0r and TGM-5, plus
recovered mechanisms, the explanatory model, and a historical regression across earlier
simulators — with the lane and the twelve-lane interconnect written in synthesizable
Verilog. The baseline machine it argues against is specified in the repo too, an 8-bit
von Neumann CPU written to understand the thing before redesigning it.

What makes it worth reading is Part 6 and Part 7. Part 6 separates measured from
asserted and states plainly that every performance ratio divides a simulator number by a
number the author chose. Part 7 lists every material error made during development,
including a lane transistor count that omitted the multiplier for six versions and was
wrong by a factor of 15. Several of the twenty-three findings in Part 3 were discovered
by writing bugs rather than by reasoning, and they are marked as such.

- **Repo:** https://github.com/Spendry/temporal-generator-machine
- **Shows:** processor architecture design, synthesizable RTL and simulation-based verification, and honest accounting of asserted versus measured numbers.

---
