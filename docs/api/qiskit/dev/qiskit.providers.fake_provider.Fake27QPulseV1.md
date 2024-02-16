---
title: Fake27QPulseV1
description: API reference for qiskit.providers.fake_provider.Fake27QPulseV1
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.providers.fake_provider.Fake27QPulseV1
---

# Fake27QPulseV1

<span id="qiskit.providers.fake_provider.Fake27QPulseV1" />

`qiskit.providers.fake_provider.Fake27QPulseV1`[GitHub](https://github.com/qiskit/qiskit/tree/main/qiskit/providers/fake_provider/backends_v1/fake_27q_pulse/fake_27q_pulse_v1.py "view source code")

Bases: [`FakePulseBackend`](providers_fake_provider#qiskit.providers.fake_provider.FakePulseBackend "qiskit.providers.fake_provider.fake_pulse_backend.FakePulseBackend")

A fake **pulse** backend with the following characteristics:

*   num\_qubits: 27

*   coupling\_map:

    > ```python
    >                06                  17
    >                ↕                    ↕
    > 00 ↔ 01 ↔ 04 ↔ 07 ↔ 10 ↔ 12 ↔ 15 ↔ 18 ↔ 20 ↔ 23
    >      ↕                   ↕                    ↕
    >      02                  13                  24
    >      ↕                   ↕                    ↕
    >      03 ↔ 05 ↔ 08 ↔ 11 ↔ 14 ↔ 16 ↔ 19 ↔ 22 ↔ 25 ↔ 26
    >                ↕                    ↕
    >                09                  20
    > ```

*   basis\_gates: `["id", "rz", "sx", "x", "cx", "reset"]`

*   **scheduled instructions:**

    \# `{'id', 'rz', 'u2', 'x', 'u3', 'sx', 'measure', 'u1'}` for all individual qubits # `{'cx'}` for all edges # `{'measure'}` for (0, …, 26)

FakeBackend initializer.

**Parameters**

*   **configuration** ([*BackendConfiguration*](qiskit.providers.models.BackendConfiguration "qiskit.providers.models.BackendConfiguration")) – backend configuration
*   **time\_alive** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")) – time to wait before returning result

## Attributes

<span id="qiskit.providers.fake_provider.Fake27QPulseV1.backend_name" />

### backend\_name

`= 'fake_27q_pulse_v1'`

<span id="qiskit.providers.fake_provider.Fake27QPulseV1.conf_filename" />

### conf\_filename

`= 'conf_hanoi.json'`

<span id="qiskit.providers.fake_provider.Fake27QPulseV1.defs_filename" />

### defs\_filename

`= 'defs_hanoi.json'`

<span id="qiskit.providers.fake_provider.Fake27QPulseV1.dirname" />

### dirname

`= '/home/runner/work/qiskit/qiskit/.tox/docs/lib/python3.9/site-packages/qiskit/providers/fake_provider/backends_v1/fake_27q_pulse'`

<span id="qiskit.providers.fake_provider.Fake27QPulseV1.options" />

### options

Return the options for the backend

The options of a backend are the dynamic parameters defining how the backend is used. These are used to control the [`run()`](#qiskit.providers.fake_provider.Fake27QPulseV1.run "qiskit.providers.fake_provider.Fake27QPulseV1.run") method.

<span id="qiskit.providers.fake_provider.Fake27QPulseV1.props_filename" />

### props\_filename

`= 'props_hanoi.json'`

<span id="qiskit.providers.fake_provider.Fake27QPulseV1.version" />

### version

`= 1`

## Methods

### configuration

<span id="qiskit.providers.fake_provider.Fake27QPulseV1.configuration" />

`configuration()`

Return the backend configuration.

**Returns**

the configuration for the backend.

**Return type**

[BackendConfiguration](qiskit.providers.models.BackendConfiguration "qiskit.providers.models.BackendConfiguration")

### defaults

<span id="qiskit.providers.fake_provider.Fake27QPulseV1.defaults" />

`defaults()`

Returns a snapshot of device defaults

### name

<span id="qiskit.providers.fake_provider.Fake27QPulseV1.name" />

`name()`

Return the backend name.

**Returns**

the name of the backend.

**Return type**

[str](https://docs.python.org/3/library/stdtypes.html#str "(in Python v3.12)")

### properties

<span id="qiskit.providers.fake_provider.Fake27QPulseV1.properties" />

`properties()`

Returns a snapshot of device properties

### provider

<span id="qiskit.providers.fake_provider.Fake27QPulseV1.provider" />

`provider()`

Return the backend Provider.

**Returns**

the Provider responsible for the backend.

**Return type**

[Provider](qiskit.providers.Provider "qiskit.providers.Provider")

### run

<span id="qiskit.providers.fake_provider.Fake27QPulseV1.run" />

`run(run_input, **kwargs)`

Main job in simulator

### set\_options

<span id="qiskit.providers.fake_provider.Fake27QPulseV1.set_options" />

`set_options(**fields)`

Set the options fields for the backend

This method is used to update the options of a backend. If you need to change any of the options prior to running just pass in the kwarg with the new value for the options.

**Parameters**

**fields** – The fields to update the options

**Raises**

[**AttributeError**](https://docs.python.org/3/library/exceptions.html#AttributeError "(in Python v3.12)") – If the field passed in is not part of the options

### status

<span id="qiskit.providers.fake_provider.Fake27QPulseV1.status" />

`status()`

Return the backend status.

**Returns**

the status of the backend.

**Return type**

[BackendStatus](qiskit.providers.models.BackendStatus "qiskit.providers.models.BackendStatus")
