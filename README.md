# MTT v5.7 — Mass-Torsion Theory (Audit-Ready)

**FROZEN CONSTANTS:** `B0=0.08, M0=200, GAMMA=2.0, K=0.8, LAM=6.0`
Viola-Seaborg: `a=1.64, b=-8.36, c=-0.194, d=-33.0`

## Equations (fully reproducible)

```python
tau_v5(M,S,rho) = B0 * (1-exp(-M/M0)) * exp(-GAMMA*|S|) * (1+K*ln(1+rho))
comp(A,Z,rho) = tau_v5(A, (A-2Z)/A, rho) * A * 0.02
log10(T_half_seconds) = (a*Z+b)/sqrt(Q) + (c*Z+d) + LAM*(comp_parent - comp_daughter - comp_alpha)
