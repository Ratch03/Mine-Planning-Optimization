# Mine Planning Optimization — MiniZinc

## Problem
Plan the most profitable underground mine tunnel path across a 2D grid of cells.
Each cell has a mining cost and an ore value. The tunnel must stay within a given
budget and length limit, while avoiding unstable cells.

## Objective
Maximise profit = total ore mined (tunnel + adjacent cells) minus total mining cost
(tunneling + reinforcement of unstable adjacent cells).

## Constraints
- Tunnel must start from a given start position
- Each cell must be orthogonally adjacent to the previous one (no branches)
- Cannot tunnel through cells with negative cost
- Unstable cells adjacent to the tunnel require reinforcement (additional cost)
- Total cost must stay within budget

## Two Variants
- **Part A** — Fixed length tunnel (tunnel must be exactly the given length)
- **Part B** — Bounded length tunnel (tunnel can be up to the given length, unused
  positions set to coordinate 0)

## Tools
- Language: MiniZinc
- Solver: HiGHS

## How to Run
1. Install MiniZinc IDE from https://www.minizinc.org/
2. Open `mineplan.mzn`
3. Select a `.dzn` data file
4. Click Run
