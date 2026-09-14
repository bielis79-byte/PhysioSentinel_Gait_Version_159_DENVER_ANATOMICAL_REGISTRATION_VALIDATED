# PhysioSentinel Gait · Version 158

## Denver semantic anatomical registration

Version 158 replaces the V157 foot-only roll correction with semantic anatomical frames validated before packaging:

- pelvis: sacrum/coccyx define the posterior direction;
- thigh: patella defines the anterior direction in both limbs;
- foot: medial vs lateral cuneiform geometry defines the medial axis, while calcaneus→phalanges preserves heel→toe progression;
- target SKEL frames use the same semantics, avoiding mirrored but visually plausible registrations;
- no change to the original 75-frame SKEL `poses`, `joints` or skin mesh.

## Foot/ankle QC v2

- Heel/Toe geometric confidence and detector confidence when present.
- Temporal continuity of the foot axis and ankle angle.
- Talus–calcaneus–toes consistency.
- Support/swing state QC with 2D IC/TO as primary source when available and 3D distal height+velocity as an auxiliary fallback.
- Double support, right/left single support, right/left swing and simultaneous-flight checks.
- Phase-specific ankle-angle summaries without automatically relabelling sign as dorsiflexion/plantarflexion unless model convention is confirmed.
- Inversion/eversion is explicitly marked orientative/low-confidence when subtalar dynamics are absent or insufficient.

## Exports

Tab 12 additionally exports:

- `11_estados_apoyo_swing_resumen.csv`
- `12_estados_apoyo_swing_por_frame.csv`

The existing foot QC CSV/JSON exports remain available.
