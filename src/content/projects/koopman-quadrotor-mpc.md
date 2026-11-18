---
title: Koopman-EDMD Modelling and MPC for Quadrotor Tracking
description: Reproduction and analysis of a data-driven control pipeline — learn a lifted linear model of a quadrotor with EDMD, then track a 3-D trajectory with model predictive control.
importance: 2
img: /assets/img/projects/thumb-koopman.png
img_alt: 3-D trajectory tracking of the quadrotor under lifted-space MPC
period: Jan 2026
affiliation: Aircraft Guidance and Control Theory (graduate course), Beijing Institute of Technology
role: Individual project — reproduced the MATLAB workflow, analysed the method and results, wrote the report
methods: [MATLAB, Koopman operator, EDMD, model predictive control, quadratic programming]
---

## Problem

A quadrotor is strongly nonlinear, which makes fast, constrained control difficult.
The **Koopman** approach sidesteps this: it "lifts" the state into a higher-dimensional set
of observables where the dynamics are approximately _linear_, so a standard linear model
predictive controller (MPC) can be used.

In this project I reproduced and analysed a published Koopman-EDMD learning-and-control
pipeline for a quadrotor, working directly in MATLAB.

## Method

1. **Data.** A nonlinear rigid-body simulator serves as the "true" plant and generates
   state–input snapshot pairs.
2. **Lifting.** Attitude is represented with **rotation matrices** instead of Euler angles,
   avoiding singularities; physics-inspired basis functions are built on top of that state.
3. **EDMD with control.** A least-squares regression identifies the matrices of a discrete,
   lifted linear predictor.
4. **MPC.** At every time step, a quadratic program over a 15-step horizon computes thrust
   and body moments that track a smooth sinusoidal 3-D reference, subject to input bounds.

## Results

The learned predictor matched the nonlinear simulator closely over short horizons — which
is what matters inside a controller that replans every step — and the MPC tracked the 3-D
reference with bounded, smooth thrust and moment commands.

<div class="row mt-3">
  <div class="col-sm-4 mt-3 mt-md-0">
    <img src="/assets/img/projects/koopman-edmd.png" alt="EDMD training data and prediction" class="img-fluid rounded z-depth-1" />
  </div>
  <div class="col-sm-8 mt-3 mt-md-0">
    <img src="/assets/img/projects/koopman-3d.png" alt="3-D trajectory tracking" class="img-fluid rounded z-depth-1" />
  </div>
</div>
<div class="caption">EDMD training data and short-horizon prediction (left); 3-D tracking of the reference trajectory (right).</div>

<div class="row justify-content-sm-center mt-3">
  <div class="col-sm-12">
    <img src="/assets/img/projects/koopman-states.png" alt="Closed-loop state histories" class="img-fluid rounded z-depth-1" />
  </div>
</div>
<div class="caption">Closed-loop states: reference (solid) versus MPC response (dashed).</div>

<div class="row justify-content-sm-center mt-3">
  <div class="col-sm-9">
    <img src="/assets/img/projects/koopman-inputs.png" alt="MPC control inputs" class="img-fluid rounded z-depth-1" />
  </div>
</div>
<div class="caption">Thrust and body-moment commands computed by the QP at each step.</div>

<table class="key-facts">
  <tr><th>Time step</th><td>2 ms</td></tr>
  <tr><th>Prediction horizon</th><td>15 steps</td></tr>
  <tr><th>Simulated duration</th><td>1.5 s</td></tr>
  <tr><th>Solver</th><td>MATLAB <code>quadprog</code></td></tr>
</table>

## Takeaways

Rotation-matrix states and attitude-aware observables keep the model globally consistent
while still allowing linear prediction and an efficient QP. Natural next steps are testing
robustness under disturbances and more aggressive references outside the training region.
