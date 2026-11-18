---
title: Matrix Analysis for ExB Probe IVDF Reconstruction
description: A linear-algebra view of what an ExB probe really measures, and how to recover the true ion velocity distribution from it.
importance: 3
period: Dec 2025
affiliation: Graduate analytical project, Beijing Institute of Technology
role: Individual project — formulation, analysis and report
methods: [response-matrix modelling, SVD, Tikhonov regularisation, non-negative least squares]
---

## The problem

An ExB probe sweeps a voltage and records collector current, and the resulting spectrum is
often read directly as the ion velocity distribution function (IVDF). It is not. Finite
pass-band, collimator geometry, angular acceptance and non-uniform fields **broaden peaks,
merge neighbouring charge states and bias the velocity scale**. Published analyses report
peak broadening of up to 287 % and about 10 % velocity underestimation when the field at
the filter centre is used.

## Approach

I wrote the measurement as a linear forward model

$$
\mathbf{g} = \mathbf{T}\,\mathbf{f}, \qquad \mathbf{f} \ge 0,
$$

where **f** is the discretised true IVDF, **g** is the measured spectrum and **T** is the
probe's response (transmittance) matrix, built from the geometry, a paraxial trajectory
model and angle averaging, with separate blocks for each charge state.

With that model, standard matrix tools answer practical questions:

- **Conditioning and SVD** — how quickly the singular values of **T** decay sets how much
  fine structure in the IVDF can be recovered at all, and how noise is amplified.
- **Regularised inversion** — plain least squares oscillates; Tikhonov smoothing and
  non-negativity constraints give stable, physical reconstructions.
- **Resolution and uncertainty** — the resolution operator shows what the inversion
  actually returns, and linear error propagation gives honest uncertainty bars.

## Findings

Synthetic tests showed that shortening the collimator and drift sections can merge two
resolved charge-state peaks and sharply worsen the condition number, and that measured peak
widths cannot be read as physical velocity spread unless the response matrix is
deconvolved. The framework also gives a concrete way to report probe configuration,
conditioning metrics and charge-exchange corrections alongside ExB data.

This analysis directly supports my experimental
[ExB probe research](/projects/exb-probe/).
