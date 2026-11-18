---
title: ExB Probe for Ion-Velocity Diagnostics of Electric-Propulsion Plasmas
description: Design, field simulation and test planning for a modular Wien-filter (ExB) probe that separates ion charge states in a thruster plume by velocity.
category: research
importance: 1
img: /assets/img/research/exb-assembly-labelled.png
img_alt: ExB probe assembly with labelled components
period: Sep 2025 – present
affiliation: High-Power Electric Propulsion Lab, School of Aerospace Engineering, Beijing Institute of Technology · Supervisor Prof. Zhang Zhe
role: Research assistant — probe design, CAD/drawings, field and trajectory simulation, test protocol
methods: [SolidWorks, COMSOL Multiphysics, particle tracing, electrostatics, magnetostatics, plasma diagnostics]
status: Ongoing. Measured spectra and detailed simulation results are unpublished and will be added after publication.
---

## Motivation

Hall and gridded ion thrusters produce plumes that contain several ion charge states
(Xe⁺, Xe²⁺, Xe³⁺, …). Knowing the velocity of each population is essential for estimating
thrust efficiency and erosion. An **ExB probe** (Wien filter) does this by crossing an electric
and a magnetic field: only ions whose velocity satisfies _v = E / B_ pass straight through
to the collector, so sweeping the plate voltage at a fixed magnetic field produces a
velocity spectrum of the beam.

## What I am doing

- **Modular probe design.** I designed the probe in SolidWorks with interchangeable parts —
  entrance collimators of several orifice diameters, drift tubes of several lengths, filter
  electrodes and a cone collector — so that resolution and signal level can be traded
  against each other in the experiment. I prepared the full set of manufacturing drawings,
  material choices and the fastener/insulator list for fabrication.
- **Field and trajectory simulation.** In COMSOL I modelled the electric field between the
  filter plates, the magnetic field of the permanent-magnet circuit, and the trajectories of
  a mixed xenon charge-state beam through the probe, including where ions land on the
  collector. These simulations were used to tune the geometry for velocity selection.
- **Test protocol.** The planned measurement places the probe in the plume of a Hall thruster
  and sweeps the plate voltage from **40 V to 220 V** at a fixed magnetic field, combined with
  magnetic-field mapping and sensitive collector-current measurement.

<div class="row mt-3">
  <div class="col-sm mt-3 mt-md-0">
    <img src="/assets/img/research/exb-bfield.png" alt="Magnetic flux density and field lines in the filter section" class="img-fluid rounded z-depth-1" />
  </div>
  <div class="col-sm mt-3 mt-md-0">
    <img src="/assets/img/research/exb-efield.png" alt="Electric field between the filter plates" class="img-fluid rounded z-depth-1" />
  </div>
</div>
<div class="caption">
  COMSOL field maps of the filter section (cross-section): magnetic flux density from the
  permanent-magnet circuit (left) and the electric field between the deflection plates at
  the top of the voltage sweep (right). Shown for illustration; quantitative results are
  withheld until publication.
</div>

<div class="row justify-content-sm-center mt-3">
  <div class="col-sm-12">
    <img src="/assets/img/research/exb-assembly-labelled.png" alt="ExB probe assembly with transparent housing and labelled components" class="img-fluid rounded z-depth-1" />
  </div>
</div>
<div class="row mt-3">
  <div class="col-sm-6 mt-3 mt-md-0">
    <img src="/assets/img/research/exb-assembly.png" alt="ExB probe assembly with closed housing" class="img-fluid rounded z-depth-1" />
  </div>
  <div class="col-sm-6 mt-3 mt-md-0">
    <img src="/assets/img/research/exb-sim-model.png" alt="Simplified probe model used for field simulation" class="img-fluid rounded z-depth-1" />
  </div>
</div>
<div class="caption">
  Probe assembly in SolidWorks: entrance collimator, magnet pair and filter electrodes inside
  the housing, drift tube and cone collector (top); closed housing with mounting flange
  (bottom left); simplified geometry used for the field simulation (bottom right).
</div>

## Related work

The measured ExB spectrum is not identical to the true ion velocity distribution: probe
geometry and finite pass-band broaden and shift the peaks. I studied this as a separate
analytical project — see
[Matrix Analysis for ExB Probe IVDF Reconstruction](/projects/exb-matrix-analysis/).

## Results

<div class="placeholder-box">
  Experimental spectra and analysis will appear here after publication.
</div>
