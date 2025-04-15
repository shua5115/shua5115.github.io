---
layout: post
title: Powertrain Simulation - Terps Racing Baja
tags: TerpsRacing UMD
splash: /assets/CVT%20shift%20ratio.jpg
---

*August-December 2024*

![](/assets/CVT%20shift%20ratio.jpg)

*CVT Ratio vs. Speed and Torque*

[Github Repository](https://github.com/shua5115/Terps-Racing-Baja-Simulator)

[Project Presentation](/assets/CVT%20Simulation%20-%20CDR.pdf)

![](/assets/CVT%20Sim%20Comparison.png)

*CVT Sim compared to Measurement*

To improve the powertrain performance for Terps Racing Baja's custom ATV, I modeled the powertrain to optimize certain variables,
such as gear ratios and CVT configuration. I created free body diagrams to model the forces within the Continuously Variable Transmission (CVT) with support from published CVT research. For maximum computational performance, I programmed a simulator from scratch in C++. I used test-driven development to ensure that simulation components were behaving correctly.

I took two classes which made this project possible: Design Optimization and Numerical Methods.
Design optimization taught me how to use algorithms to optimize variables with an objective function. I applied the bisection and gradient descent algorithms heavily in this project.
Numerical methods taught useful algorithms for numerical approximation. I applied the Newton and Runge-Kutta numerical integration algorithms.


### Acceleration Optimization Results

A multithreaded program tests all available CVT configurations, brute forcing optimal results in a few minutes.
The worst result is shown to identify which variables are most significant.
```yaml
Worst result:
k_p: 45.000000 lbf/in
m_fly: 280.000000 g
k_s: 22.750000 lbf/in
helix: 28.000000 deg
pretension: 4.000000
accel time: 12.285000 s

Best result:
k_p: 45.000000 lbf/in
m_fly: 364.000000 g
k_s: 14.650000 lbf/in
helix: 28.000000 deg
pretension: 4.000000
accel time: 5.302000 s
```


### Basic Usage of Simulator

Prints CSV table of position, velocity, engine RPM, and CVT ratio over time.

```c++
#include <iostream>
#include "trb.hpp"

int main() {
    BajaState baja = TR24_GAGED_GX9;
    // Set initial condition and cvt tune
    baja.controls.throttle = 1; // this one is required for the car to move forward

    double dt = 1e-4; // simulation timestep
    
    double t = 0;
    // CSV header
    printf("t,x,v,omega_p,ratio\n");
    // while(t < 10) { // time condition
    while(baja.x < 150*FT2M) { // distance condition
        double ratio = baja.r_s/baja.r_p;
        // CSV row
        printf("%f,%f,%f,%f,%f\n",
            t, baja.x, baja.v, baja.omega_p, ratio
        );
        // Step simulation
        trb_sim_step(baja, dt);
        t += dt;
    }
}
```