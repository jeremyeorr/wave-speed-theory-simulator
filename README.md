# Wave-Speed Theory Simulator

An interactive educational model of wave-speed limitation, dynamic airway compression, the equal-pressure point, and effort-independent expiratory flow.

The site is dependency-free: all markup, styling, equations, and interaction logic are contained in `index.html`.

## What the simulator shows

- The equal-pressure point, where airway pressure equals pleural pressure and `Ptm = 0`
- The choke point, where local gas velocity reaches the compliant-airway wave speed (`u = c`)
- Loss of upstream pressure-wave propagation when `u - c = 0`
- The plateau in expiratory flow despite increasing expiratory effort
- Effects of elastic recoil, airway area, wall stiffness, resistance, and gas density

## Core equations

Transmural pressure:

```text
Ptm = Paw - Ppl
```

Local gas velocity and compliant-airway wave speed:

```text
u = Vdot / A
c = sqrt(A / (rho * Caw))
Caw = dA / dPtm
```

At the choke point:

```text
u = c
Vdot_max = A * c
```

The simulator uses a logistic tube law:

```text
A(Ptm) = Amax / [1 + exp(-Ptm / S)]
```

`S` is a tube-law pressure scale introduced for this simplified model. At `Ptm = 0`, `Caw = Amax / (4S)`, so larger `S` means a stiffer, less compliant airway.

## Model limitations

This is a steady-state, single-collapsible-airway model with:

- a prescribed logistic tube law;
- uniform pleural pressure;
- linear upstream dissipative resistance; and
- no airway tree, regional heterogeneity, axial tension, flutter, airway closure, or time-dependent effects.

It is intended for physiological education, not clinical prediction.

## Run locally

Open `index.html` in any modern web browser. No installation or build step is required.

## References

1. Dawson SV, Elliott EA. Wave-speed limitation on expiratory flow—a unifying concept. *J Appl Physiol*. 1977;43:498-515.
2. Pedersen OF, Butler JP. Expiratory Flow Limitation. *Compr Physiol*. 2011;1:1861-1882. [doi:10.1002/cphy.c100025](https://doi.org/10.1002/cphy.c100025)
