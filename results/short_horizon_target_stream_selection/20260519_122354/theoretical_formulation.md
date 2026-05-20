# Short-Horizon Target-Stream Optimization — Theoretical Formulation

## Problem Statement

We formulate upper-level maneuver generation as a **receding-horizon optimization problem over executable target streams**, rather than low-level actuator commands.

Given:
- Current aircraft state $x_t$
- Reference trajectory $\tau_{ref}$ (waypoints)
- Frozen quaternion-based RL flight skill $\pi_\theta$ (epoch619)

We optimize future executable target-stream parameters $z_{t:t+H}$:

$$\min_z J(x_t, z_{t:t+H}; \pi_\theta, f)$$

where the closed-loop rollout is:

$$target_k = g(z_k, \tau_{ref}, x_k)$$
$$action_k = \pi_\theta(x_k, target_k)$$
$$x_{k+1} = f(x_k, action_k)$$

The target stream parameters are $z = [L, v_{target}, \Delta_{pitch}]$ where:
- $L$: lookahead distance (controls how far ahead the planner looks)
- $v_{target}$: target airspeed (controls energy management)
- $\Delta_{pitch}$: pitch offset (controls climb/descent shaping)

The cost function:

$$J = J_{track} + J_{geom} + J_{energy} + J_{safe} + J_{smooth}$$

## Key Empirical Finding

**The optimal target-stream parameters vary drastically by task type, and can be opposite across tasks:**

| Task | Best (L, vt) | CTE_p90 | Default (1000,250) CTE_p90 | Spread |
|------|-------------|---------|---------------------------|--------|
| S-curve | (600, 220) | 918m | 1503m | 64% |
| Figure-8 | (600, 220) | 1017m | 1039m | 34% |
| Helix | (600, 220) | 524m | 691m | 115% |
| **90° Vert.** | **(1500, 280)** | **51m** | 96m | **359%** |

**Critical insight**: Horizontal/curved tasks prefer *smaller* lookahead and *lower* speed (L=600, vt=220). Vertical pull-up prefers *larger* lookahead and *higher* speed (L=1500, vt=280). The optimal directions are **opposite** — no single fixed parameter works well across all tasks.

This directly validates the RH-TSO framing.

## Method Comparison

### A. Fixed Moving-Lookahead (Baseline)

Fixed $L = L_0$, $v_t = v_0$ for the entire trajectory.

**Pros**: Simplest, fastest (no optimization overhead).
**Cons**: Suboptimal for most tasks; 34-359% CTE degradation vs task-adapted params.

### B. Lattice / Parallel Shooting

At each replan interval, enumerate candidate $(L, v_t, \Delta_{pitch})$ over a discrete grid, simulate $H$ steps of closed-loop rollout for each candidate, and select the one with minimum cost.

**Number of evaluations per replan**: $|L| \times |v_t| \times |\Delta_{pitch}| = 4 \times 3 \times 3 = 36$

**Pros**: Guarantees grid-optimal selection, easy to implement, explainable.
**Cons**: 36× horizon evaluations per replan — can be slow without JAX parallelization.

### C. Beam Search Target-Stream Tree

At each depth, expand top-K partial streams with all candidates. Keep top-K for next depth.

**Complexity**: $K \times |candidates| \times H$ per replan.

**Pros**: Has tree-search methodology flavor.
**Cons**: Much slower than lattice; implementation complexity; no benefit over lattice for short horizons.

### D. CEM/MPPI-style Target-Stream Sampling

Sample $N$ candidate parameter vectors from Gaussian, evaluate via parallel rollouts, select elite samples, update distribution.

**Pros**: Most "robot-learning" flavor, works well for continuous parameter spaces.
**Cons**: Requires tuning (N, elite_frac, iterations); stochastic convergence.

## Recommendation

**Use Lattice / Parallel Shooting for the paper.**

1. It has the clearest theoretical exposition: "We discretize the target-stream parameter space and evaluate candidate streams through GPU-parallel closed-loop rollouts of the frozen flight skill."
2. With JAX vmapped parallel rollouts, 36 evaluations can be done in ~1 batch.
3. It is the simplest to explain and most reliable.
4. The empirical validation from the parameter sweep clearly demonstrates the need for task-adaptive parameter selection.

**Naming**: Receding-Horizon Target-Stream Optimization (RH-TSO).

## What NOT to claim

- This is NOT actuator-space MPC
- This is NOT global optimal
- This does NOT solve full-loop / inverted flight
- The optimization is over a DISCRETE grid, not continuous
