---
title: Thermal and Discharge Characterisation of a 50 A LaB₆ Hollow Cathode
description: Design, fabrication and testing of an instrumented high-current LaB₆ hollow cathode, with in-situ emitter temperature measurement and a 0-D plasma-thermal model.
category: research
importance: 2
img: /assets/img/research/hc-30A.jpg
img_alt: Hollow cathode discharge at 30 A and 10 sccm xenon
period: Jan 2024 – Jun 2025
affiliation: BSc thesis, North China Electric Power University · experiments at Beijing Institute of Technology · Supervisor Dr. Zhang Hui
role: Designed and fabricated the cathode, instrumented it, ran the experiments and built the model
methods: [SolidWorks, AutoCAD, CNC & EDM fabrication, Type-C thermocouples, vacuum testing, MATLAB 0-D model]
status: Undergraduate thesis (June 2025). Full thesis available on request.
---

## Why hollow cathodes

Every Hall and ion thruster needs a hollow cathode: it supplies the electrons that sustain
the discharge and neutralise the ion beam. In a high-current cathode, emitter temperature
sets both the electron emission and the lifetime — too cold and the discharge is unstable,
too hot and the emitter evaporates and erodes. Measuring that temperature _inside_ an
operating cathode is difficult, which is what this project set out to do.

## The cathode

I designed a **50 A-class, heater-less cathode** with a lanthanum hexaboride (LaB₆) emitter
— chosen for its low work function, thermal stability and resistance to poisoning.

<table class="key-facts">
  <tr><th>Emitter</th><td>LaB₆, Ø 6.3 mm × 25.4 mm</td></tr>
  <tr><th>Cathode tube, top and keeper</th><td>Graphite, CNC machined</td></tr>
  <tr><th>Contact electrode</th><td>Tungsten, Ø 2 mm, shaped by EDM</td></tr>
  <tr><th>Temperature sensing</th><td>Type-C (W-Re) thermocouples fed through ports in the keeper to the emitter surface, orifice plate and tube</td></tr>
  <tr><th>Operating range tested</th><td>10–50 A discharge current, 5–20 sccm xenon</td></tr>
  <tr><th>Facility</th><td>JPHM800 vacuum chamber, base pressure below 10⁻⁵ Pa</td></tr>
</table>

<div class="row mt-3">
  <div class="col-sm-6 mt-3 mt-md-0">
    <img src="/assets/img/research/hc-cad.jpg" alt="SolidWorks model of the hollow cathode assembly" class="img-fluid rounded z-depth-1" />
  </div>
  <div class="col-sm-6 mt-3 mt-md-0">
    <img src="/assets/img/research/hc-cad-section.png" alt="Section view of the hollow cathode model" class="img-fluid rounded z-depth-1" />
  </div>
</div>
<div class="caption">SolidWorks model of the cathode assembly (left) and its section view (right).</div>

<div class="row mt-3">
  <div class="col-sm-8 mt-3 mt-md-0">
    <img src="/assets/img/research/hc-thermocouples.jpg" alt="Thermocouples routed into the cathode" class="img-fluid rounded z-depth-1" />
  </div>
  <div class="col-sm-4 mt-3 mt-md-0">
    <img src="/assets/img/research/hc-stand.jpg" alt="Cathode mounted on its aluminium stand" class="img-fluid rounded z-depth-1" />
  </div>
</div>
<div class="caption">
  Thermocouples routed through the keeper ports and sealed with zirconia paste (left);
  the cathode on its mounting stand before installation in the chamber (right).
</div>

## Discharge behaviour

With the cathode running in xenon, I recorded discharge voltage, power and emitter
temperature across the full current and flow-rate range. The photographs below, all at
10 sccm, show the plasma change from a broad, diffuse **plume mode** at low current to a
bright, concentrated **spot mode** at high current.

<div class="row mt-3">
  <div class="col-sm-6 mt-3 mt-md-0">
    <img src="/assets/img/research/hc-20A.jpg" alt="Discharge at 20 A, 10 sccm" class="img-fluid rounded z-depth-1" />
    <div class="caption">20 A</div>
  </div>
  <div class="col-sm-6 mt-3 mt-md-0">
    <img src="/assets/img/research/hc-30A.jpg" alt="Discharge at 30 A, 10 sccm" class="img-fluid rounded z-depth-1" />
    <div class="caption">30 A</div>
  </div>
</div>
<div class="row">
  <div class="col-sm-6 mt-3 mt-md-0">
    <img src="/assets/img/research/hc-40A.jpg" alt="Discharge at 40 A, 10 sccm" class="img-fluid rounded z-depth-1" />
    <div class="caption">40 A</div>
  </div>
  <div class="col-sm-6 mt-3 mt-md-0">
    <img src="/assets/img/research/hc-50A.jpg" alt="Discharge at 50 A, 10 sccm" class="img-fluid rounded z-depth-1" />
    <div class="caption">50 A</div>
  </div>
</div>

<div class="row justify-content-sm-center mt-3">
  <div class="col-sm-12">
    <img src="/assets/img/research/hc-mode-map.jpg" alt="Grid of discharge photographs across current and flow rate" class="img-fluid rounded z-depth-1" />
  </div>
</div>
<div class="caption">
  Discharge appearance across 20–50 A (horizontal) and 5–20 sccm (vertical).
  The transition from plume to spot mode occurs at about 30–35 A.
</div>

<div class="row justify-content-sm-center mt-3">
  <div class="col-sm-8">
    <video controls muted playsinline preload="metadata" src="/assets/video/hc-discharge.mp4" aria-label="Video of the hollow cathode discharge"></video>
  </div>
</div>
<div class="caption">The cathode in operation inside the vacuum chamber.</div>

## Key findings

- **Temperature.** Measured emitter temperatures ranged from about **920 K to 1,470 K**
  over 10–50 A and 5–20 sccm, with a gradient of roughly **400 K** along the cathode —
  large enough to matter for emission uniformity and erosion.
- **Negative-resistance discharge.** At every flow rate the discharge voltage fell as
  current rose (for example from about 27 V at 20 A to 15 V at 50 A at 20 sccm), while
  power increased almost linearly with current. Lower flow rates needed higher voltage
  to sustain the discharge.
- **Mode transition.** The plume-to-spot transition occurred at about **30–35 A**, visible
  both in the photographs and as a change of slope in the operating curves.
- **Model validation.** I wrote a zero-dimensional MATLAB plasma-thermal model of the
  insert, orifice and heat balance. It reproduced the measured trends with current and flow
  rate but **over-predicted temperature by about 18 % at 50 A**, pointing to radiative and
  conductive losses that a 0-D model does not capture.

<div class="placeholder-box">
  Detailed temperature and voltage–current plots will be added after publication.
</div>

## What I would do next

Add non-contact diagnostics (two-colour pyrometry) alongside the thermocouples, extend the
model with explicit radiative and conductive loss terms, and run long-duration tests to
connect the measured temperatures with emitter wear.
