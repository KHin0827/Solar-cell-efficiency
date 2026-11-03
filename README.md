# Statistical Mechanics of Solar Cells

Toy Project on the thermodynamic efficiency limit of solar cells, based on statistical mechanics.
---

## Overview

This project derives and numerically evaluates the statistical-mechanical efficiency limit of solar cells illuminated by a black-body source. The model assumes:

- The Sun radiates as a black body at temperature \(T\).
- A solar cell absorbs every photon with energy above the band gap \(E_g\).
- Each absorbed photon contributes exactly \(E_g\) of usable work.
- Excess photon energy above \(E_g\) is lost as heat.
- Recombination, reflection, resistance, and other practical losses are neglected.

The notebook derives the photon number density and average photon energy for a black body, formulates the single-junction efficiency, numerically optimizes the band gap, and extends the calculation to a Si-based tandem/multi-junction cell.

---

## Key Formula Summary

Single-junction efficiency:

\[
\eta(E_g)
=
\frac{
\int_{E_g}^{\infty}
\frac{E^2}{e^{E/k_BT}-1}\,dE
}{
2\zeta(3)\langle E_{bb}\rangle
}
\cdot E_g,
\]

with

\[
\langle E_{bb}\rangle
=
\frac{\pi^4}{30\zeta(3)}k_BT
\approx 2.701k_BT.
\]

Equivalently, with \(x=E_g/(k_BT)\),

\[
\eta(x)
=
\frac{I(x)}{2\zeta(3)}
\frac{x}{2.701}.
\]


```python
AVG_OVER_KT = constants.pi**4 / (30 * zeta(3))  # ≈ 2.701
