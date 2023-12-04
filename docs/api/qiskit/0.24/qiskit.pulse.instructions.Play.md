<span id="qiskit-pulse-instructions-play" />

# qiskit.pulse.instructions.Play

<span id="undefined" />

`Play(pulse, channel, name=None)`

This instruction is responsible for applying a pulse on a channel.

The pulse specifies the exact time dynamics of the output signal envelope for a limited time. The output is modulated by a phase and frequency which are controlled by separate instructions. The pulse duration must be fixed, and is implicitly given in terms of the cycle time, dt, of the backend.

Create a new pulse instruction.

**Parameters**

*   **pulse** (`Pulse`) – A pulse waveform description, such as [`Waveform`](qiskit.pulse.library.Waveform#qiskit.pulse.library.Waveform "qiskit.pulse.library.Waveform").
*   **channel** ([`PulseChannel`](qiskit.pulse.channels#PulseChannel "qiskit.pulse.channels.PulseChannel")) – The channel to which the pulse is applied.
*   **name** (`Optional`\[`str`]) – Name of the instruction for display purposes. Defaults to `pulse.name`.

**Raises**

[**PulseError**](qiskit.pulse.PulseError#qiskit.pulse.PulseError "qiskit.pulse.PulseError") – If pulse is not a Pulse type.

<span id="undefined" />

`__init__(pulse, channel, name=None)`

Create a new pulse instruction.

**Parameters**

*   **pulse** (`Pulse`) – A pulse waveform description, such as [`Waveform`](qiskit.pulse.library.Waveform#qiskit.pulse.library.Waveform "qiskit.pulse.library.Waveform").
*   **channel** ([`PulseChannel`](qiskit.pulse.channels#PulseChannel "qiskit.pulse.channels.PulseChannel")) – The channel to which the pulse is applied.
*   **name** (`Optional`\[`str`]) – Name of the instruction for display purposes. Defaults to `pulse.name`.

**Raises**

[**PulseError**](qiskit.pulse.PulseError#qiskit.pulse.PulseError "qiskit.pulse.PulseError") – If pulse is not a Pulse type.

## Methods

|                                                                                                                                          |                                                                                                                                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [`__init__`](#qiskit.pulse.instructions.Play.__init__ "qiskit.pulse.instructions.Play.__init__")(pulse, channel\[, name])                | Create a new pulse instruction.                                                                                                                                                                     |
| [`append`](#qiskit.pulse.instructions.Play.append "qiskit.pulse.instructions.Play.append")(schedule\[, name])                            | Return a new [`Schedule`](qiskit.pulse.Schedule#qiskit.pulse.Schedule "qiskit.pulse.Schedule") with `schedule` inserted at the maximum time over all channels shared between `self` and `schedule`. |
| [`assign_parameters`](#qiskit.pulse.instructions.Play.assign_parameters "qiskit.pulse.instructions.Play.assign_parameters")(value\_dict) | Modify and return self with parameters assigned according to the input.                                                                                                                             |
| [`ch_duration`](#qiskit.pulse.instructions.Play.ch_duration "qiskit.pulse.instructions.Play.ch_duration")(\*channels)                    | Return duration of the supplied channels in this Instruction.                                                                                                                                       |
| [`ch_start_time`](#qiskit.pulse.instructions.Play.ch_start_time "qiskit.pulse.instructions.Play.ch_start_time")(\*channels)              | Return minimum start time for supplied channels.                                                                                                                                                    |
| [`ch_stop_time`](#qiskit.pulse.instructions.Play.ch_stop_time "qiskit.pulse.instructions.Play.ch_stop_time")(\*channels)                 | Return maximum start time for supplied channels.                                                                                                                                                    |
| [`draw`](#qiskit.pulse.instructions.Play.draw "qiskit.pulse.instructions.Play.draw")(\[dt, style, filename, interp\_method, …])          | Plot the instruction.                                                                                                                                                                               |
| [`flatten`](#qiskit.pulse.instructions.Play.flatten "qiskit.pulse.instructions.Play.flatten")()                                          | Return itself as already single instruction.                                                                                                                                                        |
| [`insert`](#qiskit.pulse.instructions.Play.insert "qiskit.pulse.instructions.Play.insert")(start\_time, schedule\[, name])               | Return a new [`Schedule`](qiskit.pulse.Schedule#qiskit.pulse.Schedule "qiskit.pulse.Schedule") with `schedule` inserted within `self` at `start_time`.                                              |
| [`shift`](#qiskit.pulse.instructions.Play.shift "qiskit.pulse.instructions.Play.shift")(time\[, name])                                   | Return a new schedule shifted forward by time.                                                                                                                                                      |

## Attributes

|                                                                                                              |                                                                                                                              |
| ------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------- |
| [`channel`](#qiskit.pulse.instructions.Play.channel "qiskit.pulse.instructions.Play.channel")                | Return the [`Channel`](qiskit.pulse.channels#Channel "qiskit.pulse.channels.Channel") that this instruction is scheduled on. |
| [`channels`](#qiskit.pulse.instructions.Play.channels "qiskit.pulse.instructions.Play.channels")             | Returns channels that this schedule uses.                                                                                    |
| [`command`](#qiskit.pulse.instructions.Play.command "qiskit.pulse.instructions.Play.command")                | The associated command.                                                                                                      |
| [`duration`](#qiskit.pulse.instructions.Play.duration "qiskit.pulse.instructions.Play.duration")             | Duration of this instruction.                                                                                                |
| [`id`](#qiskit.pulse.instructions.Play.id "qiskit.pulse.instructions.Play.id")                               | Unique identifier for this instruction.                                                                                      |
| [`instructions`](#qiskit.pulse.instructions.Play.instructions "qiskit.pulse.instructions.Play.instructions") | Iterable for getting instructions from Schedule tree.                                                                        |
| [`name`](#qiskit.pulse.instructions.Play.name "qiskit.pulse.instructions.Play.name")                         | Name of this instruction.                                                                                                    |
| [`operands`](#qiskit.pulse.instructions.Play.operands "qiskit.pulse.instructions.Play.operands")             | Return instruction operands.                                                                                                 |
| [`pulse`](#qiskit.pulse.instructions.Play.pulse "qiskit.pulse.instructions.Play.pulse")                      | A description of the samples that will be played.                                                                            |
| [`start_time`](#qiskit.pulse.instructions.Play.start_time "qiskit.pulse.instructions.Play.start_time")       | Relative begin time of this instruction.                                                                                     |
| [`stop_time`](#qiskit.pulse.instructions.Play.stop_time "qiskit.pulse.instructions.Play.stop_time")          | Relative end time of this instruction.                                                                                       |
| [`timeslots`](#qiskit.pulse.instructions.Play.timeslots "qiskit.pulse.instructions.Play.timeslots")          | Occupied time slots by this instruction.                                                                                     |

<span id="undefined" />

`append(schedule, name=None)`

Return a new [`Schedule`](qiskit.pulse.Schedule#qiskit.pulse.Schedule "qiskit.pulse.Schedule") with `schedule` inserted at the maximum time over all channels shared between `self` and `schedule`.

**Parameters**

*   **schedule** (`ScheduleComponent`) – schedule to be appended
*   **name** (`Optional`\[`str`]) – Name of the new schedule. Defaults to name of self

**Return type**

`Schedule`

<span id="undefined" />

`assign_parameters(value_dict)`

Modify and return self with parameters assigned according to the input.

**Parameters**

**value\_dict** (`Dict`\[`ParameterExpression`, `Union`\[`ParameterExpression`, `float`, `int`]]) – A mapping from Parameters to either numeric values or another Parameter expression.

**Return type**

`Play`

**Returns**

Self with updated parameters.

<span id="undefined" />

`ch_duration(*channels)`

Return duration of the supplied channels in this Instruction.

**Parameters**

**\*channels** – Supplied channels

**Return type**

`int`

<span id="undefined" />

`ch_start_time(*channels)`

Return minimum start time for supplied channels.

**Parameters**

**\*channels** – Supplied channels

**Return type**

`int`

<span id="undefined" />

`ch_stop_time(*channels)`

Return maximum start time for supplied channels.

**Parameters**

**\*channels** – Supplied channels

**Return type**

`int`

<span id="undefined" />

`property channel`

Return the [`Channel`](qiskit.pulse.channels#Channel "qiskit.pulse.channels.Channel") that this instruction is scheduled on.

**Return type**

[`PulseChannel`](qiskit.pulse.channels#PulseChannel "qiskit.pulse.channels.PulseChannel")

<span id="undefined" />

`property channels`

Returns channels that this schedule uses.

**Return type**

`Tuple`\[[`Channel`](qiskit.pulse.channels#Channel "qiskit.pulse.channels.Channel")]

<span id="undefined" />

`property command`

The associated command. Commands are deprecated, so this method will be deprecated shortly.

**Returns**

The deprecated command if available.

**Return type**

[Command](qiskit.providers.models.Command#qiskit.providers.models.Command "qiskit.providers.models.Command")

<span id="undefined" />

`draw(dt=1, style=None, filename=None, interp_method=None, scale=1, plot_all=False, plot_range=None, interactive=False, table=True, label=False, framechange=True, channels=None)`

Plot the instruction.

**Parameters**

*   **dt** (`float`) – Time interval of samples
*   **style** (*Optional\[*[*SchedStyle*](qiskit.visualization.pulse.qcstyle#SchedStyle "qiskit.visualization.pulse.qcstyle.SchedStyle")*]*) – A style sheet to configure plot appearance
*   **filename** (`Optional`\[`str`]) – Name required to save pulse image
*   **interp\_method** (`Optional`\[`Callable`]) – A function for interpolation
*   **scale** (`float`) – Relative visual scaling of waveform amplitudes
*   **plot\_all** (`bool`) – Plot empty channels
*   **plot\_range** (`Optional`\[`Tuple`\[`float`]]) – A tuple of time range to plot
*   **interactive** (`bool`) – When set true show the circuit in a new window (this depends on the matplotlib backend being used supporting this)
*   **table** (`bool`) – Draw event table for supported instructions
*   **label** (`bool`) – Label individual instructions
*   **framechange** (`bool`) – Add framechange indicators
*   **channels** (`Optional`\[`List`\[[`Channel`](qiskit.pulse.channels#Channel "qiskit.pulse.channels.Channel")]]) – A list of channel names to plot

**Returns**

A matplotlib figure object of the pulse schedule

**Return type**

matplotlib.figure

<span id="undefined" />

`property duration`

Duration of this instruction.

**Return type**

`int`

<span id="undefined" />

`flatten()`

Return itself as already single instruction.

**Return type**

`Instruction`

<span id="undefined" />

`property id`

Unique identifier for this instruction.

**Return type**

`int`

<span id="undefined" />

`insert(start_time, schedule, name=None)`

Return a new [`Schedule`](qiskit.pulse.Schedule#qiskit.pulse.Schedule "qiskit.pulse.Schedule") with `schedule` inserted within `self` at `start_time`.

**Parameters**

*   **start\_time** (`int`) – Time to insert the schedule schedule
*   **schedule** (`ScheduleComponent`) – Schedule to insert
*   **name** (`Optional`\[`str`]) – Name of the new schedule. Defaults to name of self

**Return type**

`Schedule`

<span id="undefined" />

`property instructions`

Iterable for getting instructions from Schedule tree.

**Return type**

`Tuple`\[`Tuple`\[`int`, `Instruction`]]

<span id="undefined" />

`property name`

Name of this instruction.

**Return type**

`str`

<span id="undefined" />

`property operands`

Return instruction operands.

**Return type**

`Tuple`

<span id="undefined" />

`property pulse`

A description of the samples that will be played.

**Return type**

`Pulse`

<span id="undefined" />

`shift(time, name=None)`

Return a new schedule shifted forward by time.

**Parameters**

*   **time** (`int`) – Time to shift by
*   **name** (`Optional`\[`str`]) – Name of the new schedule. Defaults to name of self

**Return type**

`Schedule`

<span id="undefined" />

`property start_time`

Relative begin time of this instruction.

**Return type**

`int`

<span id="undefined" />

`property stop_time`

Relative end time of this instruction.

**Return type**

`int`

<span id="undefined" />

`property timeslots`

Occupied time slots by this instruction.

**Return type**

`Dict`\[[`Channel`](qiskit.pulse.channels#Channel "qiskit.pulse.channels.Channel"), `List`\[`Tuple`\[`int`, `int`]]]