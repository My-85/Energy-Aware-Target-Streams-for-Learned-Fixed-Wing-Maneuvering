# Vertical Energy Fine-Tune Report

- Source checkpoint: `results/heading_pitch_V_discrete_rnn_2026-05-13-21-17/checkpoints/checkpoint_epoch_600`
- Saved checkpoint: `results/vertical_energy_finetune/20260515_1615/checkpoint/checkpoint_epoch_619`
- Total timesteps: `5000000`
- Learning rate: `0.0001`
- Eval seeds per task: `1` (quick GPU gate, not a statistical pass)

## Required Answers

- 15 pullup R3000: baseline success=1, vt_min=186.148, energy_loss=14336.603; fine-tuned success=1, vt_min=200.093, energy_loss=11658.369.
- 15 pullup R2000: baseline success=1, vt_min=186.148, energy_loss=14336.603; fine-tuned success=1, vt_min=200.093, energy_loss=11658.369.
- 30 pullup R8000: baseline success=1, vt_min=186.148, energy_loss=14336.603; fine-tuned success=1, vt_min=199.897, energy_loss=11697.034.
- 30 pullup R5000: baseline success=1, vt_min=185.855, energy_loss=14340.867; fine-tuned success=1, vt_min=199.380, energy_loss=11800.443.

1. 15 deg pull-up R=3000 / R=2000 improved: compare rows above; this quick gate is inconclusive unless success/vt_min improve consistently across seeds.
2. 30 deg pull-up completion: see 30 pull-up rows above.
3. vt_min improved: see `eval_summary.csv` vt_min columns.
4. Energy loss decreased: see `eval_summary.csv` energy_loss columns.
5. alpha/G controllable: see alpha_max and Gmax columns.
6. Original horizontal-task regression: see level/heading/pitch rows; circle and S-curve still need planner-level eval.
7. Ready for 60/90 deg arc: not yet; run multi-seed pull-up gate first.
8. Next recommendation: run multi-seed eval, then extend to Stage 8/9 only if R=3000 and 30 deg R=8000 pass without original-task regression.
