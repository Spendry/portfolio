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

The work ships as a paper, a method for measuring the energy claim, and the unedited worklog for all 23 versions. It is verified by five reproducible test suites: 17/17 on the build target, 16/16 on TGM-0r and TGM-5, plus recovered mechanisms, the explanatory model and a historical regression across earlier simulators. The lane and the twelve-lane interconnect are written in synthesizable Verilog. The baseline machine it argues against is specified in the repo too, an 8-bit
von Neumann CPU written to understand the thing before redesigning it.

What makes it worth reading is Part 6 and Part 7. Part 6 separates measured from
asserted and states plainly that every performance ratio divides a simulator number by a
number the author chose. Part 7 lists every material error made during development,
including a lane transistor count that omitted the multiplier for six versions and was
wrong by a factor of 15. Several of the twenty-three findings in Part 3 were discovered
by writing bugs rather than by reasoning, and they are marked as such.

- **Repo:** https://github.com/Spendry/temporal-generator-machine
- **Shows:** processor architecture design, synthesizable RTL and simulation-based verification, and honest accounting of asserted versus measured numbers.

## Janus

An architecture built on one move, repeated at every radius: observe the stream while
serving it, commit to a law when the stream holds still, and demote when the law misses.
The repo holds two frozen artifacts from the same line, a day apart. Janus 1.0 is ten
mechanisms composed into one complete lane, 7,471 cells, 22/22 on the bench, and DRC,
LVS and antenna clean on sky130. Janus-I then takes that lane apart and asks what each
piece was doing, arriving at three verbs and a minimal lane of 3,154 cells at 111 MHz:
45% smaller and 11% faster for the same job.

The reason both are in one repo is that the second result has no meaning without the
first sitting beside it. Unlike most of this section, the numbers here are not
estimates. Yosys 0.52 and OpenLane 2 produced them on the sky130 open PDK, and the
OpenLane configurations that reproduce each figure are in the repo.

The work stopped on a framing error it found in itself. Section 7 of the Janus-I paper
records that the machine was tested on programs compiled for a different machine, and
that the separator built to cope with that is a compatibility mechanism rather than an
architectural one. Every timing figure is typical corner, the slow corner was never run
as the place-and-route target, and both papers say so rather than leaving it to be
discovered.

- **Repo:** https://github.com/Spendry/janus
- **Shows:** RTL design in Verilog, physical design through OpenLane on the sky130 open PDK with DRC/LVS-clean signoff, and an architecture derived by removing mechanisms and measuring what each removal cost.

---
