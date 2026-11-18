---
title: Conceptual Design of a Hypersonic VTOL Mars Rocket Aircraft
description: '"Ares Kestrel" — a two-crew, LH₂/LO₂ rocket aircraft for rapid point-to-point travel on Mars, sized from an OpenVSP model.'
importance: 1
img: /assets/img/projects/thumb-mars.png
img_alt: Labelled configuration layout of the Ares Kestrel Mars rocket aircraft
period: Jul 2026
affiliation: Modern Aircraft Configuration Design (graduate course), Beijing Institute of Technology
role: Individual project — configuration, OpenVSP model, mass and performance analysis, report
methods: [OpenVSP, MassProp, MATLAB, rocket equation, configuration design]
---

## The idea

Getting around Mars is hard: there are no runways, the air is too thin for conventional
wings to do much at low speed, and ground rovers are slow. This study asks what a
**runway-independent, crewed rocket aircraft** would look like if it had to take off and
land vertically, carry two crew and a 500 kg payload, and cover long distances quickly
using liquid-hydrogen / liquid-oxygen propulsion.

<div class="row justify-content-sm-center mt-3">
  <div class="col-sm-12">
    <img src="/assets/img/projects/mars-mission.png" alt="Reference mission sequence" class="img-fluid rounded z-depth-1" />
  </div>
</div>
<div class="caption">Reference mission: vertical take-off, boost, high-speed flight, return and vertical landing.</div>

## Configuration

After comparing a rotorcraft, a pure ballistic hopper, a lifting body and a winged rocket
aircraft, I selected the winged configuration: a central fuselage with a forward two-crew
canopy, a cranked-delta wing, aft control strakes, canted twin vertical tails, twin aft
rocket engines and a dedicated VTOL propulsion allowance. The LH₂ and LO₂ tanks sit near
the centre of gravity because propellant dominates the mass.

<div class="row mt-3">
  <div class="col-sm-6 mt-3 mt-md-0">
    <img src="/assets/img/projects/mars-top.png" alt="OpenVSP top view" class="img-fluid rounded z-depth-1" />
  </div>
  <div class="col-sm-6 mt-3 mt-md-0">
    <img src="/assets/img/projects/mars-side.png" alt="OpenVSP side view" class="img-fluid rounded z-depth-1" />
  </div>
</div>
<div class="row justify-content-sm-center mt-3">
  <div class="col-sm-12">
    <img src="/assets/img/projects/mars-front.png" alt="OpenVSP front view" class="img-fluid rounded z-depth-1" />
  </div>
</div>
<div class="caption">OpenVSP top, side and front views.</div>

<table class="key-facts">
  <tr><th>Gross mass (OpenVSP MassProp)</th><td>48,096 kg</td></tr>
  <tr><th>Propellant</th><td>35,000 kg (10,000 kg LH₂ + 25,000 kg LO₂)</td></tr>
  <tr><th>Payload</th><td>500 kg, plus two crew</td></tr>
  <tr><th>Wing span / area</th><td>17.83 m / 48.86 m²</td></tr>
  <tr><th>Fuselage length</th><td>15.90 m</td></tr>
</table>

## Mass and propulsion

Rather than guessing a gross mass, I built the mass budget directly from the OpenVSP
component point masses and checked it against the MassProp total.

<div class="row mt-3">
  <div class="col-sm-6 mt-3 mt-md-0">
    <img src="/assets/img/projects/mars-mass.png" alt="Mass budget" class="img-fluid rounded z-depth-1" />
  </div>
  <div class="col-sm-6 mt-3 mt-md-0">
    <img src="/assets/img/projects/mars-propulsion.png" alt="LH2/LO2 propulsion architecture" class="img-fluid rounded z-depth-1" />
  </div>
</div>
<div class="caption">Mass budget reconciled to the OpenVSP total (left) and the conceptual LH₂/LO₂ propulsion architecture (right).</div>

## Performance

With an assumed specific impulse of 450 s, the actual mass ratio gives an ideal
**Δv of about 5.7 km/s**. With an assumed 240 kN of installed thrust, the gross
**Mars thrust-to-weight ratio is about 1.35** — enough for vertical lift-off in a
first-order sense, but with little margin for gravity losses, hover, divert or abort.

<div class="row mt-3">
  <div class="col-sm-6 mt-3 mt-md-0">
    <img src="/assets/img/projects/mars-deltav.png" alt="Delta-v sensitivity" class="img-fluid rounded z-depth-1" />
  </div>
  <div class="col-sm-6 mt-3 mt-md-0">
    <img src="/assets/img/projects/mars-tw.png" alt="Mars thrust-to-weight ratio" class="img-fluid rounded z-depth-1" />
  </div>
</div>
<div class="caption">Δv sensitivity to propellant fraction and specific impulse (left); Mars thrust-to-weight at gross, mid-burn and burnout mass (right).</div>

## Honest limits

The study is deliberately explicit about what it does _not_ show: a 35-tonne propellant
load only makes sense with in-situ propellant production on Mars; the thrust margin is
thin for a crewed vehicle; there are no validated hypersonic aerodynamic or heating data
yet; and human-rating items (abort, shielding, redundancy) are not yet in the mass budget.
The next iteration should be a mass-ratio and operations-closure study, not a styling
exercise.
