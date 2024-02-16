---
title: UMDA
description: API reference for qiskit.algorithms.optimizers.UMDA
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.algorithms.optimizers.UMDA
---

# UMDA

<span id="qiskit.algorithms.optimizers.UMDA" />

`qiskit.algorithms.optimizers.UMDA(maxiter=100, size_gen=20, alpha=0.5, callback=None)`[GitHub](https://github.com/qiskit/qiskit/tree/stable/0.46/qiskit/algorithms/optimizers/umda.py "view source code")

Bases: [`Optimizer`](qiskit.algorithms.optimizers.Optimizer "qiskit.algorithms.optimizers.optimizer.Optimizer")

Continuous Univariate Marginal Distribution Algorithm (UMDA).

UMDA \[1] is a specific type of Estimation of Distribution Algorithm (EDA) where new individuals are sampled from univariate normal distributions and are updated in each iteration of the algorithm by the best individuals found in the previous iteration.

<Admonition title="See also" type="note">
  This original implementation of the UDMA optimizer for Qiskit was inspired by my (Vicente P. Soloviev) work on the EDAspy Python package \[2].
</Admonition>

EDAs are stochastic search algorithms and belong to the family of the evolutionary algorithms. The main difference is that EDAs have a probabilistic model which is updated in each iteration from the best individuals of previous generations (elite selection). Depending on the complexity of the probabilistic model, EDAs can be classified in different ways. In this case, UMDA is a univariate EDA as the embedded probabilistic model is univariate.

UMDA has been compared to some of the already implemented algorithms in Qiskit library to optimize the parameters of variational algorithms such as QAOA or VQE and competitive results have been obtained \[1]. UMDA seems to provide very good solutions for those circuits in which the number of layers is not big.

The optimization process can be personalized depending on the parameters chosen in the initialization. The main parameter is the population size. The bigger it is, the final result will be better. However, this increases the complexity of the algorithm and the runtime will be much heavier. In the work \[1] different experiments have been performed where population size has been set to 20 - 30.

<Admonition title="Note" type="note">
  The UMDA implementation has more parameters but these have default values for the initialization for better understanding of the user. For example, `lpha` parameter has been set to 0.5 and is the percentage of the population which is selected in each iteration to update the probabilistic model.
</Admonition>

**Example**

This short example runs UMDA to optimize the parameters of a variational algorithm. Here we will use the same operator as used in the algorithms introduction, which was originally computed by Qiskit Nature for an H2 molecule. The minimum energy of the H2 Hamiltonian can be found quite easily so we are able to set maxiters to a small value.

```python
from qiskit.opflow import X, Z, I
from qiskit_aer import Aer
from qiskit.algorithms.optimizers import UMDA
from qiskit.algorithms import QAOA
from qiskit.utils import QuantumInstance


H2_op = (-1.052373245772859 * I ^ I) +             (0.39793742484318045 * I ^ Z) +             (-0.39793742484318045 * Z ^ I) +             (-0.01128010425623538 * Z ^ Z) +             (0.18093119978423156 * X ^ X)

p = 2  # Toy example: 2 layers with 2 parameters in each layer: 4 variables

opt = UMDA(maxiter=100, size_gen=20)

backend = Aer.get_backend('statevector_simulator')
vqe = QAOA(opt,
           quantum_instance=QuantumInstance(backend=backend),
           reps=p)

result = vqe.compute_minimum_eigenvalue(operator=H2_op)
```

If it is desired to modify the percentage of individuals considered to update the probabilistic model, then this code can be used. Here for example we set the 60% instead of the 50% predefined.

```python
opt = UMDA(maxiter=100, size_gen=20, alpha = 0.6)

backend = Aer.get_backend('statevector_simulator')
vqe = QAOA(opt,
           quantum_instance=QuantumInstance(backend=backend),
           reps=p)

result = vqe.compute_minimum_eigenvalue(operator=qubit_op)
```

**References**

\[1]: Vicente P. Soloviev, Pedro Larrañaga and Concha Bielza (2022, July). Quantum Parametric Circuit Optimization with Estimation of Distribution Algorithms. In 2022 The Genetic and Evolutionary Computation Conference (GECCO). DOI: [https://doi.org/10.1145/3520304.3533963](https://doi.org/10.1145/3520304.3533963)

\[2]: Vicente P. Soloviev. Python package EDAspy. [https://github.com/VicentePerezSoloviev/EDAspy](https://github.com/VicentePerezSoloviev/EDAspy).

**Parameters**

*   **maxiter** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")) – Maximum number of iterations.
*   **size\_gen** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")) – Population size of each generation.
*   **alpha** ([*float*](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)")) – Percentage (0, 1] of the population to be selected as elite selection.
*   **callback** (*Callable\[\[*[*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")*, np.array,* [*float*](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)")*], None] | None*) – A callback function passed information in each iteration step. The information is, in this order: the number of function evaluations, the parameters, the best function value in this iteration.

## Attributes

<span id="qiskit.algorithms.optimizers.UMDA.ELITE_FACTOR" />

### ELITE\_FACTOR

`= 0.4`

<span id="qiskit.algorithms.optimizers.UMDA.STD_BOUND" />

### STD\_BOUND

`= 0.3`

<span id="qiskit.algorithms.optimizers.UMDA.alpha" />

### alpha

Returns the alpha parameter value (percentage of population selected to update probabilistic model)

<span id="qiskit.algorithms.optimizers.UMDA.bounds_support_level" />

### bounds\_support\_level

Returns bounds support level

<span id="qiskit.algorithms.optimizers.UMDA.gradient_support_level" />

### gradient\_support\_level

Returns gradient support level

<span id="qiskit.algorithms.optimizers.UMDA.initial_point_support_level" />

### initial\_point\_support\_level

Returns initial point support level

<span id="qiskit.algorithms.optimizers.UMDA.is_bounds_ignored" />

### is\_bounds\_ignored

Returns is bounds ignored

<span id="qiskit.algorithms.optimizers.UMDA.is_bounds_required" />

### is\_bounds\_required

Returns is bounds required

<span id="qiskit.algorithms.optimizers.UMDA.is_bounds_supported" />

### is\_bounds\_supported

Returns is bounds supported

<span id="qiskit.algorithms.optimizers.UMDA.is_gradient_ignored" />

### is\_gradient\_ignored

Returns is gradient ignored

<span id="qiskit.algorithms.optimizers.UMDA.is_gradient_required" />

### is\_gradient\_required

Returns is gradient required

<span id="qiskit.algorithms.optimizers.UMDA.is_gradient_supported" />

### is\_gradient\_supported

Returns is gradient supported

<span id="qiskit.algorithms.optimizers.UMDA.is_initial_point_ignored" />

### is\_initial\_point\_ignored

Returns is initial point ignored

<span id="qiskit.algorithms.optimizers.UMDA.is_initial_point_required" />

### is\_initial\_point\_required

Returns is initial point required

<span id="qiskit.algorithms.optimizers.UMDA.is_initial_point_supported" />

### is\_initial\_point\_supported

Returns is initial point supported

<span id="qiskit.algorithms.optimizers.UMDA.maxiter" />

### maxiter

Returns the maximum number of iterations

<span id="qiskit.algorithms.optimizers.UMDA.setting" />

### setting

Return setting

<span id="qiskit.algorithms.optimizers.UMDA.settings" />

### settings

<span id="qiskit.algorithms.optimizers.UMDA.size_gen" />

### size\_gen

Returns the size of the generations (number of individuals per generation)

## Methods

### get\_support\_level

<span id="qiskit.algorithms.optimizers.UMDA.get_support_level" />

`get_support_level()`

Get the support level dictionary.

### gradient\_num\_diff

<span id="qiskit.algorithms.optimizers.UMDA.gradient_num_diff" />

`static gradient_num_diff(x_center, f, epsilon, max_evals_grouped=None)`

We compute the gradient with the numeric differentiation in the parallel way, around the point x\_center.

**Parameters**

*   **x\_center** (*ndarray*) – point around which we compute the gradient
*   **f** (*func*) – the function of which the gradient is to be computed.
*   **epsilon** ([*float*](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)")) – the epsilon used in the numeric differentiation.
*   **max\_evals\_grouped** ([*int*](https://docs.python.org/3/library/functions.html#int "(in Python v3.12)")) – max evals grouped, defaults to 1 (i.e. no batching).

**Returns**

the gradient computed

**Return type**

grad

### minimize

<span id="qiskit.algorithms.optimizers.UMDA.minimize" />

`minimize(fun, x0, jac=None, bounds=None)`

Minimize the scalar function.

**Parameters**

*   **fun** (*Callable\[\[POINT],* [*float*](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)")*]*) – The scalar function to minimize.
*   **x0** (*POINT*) – The initial point for the minimization.
*   **jac** (*Callable\[\[POINT], POINT] | None*) – The gradient of the scalar function `fun`.
*   **bounds** ([*list*](https://docs.python.org/3/library/stdtypes.html#list "(in Python v3.12)")*\[*[*tuple*](https://docs.python.org/3/library/stdtypes.html#tuple "(in Python v3.12)")*\[*[*float*](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)")*,* [*float*](https://docs.python.org/3/library/functions.html#float "(in Python v3.12)")*]] | None*) – Bounds for the variables of `fun`. This argument might be ignored if the optimizer does not support bounds.

**Returns**

The result of the optimization, containing e.g. the result as attribute `x`.

**Return type**

[OptimizerResult](qiskit.algorithms.optimizers.OptimizerResult "qiskit.algorithms.optimizers.OptimizerResult")

### print\_options

<span id="qiskit.algorithms.optimizers.UMDA.print_options" />

`print_options()`

Print algorithm-specific options.

### set\_max\_evals\_grouped

<span id="qiskit.algorithms.optimizers.UMDA.set_max_evals_grouped" />

`set_max_evals_grouped(limit)`

Set max evals grouped

### set\_options

<span id="qiskit.algorithms.optimizers.UMDA.set_options" />

`set_options(**kwargs)`

Sets or updates values in the options dictionary.

The options dictionary may be used internally by a given optimizer to pass additional optional values for the underlying optimizer/optimization function used. The options dictionary may be initially populated with a set of key/values when the given optimizer is constructed.

**Parameters**

**kwargs** ([*dict*](https://docs.python.org/3/library/stdtypes.html#dict "(in Python v3.12)")) – options, given as name=value.

### wrap\_function

<span id="qiskit.algorithms.optimizers.UMDA.wrap_function" />

`static wrap_function(function, args)`

Wrap the function to implicitly inject the args at the call of the function.

**Parameters**

*   **function** (*func*) – the target function
*   **args** ([*tuple*](https://docs.python.org/3/library/stdtypes.html#tuple "(in Python v3.12)")) – the args to be injected

**Returns**

wrapper

**Return type**

function\_wrapper
