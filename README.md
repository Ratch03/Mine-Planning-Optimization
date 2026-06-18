# Mine Planning Optimization — MiniZinc

## Problem

Plan the most profitable underground mine tunnel path across a 2D grid of cells.
Each cell has a mining cost and an associated ore value. The tunnel must stay within
a given budget and length limit while avoiding unstable (negative-cost) cells.

## Objective

Maximise profit = total ore mined (tunnel cells + orthogonally adjacent cells) minus
total mining cost (tunnelling cost + reinforcement cost for any unstable adjacent cells).

## Constraints

- The tunnel must start from one of the given start positions
- Each tunnel cell must be orthogonally adjacent (above, below, left, right) to the
  previous cell — no branching
- The tunnel cannot pass through cells with negative cost (unstable ground)
- Unstable cells adjacent to the tunnel require reinforcement, adding to total cost
- Total cost (tunnelling + reinforcement) must stay within the given budget

## Two Variants

- **Part A — Fixed length tunnel**: the tunnel must be exactly the given length.
  Some problem instances have no feasible solution under this constraint.
- **Part B — Bounded length tunnel**: the tunnel can be up to the given length, with
  unused tunnel positions set to coordinate `(0,0)` and placed at the end of the
  position lists. This variant guarantees a solution exists wherever Part A does,
  and often finds a higher-profit result by not forcing unnecessary tunnel length.

## Tools

- Language: MiniZinc
- Solver: HiGHS

## How to Run

1. Install MiniZinc IDE from <https://www.minizinc.org/>
2. Open `mineplan.mzn`
3. Select a `.dzn` data file
4. Click Run

## Author

**Ratchana Pourouchottaman**
Master of AI — Monash University
[LinkedIn](https://linkedin.com/in/ratchana) · [GitHub](https://github.com/Ratch03) · [Portfolio](https://portfolio-beige-mu-mc6c9uw8zf.vercel.app)
