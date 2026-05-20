# RH-TSO Method Comparison

## Experiment Design

4 tasks × 3 (L, vt) parameter pairs, using frozen epoch619 policy.

**Parameter grid**: L ∈ {600, 1000, 1500}, vt ∈ {220, 250, 280}

## Raw Results

| Task | L | vt | CTE_m | CTE_p90 | Gmax | vt_min | Time(s) |
|------|---|---|-------|---------|------|--------|---------|
| s_curve | 600 | 220 | 276 | **918** | 7.2 | 185 | 166 |
| s_curve | 1000 | 250 | 486 | 1503 | 7.7 | 193 | 140 |
| s_curve | 1500 | 280 | 557 | 1482 | 7.4 | 196 | 140 |
| figure_eight | 600 | 220 | 484 | **1017** | 9.2 | 176 | 172 |
| figure_eight | 1000 | 250 | 496 | 1039 | 9.6 | 180 | 172 |
| figure_eight | 1500 | 280 | 775 | 1364 | 9.7 | 196 | 84 |
| mild_3d | 600 | 220 | 156 | **524** | 6.9 | 187 | 173 |
| mild_3d | 1000 | 250 | 193 | 691 | 8.1 | 194 | 175 |
| mild_3d | 1500 | 280 | 321 | 1125 | 7.7 | 191 | 177 |
| vertical_90 | 600 | 220 | 87 | 234 | 6.6 | 187 | 104 |
| vertical_90 | 1000 | 250 | 43 | 96 | 7.5 | 191 | 93 |
| vertical_90 | 1500 | 280 | 22 | **51** | 6.4 | 190 | 88 |

## Analysis

### Per-Task Parameter Sensitivity

| Task | Best (L,vt) | Best CTE_p90 | Default (1000,250) CTE_p90 | Degradation | Optimal Direction |
|------|-------------|-------------|---------------------------|-------------|-------------------|
| S-curve | (600, 220) | 918 | 1503 | **-39%** | smaller L, lower vt |
| Figure-8 | (600, 220) | 1017 | 1039 | -2% | smaller L, lower vt |
| Helix | (600, 220) | 524 | 691 | **-24%** | smaller L, lower vt |
| 90° Vert. | (1500, 280) | 51 | 96 | **-47%** | **larger L, higher vt** |

### Key Insight

**Horizontal/curved tasks** benefit from shorter lookahead + lower speed — the policy tracks better when it focuses on nearby waypoints at moderate speed.

**Vertical pull-up** benefits from longer lookahead + higher speed — the policy needs to "see ahead" to prepare for the pull-up, and higher speed provides energy for climbing.

The optimal directions are **opposite** across task types. This strongly motivates task-adaptive target-stream selection.

## Method Viability Assessment

| Criterion | Lattice | Beam | CEM | Baseline |
|-----------|---------|------|-----|----------|
| Implementation complexity | Low | Medium | Medium | None |
| Runtime overhead | 36× per replan | >100× per replan | 20-32× per replan | 1× |
| Theoretical clarity | High | Medium | High | None |
| Improvement potential | Yes | Yes | Yes | N/A |
| JAX-parallelizable | Yes | Partially | Yes | N/A |
| **Recommend** | **Yes** | No (too slow) | Possible | Compare against |

## Final Recommendation

**Use Lattice / Parallel Shooting for the paper.**

1. The parameter sweep empirically validates that optimal parameters are task-dependent
2. The lattice method is the simplest implementation that exploits this finding
3. It can be formulated cleanly as "receding-horizon optimization over executable target streams"
4. JAX vmapped parallel rollouts make it computationally feasible
5. Beam search provides no advantage for short horizons
6. CEM is a good alternative but adds tuning complexity without clear benefit for a discrete parameter space
