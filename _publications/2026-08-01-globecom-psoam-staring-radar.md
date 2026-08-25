---
title: "Exploring Two-Dimensional Staring Radar Imaging Using Novel OAM Beams without Energy Void"
collection: publications
permalink: /publication/2026-globecom-psoam-staring-radar
excerpt: 'Transmit-side azimuth discrimination for compact staring radar using the equivalent-order diversity of plane-spiral OAM illuminations — angular resolution in a single-receive-channel FMCW architecture, validated in simulation and on a stepped-frequency X-band testbed.'
date: 2026-08-01
venue: 'IEEE Global Communications Conference (GLOBECOM) Workshops — Workshop on Communications, Sensing, and Computing for Sustainable IoT Connectivity: Architecture, Implementation, and Applications'
citation: 'K. Cai, Y. Zhao, E. Shi, D. Lin, and Y. L. Guan, "Exploring Two-Dimensional Staring Radar Imaging Using Novel OAM Beams without Energy Void," in <i>Proc. IEEE GLOBECOM Workshops</i>, 2026. (Under review.)'
---

**First author.** Under review.

## The problem

A compact staring radar with a single receive channel cannot separate two targets that occupy the same range–Doppler cell — think two vehicles side by side, or two pedestrians walking abreast. Wideband FMCW processing resolves range and slow time resolves Doppler, but neither separates targets that differ only in azimuth. Azimuth normally comes from spatial sampling across a receive array, and for the physically large X-band radiators involved here, a densely sampled receive array is impractical.

## The approach

Instead of adding receive channels, code the **transmit** side. Four plane-spiral OAM (PS-OAM) radiators, each with a distinct measured azimuthal phase slope, illuminate the scene sequentially; their *equivalent-order diversity* provides an angular sensing manifold that is matched during spherical-wave backprojection.

The point-target response factorizes into a common physical channel and a mode-domain factor, and the angular-discrimination scale follows the span of the equivalent orders. For the measured set *l*<sub>e</sub> = {23, 30, 35, 45} — span *L* = 22 — the characteristic scale is 2π/*L* ≈ 16°.

## Results

In simulation (10 GHz carrier, 1 GHz bandwidth, two coherent targets at 15 m), the method resolves the pair from **≈15°** separation in phase, and from **≈19°** across all 360 sampled relative scattering phases. A magnitude-matched conventional baseline — same amplitude envelope, differing *only* in azimuthal phase slope — attains no valid separability limit anywhere in the 3°–40° sweep, which attributes the gain to the mode-domain coding rather than to beamwidth or taper.

![Simulation: conventional versus PS-OAM backprojection](/images/psoam-simulation.png)
*Same-range two-target imaging under the matched MT-1R geometry; both targets at 15 m, 18° apart. (a) Repeated conventional spherical-wave BP — one merged lobe. (b) PS-OAM equivalent-order BP — two resolved peaks. (c) Azimuth cuts at 15 m, with the 26% dip threshold marked.*

A stepped-frequency VNA measurement at ≈8 m (9.5–10.5 GHz, 801 points) makes the same comparison in hardware: the conventional transmit antenna produces one broad azimuth lobe of ≈34.9° power FWHM, whereas the four PS-OAM radiators produce **two distinct image peaks separated by ≈28.6°**, with an inter-peak dip metric of **η = 0.936**.

![Measured comparison at 8 m](/images/psoam-measurement.png)
*Measured comparison for the nominal 8-m two-target scene, same range gate, azimuth sector, and dynamic range throughout. (a) Conventional transmit antenna. (b) The four measured PS-OAM orders. (c) Azimuth cuts through the peak-range rows: the conventional response stays one broad lobe, the PS-OAM response is bimodal at −15.4° and +13.2° with η = 0.936. The azimuth axis is model-based and not yet absolutely calibrated.*

## What it does not claim

Equivalent-order diversity creates no aperture-independent angular degrees of freedom — higher phase slopes still require correspondingly larger mode-generating apertures. The benefit is architectural: fixed antennas, no mechanical scanning, and an angular response controlled by transmit mode content rather than by receive-element count.
