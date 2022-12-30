---
layout: page
title: vfcfisher
description: fisher matrix - fundamental constants and dark energy
img: /assets/img/vfcfisherIcon.png
importance: 4
category: work
---

As described in the [research](./projects/research/) explanation, one of the most promising developments for future data in cosmology is the _cosmological recombination radiation_. This distortion signal will give us another perspective on the physical cosmology within the wider Universe, even before the last scattering surface leading to the CMB anisotropies.

However, many non-standard physical scenarios are sensitive to these variations such as changes to the fundamental electromagnetism constants and also dark energy models such as _early dark energy_. This project was designed to try and probe both of these effects and even motivates a wider study into how one may be affected by the other.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/pdf/vfcFisherGenerator.pdf' | relative_url }}" alt="" title="Flowchart for the vfcFisher code"/>
    </div>
</div>
<div class="caption">
    Flowchart detailing the structure of the lite Python API called <em>vfcFisher</em> used for calculating VFC and EDE parameter forecasts.
</div>

As shown in the flowchart, `vfcFisher` generates the spectra Python objects from `CosmoSpec`, feeds them into the Fisher code with a noise spectra included and then passes these objects to a separate pocket of routines called `vfcPlot`.

### Implementation
`vfcFisher` is the small Python package designed to integrate with realistic spectral distortion results and apply the code from `GetDist` to generate simulated probability contours for given models. This module has also utilised elements of the early dark energy equivalent to create the forecasts for the early dark energy amplitude as well.

Everything that is given by [CosmoSpec](https://chluba.de/CosmoSpec) can be built into a series of classes: `Spectrum` holds the CRR information that is parsed into a unique object, derivative of that is `NegSpectrum`. `Parameter` contains the information required to specifically define all the information relevant for that. The spectrometer noise spectra is built into a `NoiseModel` class that can be configured for any mission you want to target. Finally all this information is pulled into a `Fisher` object which calculates the covariances, detailed Fisher information and then does all the necessary matrix operations to calculate the effective errors.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/pdf/vfEde.pdf' | relative_url }}" alt="" title="Predictive contours for early dark energy Fisher"/>
    </div>
</div>
<div class="caption">
   Preliminary likelihood contours using the CRR as a tracer for the early dark energy parameters. They have been tested for all models under the ULA approximation, but here we show \(\left(n,z_c\right) = (2,3000), (2,2000), (2,1500)\) models since they are shown to be very constrainable.
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/pdf/vfAlpha.pdf' | relative_url }}" alt="" title="Predictive contours for fine structure constant Fisher"/>
    </div>
</div>
<div class="caption">
    Likelihood contours for the key degeneracy in the fine structure constant addition to the \(\Lambda{\rm CDM}\) cosmology: the sound horizon. Here the variations for Planck and the original Voyage 2050 specification are shown to be consistent; but the higher resolution spectrometer gives a much tighter contour as the degeneracy in the CMB is broken by the addition of the recombination lines.
</div>
