---
title: gaussian_deriv
description: API reference for qiskit.pulse.library.gaussian_deriv
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.pulse.library.gaussian_deriv
---

# qiskit.pulse.library.gaussian\_deriv[¶](#qiskit-pulse-library-gaussian-deriv "Permalink to this headline")

<span id="qiskit.pulse.library.gaussian_deriv" />

`gaussian_deriv(duration, amp, sigma, name=None)`

Generates unnormalized gaussian derivative [`Waveform`](qiskit.pulse.library.Waveform "qiskit.pulse.library.Waveform").

For $A=$ `amp` and $\sigma=$ `sigma` applies the midpoint sampling strategy to generate a discrete pulse sampled from the continuous function:

$$
f(x) = A\frac{(x - \mu)}{\sigma^2}\exp\left(\left(\frac{x - \mu}{2\sigma}\right)^2 \right)
$$

i.e. the derivative of the Gaussian function, with center $\mu=$ `duration/2`.

**Parameters**

*   **duration** (`int`) – Duration of pulse. Must be greater than zero.
*   **amp** (`complex`) – Pulse amplitude of corresponding Gaussian at the pulse center (`duration/2`).
*   **sigma** (`float`) – Width (standard deviation) of pulse.
*   **name** (`Optional`\[`str`]) – Name of pulse.

**Return type**

[`Waveform`](qiskit.pulse.library.Waveform "qiskit.pulse.library.waveform.Waveform")
