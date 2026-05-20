# Vertical Arc Loop-Quality Evaluation

**Checkpoint:** epoch 619 (vertical-energy fine-tuned)
**Date:** 20260517_173622
**Target:** loop-plane full-attitude (roll computed from rotation matrix)

## Grading Criteria

### Loop-Quality Grade (NEW)

| Criterion | A | B | C | Fail |
|-----------|---|---|---|------|
| CTE_mean | <100m | <500m | - | - |
| CTE_p90 | <300m | <1200m | - | - |
| CTE_max | <800m | - | - | - |
| velocity_tangent_error | <15° | <30° | - | - |
| nose_tangent_error | <15° | <30° | - | - |
| nose_velocity_error | <15° | - | - | - |
| wing_plane_error | <15° | - | - | - |
| q_error (attitude) | <0.5 rad | - | - | - |
| Gmax | <9 | <10 | - | - |
| vt_min | ≥190 m/s | ≥175 m/s | - | - |
| Completed | yes | yes | yes | no |

### CTE-Only Grade (DEPRECATED)

| Criterion | A | B | C | Fail |
|-----------|---|---|---|------|
| CTE_mean | <100m | <500m | - | - |
| CTE_p90 | <300m | <1200m | - | - |
| CTE_max | <800m | - | - | - |
| Gmax | <9 | <10 | - | - |
| vt_min | ≥190 m/s | ≥175 m/s | - | - |

## Results Summary

| Angle | R | CTE_m | v_tang | n_tang | n_vel | wing_p | belly | q_err | Gmax | vt_min | α range | Loop Grade | CTE-Grade (depr.) |
|-------|---|-------|--------|--------|-------|--------|-------|-------|------|--------|---------|------------|-------------------|
| 60° | 8000 | 80 | 6.4° | 8.8° | 5.8° | 34.4° | 145.0° | 0.085 | 5.8 | 194 | [-23,8] | **B** | A |
| 60° | 10000 | 69 | 4.8° | 6.9° | 4.7° | 27.8° | 151.7° | 0.070 | 5.8 | 194 | [-23,7] | **B** | A |
| 90° | 10000 | 54 | 3.5° | 5.8° | 4.1° | 20.0° | 159.0° | 0.066 | 5.8 | 194 | [-23,6] | **B** | A |
| 90° | 12000 | 56 | 3.1° | 5.5° | 4.0° | 17.4° | 161.6° | 0.067 | 5.8 | 194 | [-23,5] | **B** | A |
| 105° | 10000 | 54 | 3.5° | 5.7° | 4.3° | 21.6° | 157.2° | 0.120 | 5.8 | 194 | [-23,9] | **B** | A |
| 105° | 12000 | 63 | 3.3° | 5.8° | 4.6° | 20.3° | 158.5° | 0.112 | 5.8 | 194 | [-23,11] | **B** | A |
| 120° | 10000 | 53 | 3.4° | 5.6° | 4.1° | 18.9° | 159.6° | 0.108 | 5.8 | 194 | [-23,11] | **B** | A |
| 120° | 12000 | 58 | 3.6° | 5.5° | 4.4° | 17.9° | 160.8° | 0.100 | 5.8 | 194 | [-23,9] | **B** | A |
| 135° | 12000 | 59 | 3.7° | 5.0° | 4.3° | 16.2° | 162.4° | 0.095 | 5.8 | 194 | [-23,9] | **B** | A |
| 150° | 12000 | 72 | 3.7° | 5.1° | 4.5° | 15.0° | 163.8° | 0.092 | 5.8 | 194 | [-23,11] | **B** | A |
| 180° | 15000 | 6101 | 63.9° | 62.6° | 18.9° | 77.5° | 129.6° | 0.893 | 7.8 | 194 | [-42,24] | **Fail** | Fail |
| 180° | 12000 | 11362 | 58.5° | 58.1° | 19.3° | 74.8° | 130.2° | 1.197 | 8.5 | 194 | [-44,10] | **Fail** | Fail |

## Per-Angle Detailed Metrics

### 60° Vertical Arc (R=8000m)

- **Loop Grade:** B | CTE-only (depr.): A
- Steps: 173 | Termination: ok

| Metric | Value |
|--------|-------|
| CTE_mean | 80.439 |
| CTE_p90 | 169.721 |
| CTE_max | 193.633 |
| velocity_tangent_error_mean | 6.445 |
| velocity_tangent_error_p90 | 14.838 |
| nose_tangent_error_mean | 8.782 |
| nose_tangent_error_p90 | 18.983 |
| nose_velocity_error_mean | 5.752 |
| nose_velocity_error_p90 | 13.037 |
| wing_plane_error_mean | 34.401 |
| wing_plane_error_p90 | 126.480 |
| belly_error_mean | 145.040 |
| q_error_mean_rad | 0.085 |
| q_error_p90_rad | 0.218 |
| roll_tracking_error_mean | 3.948 |
| env_alpha_min | -22.840 |
| env_alpha_max | 7.722 |
| env_alpha_mean | -0.542 |
| target_roll_min | -168.153 |
| target_roll_max | 161.187 |
| actual_roll_min | -178.886 |
| actual_roll_max | 170.749 |
| Gmax | 5.841 |
| vt_min | 193.963 |

### 60° Vertical Arc (R=10000m)

- **Loop Grade:** B | CTE-only (depr.): A
- Steps: 212 | Termination: ok

| Metric | Value |
|--------|-------|
| CTE_mean | 68.712 |
| CTE_p90 | 171.154 |
| CTE_max | 201.975 |
| velocity_tangent_error_mean | 4.834 |
| velocity_tangent_error_p90 | 13.792 |
| nose_tangent_error_mean | 6.904 |
| nose_tangent_error_p90 | 18.058 |
| nose_velocity_error_mean | 4.707 |
| nose_velocity_error_p90 | 8.526 |
| wing_plane_error_mean | 27.827 |
| wing_plane_error_p90 | 114.850 |
| belly_error_mean | 151.703 |
| q_error_mean_rad | 0.070 |
| q_error_p90_rad | 0.206 |
| roll_tracking_error_mean | 3.362 |
| env_alpha_min | -22.840 |
| env_alpha_max | 6.989 |
| env_alpha_mean | -0.160 |
| target_roll_min | -168.153 |
| target_roll_max | 161.187 |
| actual_roll_min | -178.886 |
| actual_roll_max | 170.749 |
| Gmax | 5.841 |
| vt_min | 193.889 |

### 90° Vertical Arc (R=10000m)

- **Loop Grade:** B | CTE-only (depr.): A
- Steps: 314 | Termination: ok

| Metric | Value |
|--------|-------|
| CTE_mean | 53.928 |
| CTE_p90 | 146.312 |
| CTE_max | 207.285 |
| velocity_tangent_error_mean | 3.499 |
| velocity_tangent_error_p90 | 9.244 |
| nose_tangent_error_mean | 5.792 |
| nose_tangent_error_p90 | 13.701 |
| nose_velocity_error_mean | 4.110 |
| nose_velocity_error_p90 | 5.915 |
| wing_plane_error_mean | 20.033 |
| wing_plane_error_p90 | 80.896 |
| belly_error_mean | 158.951 |
| q_error_mean_rad | 0.066 |
| q_error_p90_rad | 0.195 |
| roll_tracking_error_mean | 3.969 |
| env_alpha_min | -22.840 |
| env_alpha_max | 5.732 |
| env_alpha_mean | 0.793 |
| target_roll_min | -168.153 |
| target_roll_max | 161.187 |
| actual_roll_min | -178.886 |
| actual_roll_max | 170.749 |
| Gmax | 5.841 |
| vt_min | 193.889 |

### 90° Vertical Arc (R=12000m)

- **Loop Grade:** B | CTE-only (depr.): A
- Steps: 377 | Termination: ok

| Metric | Value |
|--------|-------|
| CTE_mean | 56.296 |
| CTE_p90 | 152.545 |
| CTE_max | 238.334 |
| velocity_tangent_error_mean | 3.142 |
| velocity_tangent_error_p90 | 10.120 |
| nose_tangent_error_mean | 5.535 |
| nose_tangent_error_p90 | 13.068 |
| nose_velocity_error_mean | 4.020 |
| nose_velocity_error_p90 | 5.426 |
| wing_plane_error_mean | 17.429 |
| wing_plane_error_p90 | 66.217 |
| belly_error_mean | 161.608 |
| q_error_mean_rad | 0.067 |
| q_error_p90_rad | 0.200 |
| roll_tracking_error_mean | 5.881 |
| env_alpha_min | -22.840 |
| env_alpha_max | 4.519 |
| env_alpha_mean | 1.128 |
| target_roll_min | -168.153 |
| target_roll_max | 161.187 |
| actual_roll_min | -178.886 |
| actual_roll_max | 170.749 |
| Gmax | 5.841 |
| vt_min | 193.889 |

### 105° Vertical Arc (R=10000m)

- **Loop Grade:** B | CTE-only (depr.): A
- Steps: 366 | Termination: ok

| Metric | Value |
|--------|-------|
| CTE_mean | 53.821 |
| CTE_p90 | 132.785 |
| CTE_max | 207.161 |
| velocity_tangent_error_mean | 3.463 |
| velocity_tangent_error_p90 | 8.785 |
| nose_tangent_error_mean | 5.701 |
| nose_tangent_error_p90 | 12.712 |
| nose_velocity_error_mean | 4.336 |
| nose_velocity_error_p90 | 6.316 |
| wing_plane_error_mean | 21.563 |
| wing_plane_error_p90 | 86.274 |
| belly_error_mean | 157.243 |
| q_error_mean_rad | 0.120 |
| q_error_p90_rad | 0.231 |
| roll_tracking_error_mean | 8.533 |
| env_alpha_min | -22.840 |
| env_alpha_max | 8.577 |
| env_alpha_mean | 1.165 |
| target_roll_min | -168.153 |
| target_roll_max | 180.000 |
| actual_roll_min | -179.213 |
| actual_roll_max | 179.693 |
| Gmax | 5.841 |
| vt_min | 193.889 |

### 105° Vertical Arc (R=12000m)

- **Loop Grade:** B | CTE-only (depr.): A
- Steps: 439 | Termination: ok

| Metric | Value |
|--------|-------|
| CTE_mean | 62.716 |
| CTE_p90 | 138.327 |
| CTE_max | 238.436 |
| velocity_tangent_error_mean | 3.350 |
| velocity_tangent_error_p90 | 9.479 |
| nose_tangent_error_mean | 5.757 |
| nose_tangent_error_p90 | 12.251 |
| nose_velocity_error_mean | 4.558 |
| nose_velocity_error_p90 | 8.717 |
| wing_plane_error_mean | 20.328 |
| wing_plane_error_p90 | 80.016 |
| belly_error_mean | 158.529 |
| q_error_mean_rad | 0.112 |
| q_error_p90_rad | 0.230 |
| roll_tracking_error_mean | 6.842 |
| env_alpha_min | -22.840 |
| env_alpha_max | 11.257 |
| env_alpha_mean | 1.745 |
| target_roll_min | -168.153 |
| target_roll_max | 180.000 |
| actual_roll_min | -179.991 |
| actual_roll_max | 179.498 |
| Gmax | 5.841 |
| vt_min | 193.889 |

### 120° Vertical Arc (R=10000m)

- **Loop Grade:** B | CTE-only (depr.): A
- Steps: 418 | Termination: ok

| Metric | Value |
|--------|-------|
| CTE_mean | 53.298 |
| CTE_p90 | 122.478 |
| CTE_max | 207.190 |
| velocity_tangent_error_mean | 3.429 |
| velocity_tangent_error_p90 | 8.402 |
| nose_tangent_error_mean | 5.646 |
| nose_tangent_error_p90 | 11.197 |
| nose_velocity_error_mean | 4.095 |
| nose_velocity_error_p90 | 6.848 |
| wing_plane_error_mean | 18.934 |
| wing_plane_error_p90 | 78.530 |
| belly_error_mean | 159.574 |
| q_error_mean_rad | 0.108 |
| q_error_p90_rad | 0.224 |
| roll_tracking_error_mean | 7.427 |
| env_alpha_min | -22.840 |
| env_alpha_max | 11.031 |
| env_alpha_mean | 1.303 |
| target_roll_min | -168.153 |
| target_roll_max | 180.000 |
| actual_roll_min | -179.974 |
| actual_roll_max | 179.811 |
| Gmax | 5.841 |
| vt_min | 193.889 |

### 120° Vertical Arc (R=12000m)

- **Loop Grade:** B | CTE-only (depr.): A
- Steps: 500 | Termination: ok

| Metric | Value |
|--------|-------|
| CTE_mean | 58.070 |
| CTE_p90 | 121.256 |
| CTE_max | 238.389 |
| velocity_tangent_error_mean | 3.640 |
| velocity_tangent_error_p90 | 8.825 |
| nose_tangent_error_mean | 5.460 |
| nose_tangent_error_p90 | 10.245 |
| nose_velocity_error_mean | 4.447 |
| nose_velocity_error_p90 | 6.844 |
| wing_plane_error_mean | 17.912 |
| wing_plane_error_p90 | 69.523 |
| belly_error_mean | 160.787 |
| q_error_mean_rad | 0.100 |
| q_error_p90_rad | 0.209 |
| roll_tracking_error_mean | 6.611 |
| env_alpha_min | -22.840 |
| env_alpha_max | 9.238 |
| env_alpha_mean | 1.559 |
| target_roll_min | -168.153 |
| target_roll_max | 180.000 |
| actual_roll_min | -179.772 |
| actual_roll_max | 179.977 |
| Gmax | 5.841 |
| vt_min | 193.889 |

### 135° Vertical Arc (R=12000m)

- **Loop Grade:** B | CTE-only (depr.): A
- Steps: 559 | Termination: ok

| Metric | Value |
|--------|-------|
| CTE_mean | 59.213 |
| CTE_p90 | 120.069 |
| CTE_max | 244.734 |
| velocity_tangent_error_mean | 3.706 |
| velocity_tangent_error_p90 | 6.922 |
| nose_tangent_error_mean | 5.043 |
| nose_tangent_error_p90 | 7.533 |
| nose_velocity_error_mean | 4.305 |
| nose_velocity_error_p90 | 6.402 |
| wing_plane_error_mean | 16.206 |
| wing_plane_error_p90 | 60.382 |
| belly_error_mean | 162.382 |
| q_error_mean_rad | 0.095 |
| q_error_p90_rad | 0.197 |
| roll_tracking_error_mean | 6.172 |
| env_alpha_min | -22.840 |
| env_alpha_max | 9.304 |
| env_alpha_mean | 1.160 |
| target_roll_min | -168.153 |
| target_roll_max | 180.000 |
| actual_roll_min | -179.994 |
| actual_roll_max | 179.906 |
| Gmax | 5.841 |
| vt_min | 193.889 |

### 150° Vertical Arc (R=12000m)

- **Loop Grade:** B | CTE-only (depr.): A
- Steps: 620 | Termination: ok

| Metric | Value |
|--------|-------|
| CTE_mean | 71.606 |
| CTE_p90 | 181.189 |
| CTE_max | 326.215 |
| velocity_tangent_error_mean | 3.712 |
| velocity_tangent_error_p90 | 6.649 |
| nose_tangent_error_mean | 5.078 |
| nose_tangent_error_p90 | 8.840 |
| nose_velocity_error_mean | 4.539 |
| nose_velocity_error_p90 | 6.451 |
| wing_plane_error_mean | 15.040 |
| wing_plane_error_p90 | 49.235 |
| belly_error_mean | 163.823 |
| q_error_mean_rad | 0.092 |
| q_error_p90_rad | 0.191 |
| roll_tracking_error_mean | 5.804 |
| env_alpha_min | -22.840 |
| env_alpha_max | 10.687 |
| env_alpha_mean | 0.478 |
| target_roll_min | -168.153 |
| target_roll_max | 180.000 |
| actual_roll_min | -179.975 |
| actual_roll_max | 179.979 |
| Gmax | 5.841 |
| vt_min | 193.889 |

### 180° Vertical Arc (R=15000m)

- **Loop Grade:** Fail | CTE-only (depr.): Fail
- Steps: 2000 | Termination: crash

| Metric | Value |
|--------|-------|
| CTE_mean | 6101.139 |
| CTE_p90 | 19515.614 |
| CTE_max | 23944.087 |
| velocity_tangent_error_mean | 63.876 |
| velocity_tangent_error_p90 | 140.641 |
| nose_tangent_error_mean | 62.581 |
| nose_tangent_error_p90 | 131.719 |
| nose_velocity_error_mean | 18.889 |
| nose_velocity_error_p90 | 34.833 |
| wing_plane_error_mean | 77.464 |
| wing_plane_error_p90 | 162.756 |
| belly_error_mean | 129.646 |
| q_error_mean_rad | 0.893 |
| q_error_p90_rad | 2.781 |
| roll_tracking_error_mean | 29.386 |
| env_alpha_min | -42.085 |
| env_alpha_max | 24.166 |
| env_alpha_mean | -14.228 |
| target_roll_min | -168.153 |
| target_roll_max | 180.000 |
| actual_roll_min | -180.000 |
| actual_roll_max | 179.956 |
| Gmax | 7.820 |
| vt_min | 193.889 |

### 180° Vertical Arc (R=12000m)

- **Loop Grade:** Fail | CTE-only (depr.): Fail
- Steps: 2000 | Termination: crash

| Metric | Value |
|--------|-------|
| CTE_mean | 11361.525 |
| CTE_p90 | 39274.888 |
| CTE_max | 50388.059 |
| velocity_tangent_error_mean | 58.470 |
| velocity_tangent_error_p90 | 127.019 |
| nose_tangent_error_mean | 58.058 |
| nose_tangent_error_p90 | 112.554 |
| nose_velocity_error_mean | 19.328 |
| nose_velocity_error_p90 | 35.408 |
| wing_plane_error_mean | 74.805 |
| wing_plane_error_p90 | 137.609 |
| belly_error_mean | 130.172 |
| q_error_mean_rad | 1.197 |
| q_error_p90_rad | 2.908 |
| roll_tracking_error_mean | 36.524 |
| env_alpha_min | -44.119 |
| env_alpha_max | 9.547 |
| env_alpha_mean | -15.686 |
| target_roll_min | -168.153 |
| target_roll_max | 180.000 |
| actual_roll_min | -179.972 |
| actual_roll_max | 179.988 |
| Gmax | 8.473 |
| vt_min | 193.889 |

## Demo Categories

### Main Demo

| Angle | R | CTE_m | wing_p | Grade |
|-------|---|-------|--------|-------|
| 60° | 8000 | 80 | 34.4° | **B** |
| 60° | 10000 | 69 | 27.8° | **B** |
| 90° | 10000 | 54 | 20.0° | **B** |
| 90° | 12000 | 56 | 17.4° | **B** |

### Boundary Demo

| Angle | R | CTE_m | wing_p | Grade |
|-------|---|-------|--------|-------|
| 105° | 10000 | 54 | 21.6° | **B** |
| 105° | 12000 | 63 | 20.3° | **B** |
| 120° | 10000 | 53 | 18.9° | **B** |
| 120° | 12000 | 58 | 17.9° | **B** |
| 135° | 12000 | 59 | 16.2° | **B** |
| 150° | 12000 | 72 | 15.0° | **B** |

### Failure Diagnosis

| Angle | R | CTE_m | v_tang | n_tang | wing_p | q_err | Gmax | vt_min |
|-------|---|-------|--------|--------|--------|-------|------|--------|
| 180° | 15000 | 6101 | 63.9° | 62.6° | 77.5° | 0.893 | 7.8 | 194 |
| 180° | 12000 | 11362 | 58.5° | 58.1° | 74.8° | 1.197 | 8.5 | 194 |

## Key Findings

- A: 0, B: 10, C: 0, Fail: 2

### Grade Transitions vs CTE-only

| Angle | R | CTE-only | Loop-Quality | Key Regressor |
|-------|---|----------|--------------|---------------|
| 60° | 8000 | A | **B** | wing_p |
| 60° | 10000 | A | **B** | wing_p |
| 90° | 10000 | A | **B** | wing_p |
| 90° | 12000 | A | **B** | wing_p |
| 105° | 10000 | A | **B** | wing_p |
| 105° | 12000 | A | **B** | wing_p |
| 120° | 10000 | A | **B** | wing_p |
| 120° | 12000 | A | **B** | wing_p |
| 135° | 12000 | A | **B** | wing_p |
| 150° | 12000 | A | **B** | wing_p |
