# Game Analytics Guidelines — CIATEC

## 1. Introduction to Game Analytics

### 1.1 What is Game Analytics

Game Analytics is the systematic use of data produced while a game runs, to understand player behaviour, how the game works, and the effects of player–system interaction.

In experimental games and serious games, Game Analytics has an added function: turning observed gameplay behaviour into data that can answer a research question.

The goal is not to collect as much data as possible. It is to record what is needed to relate what the experiment controlled, what the player did, and what can be calculated from those observations.

In the CIATEC context, that relationship is:

```
Paradigm
   ↓
Construct
   ↓
Experimental variable
   ↓
Game mechanic
   ↓
Behaviour
   ↓
Telemetry
   ↓
Metric
   ↓
Digital biomarker
```

The experimental paradigm should drive the core game mechanic, and telemetry should allow the data to be analyzed afterward.

### 1.2 Game Analytics × Game Telemetry × Game Data Mining

These terms are related but not equivalent.

**Game Telemetry** is the collection and recording of data produced during gameplay — discrete events (a click, a response) or continuous signals (position, movement, orientation).

**Game Analytics** is the analysis of that data to answer questions about player behaviour, system behaviour, or the phenomenon under study.

**Game Data Mining** is the use of computational techniques to find patterns, relations, or structures in large game datasets.

Simplified:

```
Telemetry   → collects the data
Analytics   → interprets the data
Data Mining → finds patterns in the data
```

Telemetry can represent both player behaviour and behaviour produced by the game system itself. For CIATEC's experimental games, this manual focuses on the relationship between telemetry and analysis of participant behaviour.

### 1.3 What Game Analytics is used for

Game Analytics can answer questions such as:

- Did the participant respond correctly?
- How long did the response take?
- Which stimulus was present when the response occurred?
- Which position or trajectory was used?
- How many errors occurred?
- How did behaviour change between experimental conditions?
- Did the participant show more variability in a given condition?
- Can the observed result be recalculated from the recorded data?

What to record should follow from these questions — not from what is technically possible to log. The choice of analysis technique also depends on the goal of the investigation.

### 1.4 What's different about experimental games and serious games

In a commercial game, data is mainly used to understand usage, retention, performance, or player behaviour.

In a CIATEC experimental game, there's an extra layer: the game is also a data-collection instrument. That means preserving the relationship between:

```
What was presented
        ↓
What the participant did
        ↓
What was observed
        ↓
What can be calculated
```

Example, in a reaction paradigm:

```
Controlled:
  stimulus = red circle
  onset time = 10.250 s

Observed:
  response = left button
  response time = 10.682 s

Derived:
  reaction time = 432 ms
```

The 432 ms doesn't need to be stored as primary data — it should be reconstructable from the logged events. This matters especially at CIATEC because the intended architecture separates gameplay execution from evaluation logic: the game receives a configuration, runs the task, and returns raw telemetry; evaluation can happen later in the research system.

### 1.5 Core principle

Record what is necessary to reconstruct and analyze the behaviour relevant to the experimental paradigm. More data does not mean better data. Logging should preserve experimental context, observed behaviour, and the ability to calculate the defined indicators — without turning telemetry into an indiscriminate data dump.

---

## 2. From Game to Data

A game is a system that receives inputs, changes state, and produces observable responses. During execution, both the player and the system itself produce information that can be logged and analyzed.

At CIATEC, the goal of Game Analytics is a traceable relationship between what happens in the game and the phenomenon under investigation.

### 2.1 The game as an observable system

During a session, at least two components matter:

```
Player → Action → Game → State change → System response
```

The system can also produce events independent of any direct player action — a stimulus appearing, a timer reaching a value, an object changing position. Both player-driven and system-driven data can matter for understanding the interaction. At CIATEC, the meaning of a response also depends on the game's state at the moment it occurred.

### 2.2 Player Behaviour

Player Behaviour is the participant's observable behaviour during interaction with the game. It can include:

- actions taken
- sequence of actions
- time between events
- choices made
- correct/incorrect responses
- position and trajectory
- movements
- interruptions or pauses
- interaction patterns

Behaviour should not be confused directly with a cognitive, motor, or clinical construct. For example: the *observed behaviour* is "participant selected option 3"; the *metric* is "time between presentation and response"; the *construct* depends on the experimental paradigm. Scientific interpretation only happens once observed behaviour is related to the paradigm and the corresponding construct.

### 2.3 Game State

Game State is the relevant state of the game at a given moment. It can include:

- current level
- experimental condition
- stimulus presented
- object positions
- game time
- round state
- score
- active objects
- rules or parameters in use

Not every visual element needs to be logged individually — only what's needed to reconstruct the context in which the behaviour occurred. If the experimental question depends on where a stimulus was presented, that position must be linked to the corresponding trial.

### 2.4 Player Action

Player Action is an action taken by the participant: click, tap, key press, movement, option selection, cursor movement, controller response, body movement.

A single action rarely has enough scientific meaning on its own — its meaning depends on context:

```
Stimulus presented → Action taken → Time of action → Trial outcome
```

A response should be linked to the stimulus, trial, or condition that produced it whenever that's relevant to the paradigm.

### 2.5 Events, signals, and telemetry

Telemetry falls into two main types.

**Events** — discrete occurrences: `SESSION_START`, `TRIAL_START`, `STIMULUS_PRESENTED`, `PLAYER_ACTION`, `SUCCESS`, `FAILURE`, `PAUSE`, `RESTART`, `SESSION_END`. CIATEC's development documentation uses a lifecycle/gameplay sequence similar to: `Start → Action → Success/Failure → Pause → Restart → Finish`.

**Continuous signals** — values observed repeatedly over time: X/Y position, velocity, acceleration, orientation, trajectory, hand position, body position, controller input, gaze. The need for continuous telemetry depends on the phenomenon under study — in spatial analysis, for instance, a trajectory is a sequence of positions tied to time.

### 2.6 Raw data vs. derived data

Raw data are observations recorded during execution (e.g. `timestamp = 10.250s`, `stimulus_position = 3`, `response = 2`, `x = 0.72`, `y = 0.41`). Derived data are calculated from those records afterward (reaction time, distance travelled, average velocity, error, accuracy, variability).

Raw data should be preserved whenever possible, so metrics can be recalculated later. This matters at CIATEC because the architecture expects the game to return raw telemetry and evaluation logic to stay in the research system.

### 2.7 Traceability

Every relevant result should be traceable to the data that produced it:

```
Session → Condition → Level → Trial → Stimulus → Response → Telemetry → Metric
```

This lets you answer: which stimulus was present, which condition was active, what response was made, when it happened, what the outcome was, and which data produced the metric. If a metric can't be traced back to the data that produced it, its reproducibility is compromised.

---

## 3. Conceptual Telemetry Model

Telemetry is the representation of a game session's relevant events and states as data that can be stored, analyzed, and later reinterpreted. At CIATEC, it must preserve the relationship between what was presented to the participant, what the participant did, and what happened during the interaction — not record indiscriminately everything the game does.

### 3.1 Base unit: Session

A Session is one game run tied to one participant. At minimum it should identify: `session_id`, `participant_id`, `game_id`, `game_version`, `start_timestamp`, `end_timestamp`. Other metadata (device, OS, input method, telemetry schema version) may be needed depending on the game. The session is the unit that groups everything produced during one run.

### 3.2 Condition or Preset

Condition is the experimental configuration under which the participant runs a part of the game. In the CIATEC paradigm, the game can receive a structured configuration from the research system (e.g. `stimulus_position`, `stimulus_type`, `stimulus_duration`, `target_size`, `target_distance`, `number_of_options`, `difficulty`); the client executes the mechanic and returns raw telemetry. The condition must be identifiable in the telemetry so observed behaviour can later be linked back to it.

### 3.3 Level

Level is a unit of configuration or progression. It can contain different stimuli, trials, or events depending on the game's structure. Log `level_id` when the distinction between levels matters for analysis. A level is not automatically the same as an experimental condition — one level can run under different conditions, and one condition can apply across different levels.

### 3.4 Trial

Trial is a single experimental attempt inside the game. Not every game needs this unit explicitly — it matters most when the game presents a sequence of stimuli and responses that must be analyzed individually (e.g. `Level → Trial 01, 02, 03, 04`). When the paradigm depends on per-trial measures, each trial needs an identifier linking stimulus, response, events, and time measures.

### 3.5 Stimulus

Stimulus is what's presented to the participant as part of the task — visual, auditory, spatial, textual, motor, or multimodal. Fields typically include `stimulus_type`, `stimulus_id`, `stimulus_position`, `stimulus_onset`, `stimulus_duration`, `stimulus_condition`. Logging the stimulus matters whenever interpreting the response depends on knowing exactly what was presented — recording only `response` and `reaction_time` is not enough if you also need to know which stimulus, under which condition, produced that response.

### 3.6 Response

Response is the participant's observed reaction to the stimulus or situation. Fields: `response_type`, `response_value`, `response_position`, `response_timestamp`, `reaction_time`, `correct`. Preserve the observed value whenever possible — a classification like `correct = true` can be derived later from stimulus + response, and keeping that separation lets you recompute the interpretation if the evaluation rules change.

### 3.7 Event

Event is a discrete occurrence in the game: `session_start`, `level_start`, `stimulus_presented`, `input_received`, `response_registered`, `success`, `failure`, `pause`, `resume`, `restart`, `level_end`, `session_end`. Every event needs at least `event_type`, `timestamp`, `session_id`, and, when applicable, `condition_id`, `level_id`, `trial_id`, `stimulus_id`, or another game-specific identifier. The structure can vary by paradigm; the common requirement is preserving temporal sequence and relations between events.

### 3.8 Continuous Signal

Some phenomena can't be represented well by discrete events alone. When a variable of interest changes continuously, log it as a continuous signal / time series: `position_x`, `position_y`, `position_z`, `velocity`, `acceleration`, `orientation`, `pose_landmarks`, `gaze_position`, `pointer_position`. In motor tasks, for example, the trajectory between two events may be an essential part of the measure — logging only `movement_start` and `movement_end` discards what's needed to compute distance, velocity, acceleration, variability, or trajectory shape. Log `sampling_rate`, `timestamp`, and `value` whenever the sampling rate is relevant.

### 3.9 How the elements relate

```
Session
  ├── Condition / Preset
  │       └── Level
  │              └── Trial
  │                     ├── Stimulus
  │                     ├── Response
  │                     ├── Events
  │                     └── Continuous Signals
  └── Context / Metadata
```

This doesn't force a specific database model — it's a conceptual organization to keep experimental context, presentation, behaviour, and collected data linked.

### 3.10 Controlled, Observed, and Derived

A core distinction for experimental Game Analytics: separate three kinds of information.

- **Controlled** — defined by the experiment: `stimulus_position`, `stimulus_type`, `target_size`, `stimulus_duration`, `condition`.
- **Observed** — actually recorded during interaction: `response_position`, `response_timestamp`, `player_position`, `input_sequence`, `trajectory`.
- **Derived** — calculated afterward from observed data + experimental context: `reaction_time`, `accuracy`, `error_rate`, `distance`, `velocity`, `trajectory_variability`.

```
CONTROLLED → OBSERVED → DERIVED
```

This separation keeps what the experiment manipulated distinct from what the participant produced and from what was calculated afterward. At CIATEC this matters in particular because evaluation can run on the server — separating game execution from evaluation logic lets raw telemetry be preserved and different analysis methods applied later.

---

## 4. What to Record: Event Telemetry

Event Telemetry covers the discrete occurrences that matter during a game run, forming the temporal sequence needed to reconstruct a session and relate gameplay to experimental conditions. The principle is not to log every internal software occurrence — only what has meaning for the experiment, for behaviour analysis, or for reconstructing the session.

### 4.1 Lifecycle events

Lifecycle events mark start, interruption, and end of execution: `session_start`, `session_end`, `level_start`, `level_end`, `pause`, `resume`, `restart`. They establish the session's temporal structure:

```
Session Start → Level Start → Gameplay → Level End → Session End
```

When a session has multiple levels or rounds, preserve those relations.

### 4.2 Gameplay events

Produced by the game mechanic itself: `target_spawned`, `target_collected`, `object_hit`, `object_missed`, `goal_reached`, `obstacle_hit`, `round_completed`. There's no universal list — each event just needs to represent an occurrence meaningful for analysis or for reconstructing behaviour.

### 4.3 Interaction events

Discrete participant actions: `button_pressed`, `option_selected`, `pointer_clicked`, `key_pressed`, `touch_started`, `touch_ended`, `response_registered`. When the response is part of the observed variable, the event must preserve what identifies that response (`response_registered`, `response_value`, `response_position`, `timestamp`). It doesn't need to store an interpretation like correct/incorrect — that classification can be derived later from stimulus + response.

### 4.4 Stimulus events

Stimulus presentation is often central in experimental paradigms. A stimulus event can record: `stimulus_presented`, `stimulus_id`, `stimulus_type`, `stimulus_position`, `condition_id`, `timestamp`. This establishes the timing relation between stimulus and subsequent response:

```
Stimulus Presented → Participant Response → Outcome
```

Where response time matters, these timestamps are essential.

### 4.5 Outcome events

Immediate result of an interaction or trial: `success`, `failure`, `timeout`, `invalid_response`, `early_response`, `miss`. Useful operationally, but handle with care — whenever possible, preserve the raw data that lets the outcome be determined. Recording only `success` doesn't let you later verify whether the classification was correct.

More traceable structure:

```
Stimulus → Response → Raw data → Derived outcome
```

### 4.6 Timestamps

Every relevant event needs a time reference, to reconstruct: order of events, interval between events, action duration, response time, interruptions/pauses, and the timing relation between stimulus and response. Example: `stimulus_presented 10.250s`, `response_registered 11.083s` — their difference gives response time, provided the protocol defines the boundary events properly.

### 4.7 Identification and relationships

An isolated event has little analytical value if you can't tell which session, level, or trial it belongs to. Link events to `session_id`, `condition_id`, `level_id`, `trial_id`, `stimulus_id`, `event_id` as applicable. Not every field needs to exist on every event — the structure should reflect the game's and paradigm's organization.

### 4.8 Event sequence

Temporal sequence carries information. `stimulus_presented → input_received → response_registered → success` is different from `stimulus_presented → success → response_registered`. Order lets you detect inconsistencies, interruptions, and unexpected behaviour, and helps verify the protocol ran as expected.

### 4.9 Game-specific events

The telemetry standard should give a common structure without preventing game-specific events (`target_hit`, `ball_launched`, `card_flipped`, `button_selected`, `object_rotated`, `gesture_detected`), which can coexist with common ones (`session_start`, `level_start`, `stimulus_presented`, `response_registered`, `level_end`, `session_end`). Standardize the core concepts and relationships, not a rigid name list for every mechanic.

### 4.10 Events and continuous data

Event Telemetry and Continuous Telemetry aren't mutually exclusive — a game can log both at once (a stimulus event, a stream of position samples, then a response event). Events mark discrete occurrences; continuous data describes behaviour between them. Which to use depends on the phenomenon under study.

### 4.11 The sufficiency principle

Useful test: *if the results were deleted, could they be reconstructed from the recorded data?* If not, check what's missing. This matters at CIATEC specifically because evaluation may run later in the research system — preserving raw data lets metrics be recalculated and new analysis methods applied without recollecting data.

### 4.12 Worked example

A simple reaction task might generate:

```
session_start
level_start
stimulus_presented
  stimulus_id = S01, stimulus_type = visual, condition_id = C02, timestamp = T1
response_registered
  response_value = button_A, timestamp = T2
level_end
session_end
```

Reaction time = T2 − T1.

```
Controlled → stimulus_type, condition_id
Observed   → response_value, T1, T2
Derived    → reaction_time
```

This separation keeps the origin of each piece of information clear.

---

## 5. Continuous Telemetry

Continuous telemetry logs a variable over time rather than only discrete occurrences. It's needed when the information that matters lives in the behaviour *between* two events. At CIATEC, whether to use it depends on the paradigm and the variable of interest — not every game needs continuous capture.

### 5.1 When to use it

Appropriate when trajectory, dynamics, or the time-variation of a variable is itself part of the phenomenon: position, velocity, acceleration, orientation, trajectory, body pose, cursor position, gaze position. In a motor-control task, logging only the start and end of a movement discards the trajectory itself.

### 5.2 Event vs. continuous signal

Events are discrete: `stimulus_presented`, `movement_start`, `movement_end`, `response_registered`. Continuous signals are values over time:

```
timestamp   position_x   position_y
10.000      0.32         0.48
10.016      0.34         0.49
10.032      0.37         0.51
```

Both can coexist: `Stimulus → Movement Start → Continuous Signal → Movement End → Response`. Events delimit the structure of the action; signals describe its behaviour during execution.

### 5.3 Spatial variables

Describe where the participant, object, or cursor is: `position_x`, `position_y`, `position_z`, `target_x`, `target_y`, `distance_to_target`. Used to study trajectories, displacement, precision, and position–behaviour relations. Depending on the application, log normalized coordinates, screen coordinates, world coordinates, or another appropriate representation.

### 5.4 Temporal variables

Every observation in a continuous series needs a time reference: `timestamp`, `value`, and, when useful, `sampling_rate`, `sample_index`. The relation between samples must let you determine the signal's temporal sequence.

### 5.5 Sampling rate

30 Hz ≈ 30 samples/second, 60 Hz ≈ 60, 120 Hz ≈ 120. The rate needed depends on how fast the phenomenon changes and what analysis is intended. Too low a rate can erase relevant movement features; unnecessarily high rates inflate data volume without proportional analytical gain. Sampling rate is a decision tied to the variable and paradigm, not just a device spec.

### 5.6 Trajectory

A trajectory is a time-ordered sequence of positions (P1 → P2 → P3 → P4 → P5), from which metrics can be derived depending on the paradigm: `distance`, `path_length`, `movement_time`, `average_velocity`, `peak_velocity`, `acceleration`, `trajectory_variability`. These are derived — the observed trajectory itself should be preserved whenever needed to reproduce or review the analysis.

### 5.7 Body movement and pose

Games using camera or motion sensors may log body landmarks or other kinematic representations: `landmark_id`, `x`, `y`, `z`, `visibility`, `timestamp`. Choice of body parts and granularity should relate to the phenomenon under study — logging many body points with no defined analytical purpose just inflates data volume and processing complexity.

### 5.8 Continuous input

Some input devices produce continuous values (`mouse_position`, `joystick_axis`, `touch_position`, `wheel_position`, `gaze_position`), which can be treated as a time series (`timestamp`, `cursor_x`, `cursor_y`) and later related to game events to determine how the participant executed an action.

### 5.9 Relating signals to events

Continuous telemetry should be linkable to the events that delimit an action: e.g. `movement_start = T1`, `movement_end = T2` — the samples between T1 and T2 represent that movement. This lets specific features be extracted later without requiring the game client to know every metric that will ever be used.

### 5.10 Raw data and metrics

Preserve the raw signal before computing derived metrics:

```
Raw signal → Position samples → Trajectory → Distance → Velocity → Derived metric
```

This lets metrics be recalculated if the processing method changes — particularly relevant at CIATEC, since evaluation logic can stay in the research system while the game supplies the data.

### 5.11 Time-series quality

Continuous data can have problems that pure discrete telemetry doesn't: missing samples, duplicated samples, irregular intervals, timestamp errors, tracking loss, input loss, latency, sampling-rate changes, impossible values. A series declared as 60 Hz can still show irregular intervals — analysis should use the effective observed rate, not the nominal device spec.

### 5.12 Data volume

Continuous telemetry can produce large volumes of data. Before logging a variable, ask: what phenomenon does it represent, what analysis depends on it, what sampling rate is needed, for how long, will the raw data be preserved, and could the capture affect game performance? Collection should be sufficient, not indiscriminate.

### 5.13 Worked example

A cursor-to-target task might log events (`stimulus_presented`, `movement_start`, `movement_end`, `response_registered`) plus a continuous stream (`timestamp`, `cursor_x`, `cursor_y`) during movement, from which `movement_time`, `distance`, `velocity`, `trajectory_deviation` can be derived:

```
Controlled → target_position, target_size
Observed   → cursor_position over time, movement_start, movement_end
Derived    → movement_time, distance, velocity, trajectory_deviation
```

The game doesn't need to compute all of these metrics during execution.

---

## 6. Variables: Controlled, Observed, Derived

Experimental analysis in games requires distinguishing what the experiment defined, what was observed during interaction, and what was calculated afterward — central to keeping traceability between paradigm, participant behaviour, and the indicators obtained from telemetry:

```
CONTROLLED → OBSERVED → DERIVED
```

### 6.1 Controlled variables

Defined by the experiment or by the configuration sent to the game — what the researcher intends to manipulate, hold constant, or compare across conditions: `stimulus_type`, `stimulus_position`, `stimulus_duration`, `target_size`, `target_distance`, `number_of_options`, `difficulty`, `condition`. In the CIATEC paradigm these can be part of the structured configuration the game receives; the client executes it and logs the resulting data. A controlled variable must be identifiable in the session so behaviour can later be tied to the condition it occurred under.

### 6.2 Observed variables

What actually happened during interaction: `response_value`, `response_position`, `response_timestamp`, `player_position`, `input_sequence`, `trajectory`, `movement_start`, `movement_end`. These should represent the recorded observation without unnecessarily folding in interpretation. Recording `response_position = X` preserves the observation; recording only `response = correct` already bakes in a derived interpretation of stimulus + response.

### 6.3 Derived variables

Calculated from controlled and observed variables: `reaction_time`, `accuracy`, `error_rate`, `distance`, `velocity`, `trajectory_variability`, `movement_time`. A derived variable must have a clear relation to the data that produced it (`stimulus_timestamp` + `response_timestamp` → `reaction_time`; `position samples` → `trajectory` → `distance`), so it can be recalculated later.

### 6.4 The experimental chain

```
Paradigm → Controlled Variables → Game Mechanic → Observed Behaviour
→ Telemetry → Derived Metrics → Interpretation
```

The game implements the mechanic that operationalizes the experimental condition; interaction produces observable behaviour; telemetry records it; metrics are calculated afterward from the collected data.

### 6.5 Example: reaction time

Controlled: `stimulus_type = visual`. Observed: `stimulus_timestamp = T1`, `response_timestamp = T2`. Derived: `reaction_time = T2 − T1`. Reaction time isn't directly observed as an independent entity — it's calculated from the logged events.

### 6.6 Example: spatial precision

Controlled: `target_position`, `target_size`. Observed: `response_position`. Derived: `distance_to_target` — which can feed other precision/error metrics depending on the paradigm.

### 6.7 Example: trajectory

Controlled: `target_position`, `target_size`. Observed: `position_x(t)`, `position_y(t)`. Derived: `path_length`, `movement_time`, `average_velocity`, `peak_velocity`, `trajectory_deviation`. The observed trajectory is preserved as a time series so metrics can be recalculated from it.

### 6.8 Experimental variable ≠ metric

Three different roles: an experimental variable (e.g. `stimulus_position`) defines a condition or manipulation; an observation (e.g. `response_position`) records behaviour; a metric (e.g. `distance_to_target`) summarizes or transforms the observed data.

### 6.9 Metric ≠ biomarker

A metric calculated from telemetry is not automatically a digital biomarker:

```
Telemetry → Metric → Construct → Potential Digital Biomarker
```

Treating a metric as a biomarker for a construct requires an evidence base establishing that relationship. Reaction time, for instance, can be a relevant metric in many paradigms, but its interpretation depends on the task, the experimental conditions, and the construct under study.

### 6.10 Controlled variables and comparability

Comparing participants depends on properly maintaining experimental conditions — e.g. stimulus position, size, duration, or frequency must be logged explicitly when relevant. In CIATEC's paradigm file, the proportion of No-Go stimuli is flagged as a variable that can change task interpretation; in Stroop, the proportion of incongruent trials can influence the observed effect. A controlled variable isn't just a technical game parameter — it can be part of the definition of the phenomenon being measured.

### 6.11 What must be preserved

Whenever a metric can be recalculated from raw data, the data needed for that calculation must be preserved. Don't keep only `reaction_time = 843ms` — keep `stimulus_timestamp` and `response_timestamp`. Don't keep only `distance = 142px` — keep `position_x(t)` and `position_y(t)`. This keeps the door open to applying different analysis methods later.

---

## 7. Context and Reproducibility

Data from an experimental game shouldn't be analyzed in isolation — interpreting a response depends on the context it occurred in: game version, experimental condition, level, stimulus presented, and technical characteristics of the run. At CIATEC, telemetry must preserve enough context to relate collected data to the configuration that produced the observed behaviour.

### 7.1 Execution context

A session should identify, when applicable: `session_id`, `participant_id`, `game_id`, `game_version`, `telemetry_schema_version`, `condition_id`, `level_id`, `trial_id`, `stimulus_id`.

### 7.2 Game version

Log `game_version` because implementation changes can change observed behaviour or how data is produced. Analysis combining sessions from different versions should check compatibility for the analysis's purpose. A small visual change can alter participant behaviour; a change in interaction logic can directly alter the observed variable; a change in telemetry implementation can alter data meaning or availability.

### 7.3 Telemetry schema version

Data structure can change independently of the game version — log `telemetry_schema_version` when relevant, to distinguish a mechanic change from a data-recording change.

### 7.4 Experimental condition

The condition a session or trial ran under must be identifiable (`condition_id = C03`). When a condition has specific parameters, preserve them or make them recoverable from the configuration used (e.g. `stimulus_position = left`, `stimulus_duration = 500`, `target_size = 80`).

### 7.5 Level, trial, and stimulus

```
session → condition → level → trial → stimulus → response
```

Without these relationships it can be impossible to determine which stimulus produced which response, or under which condition a metric was obtained.

### 7.6 Randomization and seed

When randomization affects order, position, stimuli, or other elements, and reproducibility matters, preserve `random_seed`. The goal isn't necessarily to visually replay every session, but to determine how the configuration was generated and, when technically possible, reproduce the sequence used. Randomization should be treated as part of the experimental context whenever it can affect interpretation of results.

### 7.7 Device and input method

Log when relevant: `device_type`, `operating_system`, `input_method`, `screen_resolution`, `orientation`. Input methods: mouse, keyboard, touch, gamepad, camera, motion sensor. Matters especially when interaction mode can change observed behaviour.

### 7.8 Sampling rate

For continuous data, `sampling_rate` should be part of the context whenever it's needed to interpret the time series (e.g. `sampling_rate = 60 Hz`). When the effective rate can differ from the nominal one, that difference should factor into data-quality analysis.

### 7.9 Time

Timestamps reconstruct event order. Preserve enough to interpret time correctly (`timestamp`, `session_start`, `event_time`, `sample_time`), to avoid incorrectly combining data across sessions, devices, or time references.

### 7.10 Reproducibility

Reproducibility here doesn't mean replaying the whole game run exactly. It mainly means preserving enough information to: identify the experimental condition; identify the system version; reconstruct the relevant event sequence; relate stimuli to responses; correctly interpret continuous data; recalculate derived metrics; and verify the run's consistency.

### 7.11 Example

Two responses with the same `reaction_time = 800ms` look equivalent without more context. But full data might show:

```
Session A: condition_id = C01, stimulus_type = visual,   game_version = 1.2, input_method = touch
Session B: condition_id = C02, stimulus_type = auditory, game_version = 1.4, input_method = keyboard
```

Same derived value, different experimental context — an isolated metric doesn't necessarily carry all the information needed for interpretation.

### 7.12 Context as part of the data

At CIATEC, context isn't secondary information:

```
Context + Experimental Condition + Observed Behaviour → Telemetry → Derived Metrics
```

The same observation can mean different things under different experimental conditions.

---

## 8. From Telemetry to Metric

Telemetry is the collected data; a metric is a calculated representation of a specific characteristic of the observed behaviour or performance. At CIATEC, going from telemetry to metric must keep a traceable relation between raw data, calculation method, and the phenomenon being analyzed:

```
Telemetry → Feature Extraction → Metric → Construct → Interpretation
```

### 8.1 Telemetry as raw material

Collected data is the raw material for analysis: `stimulus_timestamp`, `response_timestamp`, `response_position`, `target_position`, `position_x(t)`, `position_y(t)`, `input_sequence`. It doesn't need to directly represent the final analysis result — telemetry's job is to preserve enough information for different metrics to be calculated later.

### 8.2 Feature extraction

Transforming raw data into characteristics usable in analysis: `position_x(t)`, `position_y(t)` → `trajectory` → `path_length`; or `stimulus_timestamp`, `response_timestamp` → `reaction_time`. A feature can be as simple as a time difference or involve a full time series.

### 8.3 Temporal metrics

Describe time-related characteristics: `reaction_time`, `movement_time`, `response_latency`, `inter_response_interval`. E.g. `reaction_time = response_timestamp − stimulus_timestamp`. The metric's meaning depends on which events define the start and end of the measure.

### 8.4 Performance metrics

Describe the outcome of interactions: `accuracy`, `error_rate`, `success_rate`, `completion_time`, `number_of_errors`. Can be calculated at different levels (trial, level, session, participant, condition) — the aggregation unit should follow the research question.

### 8.5 Spatial metrics

`distance_to_target`, `path_length`, `trajectory_deviation`, `endpoint_error` — e.g. `position samples → trajectory → path_length`. A spatial metric should be interpreted relative to the space and task it was obtained in.

### 8.6 Movement metrics

`velocity`, `peak_velocity`, `acceleration`, `jerk`, `movement_duration`:

```
Position → Velocity → Acceleration → Jerk
```

Each transformation adds a processing layer, so the derivation method should be known and, when relevant, documented.

### 8.7 Behavioural metrics

Event sequences can also produce behavioural metrics: `number_of_attempts`, `number_of_restarts`, `pause_frequency`, `action_sequence`, `response_consistency` — describing interaction patterns that complement performance measures.

### 8.8 Aggregation

A metric can be calculated at different levels — e.g. `reaction_time = 820ms` at trial level, `mean_reaction_time = 805ms` at level level, `mean_reaction_time = 798ms` at session level. Aggregation changes the unit of analysis, so a metric definition should specify, when needed: `metric`, `unit`, `aggregation`, `population`, `condition`.

### 8.9 Distributions and variability

A mean doesn't always represent behaviour well. Consider `median`, `standard_deviation`, `variance`, `interquartile_range`, `coefficient_of_variation`, `within_subject_variability` as needed. For measures like reaction time, the distribution can carry information a single mean would lose.

### 8.10 Metric and construct

A metric describes an observable/calculable aspect of behaviour; a construct is the theoretical phenomenon the paradigm investigates. The relation isn't automatic:

```
Telemetry → Metric → Construct
```

CIATEC's paradigm file uses measures like reaction time, errors, accuracy, trajectory, and spatial efficiency to investigate distinct constructs across different tasks — the same metric type can mean different things depending on the task.

### 8.11 Metric and digital biomarker

A metric can contribute to defining a digital biomarker but isn't automatically one:

```
Raw Telemetry → Derived Metric → Construct → Evidence / Validation → Digital Biomarker
```

The relation depends on scientific grounding and validation.

### 8.12 Metric reproducibility

A metric must be specified well enough to be recalculated. Know, when relevant: `input data`, `formula`, `processing method`, `time window`, `aggregation method`, `units`, `exclusion rules`. Example: `reaction_time = response_timestamp − stimulus_timestamp`. Additional rules (e.g. excluding anticipatory responses) are part of the metric's definition too.

### 8.13 Raw vs. derived data

The architecture should avoid replacing raw data with calculated results:

```
Raw Telemetry → Processing → Derived Metrics → Analysis
```

This allows recalculating metrics, fixing algorithms, testing different methods, developing new indicators, and running retrospective analyses on existing datasets — particularly important in CIATEC's architecture, where evaluation can stay separate from game execution.

### 8.14 Complete example

Controlled: `stimulus_type`, `stimulus_position`, `condition_id`. Observed: `stimulus_timestamp`, `response_timestamp`, `response_position`. Metrics: `reaction_time`, `spatial_error`, `accuracy`.

```
Condition → Stimulus → Response → Raw Telemetry → Metrics → Construct
```

---

## 9. Data Quality and Validity

Telemetry quality determines how reliable the resulting analysis is. A dataset can hold many records and still be unusable if there is loss, temporal inconsistency, capture failure, or ambiguity about experimental context.

Missing data can come from network, client, or software problems, and its absence isn't necessarily random — it can bias analysis. At CIATEC, data quality must be considered from collection through metric generation.

### 9.1 Session integrity

First check: was the session recorded as a structurally complete sequence (`session_start ... level_start ... level_end ... session_end`)? A session ending without `session_end` doesn't automatically mean invalid data — it could indicate an interruption, unexpected close, technical failure, or lost connection. Session state should distinguish these situations when possible.

### 9.2 Missing data

Can occur at different levels: participant, session, event, trial, sample, or field. Identify and analyze missing data before using it. Common causes: network failure, client failure, software error, sensor failure, tracking loss, interruption. Absence can also relate to the participant's own behaviour — don't assume missing data is random.

### 9.3 Duplicate events

Can come from implementation bugs, resent data, or communication issues (e.g. `response_registered` logged twice for the same occurrence). Duplication can distort metrics like `number_of_responses`, `accuracy`, `error_rate`. Give each event an identifier or field combination that lets duplicates be detected.

### 9.4 Temporal order

Event sequence should match the game's logic. Expected: `stimulus_presented → response_registered → success`. A sequence like `success → stimulus_presented → response_registered` can indicate a logging error, async processing, or data inconsistency — check order especially when analysis depends on time differences.

### 9.5 Timestamps

Check for missing timestamps, duplicated timestamps, negative intervals, unexpected gaps, inconsistent ordering. For continuous data, also check sample-interval regularity (e.g. `T1→T2 = 16ms`, `T2→T3 = 17ms`, `T3→T4 = 250ms` — the last jump can indicate sample loss or a processing interruption).

### 9.6 Sampling rate

Nominal sensor rate doesn't guarantee constant effective rate. A 60 Hz capture can show irregular intervals due to processing load, tracking loss, network latency, or device limitations. When analysis depends on temporal dynamics, use the effective observed rate.

### 9.7 Tracking loss

Camera, pose-estimation, eye-tracking, and other sensors can temporarily lose observation. Don't silently convert a loss into a valid position — log capture-quality state when possible (`tracking_valid = true/false`) to distinguish a real observation from a missing one.

### 9.8 Latency

Latency can occur between stimulus presentation, input detection, event registration, telemetry transmission, and server reception — these times aren't equivalent. For time-sensitive measures, define which timestamp represents the experimentally relevant moment; server arrival time shouldn't be confused with when the participant actually responded.

### 9.9 Impossible values

Validation should catch values incompatible with a variable's domain: negative `reaction_time`, position outside valid range, impossible coordinates, negative duration, invalid event type. These can indicate implementation errors, wrong transformations, or data corruption. Validation rules should be defined per variable and paradigm.

### 9.10 Cross-entity consistency

Check relations between data too — e.g. does `trial_id = T05` belong to the right session, does `stimulus_id = S10` belong to the right trial, does `response_id = R18` respond to the right stimulus. Relational consistency is needed to reconstruct the experimental sequence.

### 9.11 Session reconstruction

One of the most important checks: try to reconstruct a session from telemetry alone (`Session → Condition → Level → Trial → Stimulus → Response → Outcome`). If you can't determine what happened during a session, investigate whether telemetry is incomplete or the data model doesn't preserve enough relations.

### 9.12 Result reconstruction

Check whether results can be recalculated from raw telemetry. If only `reaction_time = 843ms` was stored (instead of `stimulus_timestamp` + `response_timestamp`), you can't verify or recalculate it from the original events. Same principle applies to spatial, kinematic, and behavioural metrics.

### 9.13 Quality vs. validity

Related but different concepts. Data can be technically good quality (complete telemetry, correct timestamps, no missing data) and still not adequately represent the construct under study. CIATEC's paradigm file notes that gamification can introduce confounds related to engagement, prior gaming experience, and virtual rewards — validating a game as a measurement instrument requires dedicated validity and reliability studies.

### 9.14 Technical vs. experimental data

Technical failures are part of session context too. The PPI for the ATGCP-TEA project, for example, logged sessions affected by camera failure and system freezes — these ran under conditions different from those intended, and require caution in interpretation. The telemetry system should flag these situations when possible: `camera_failure`, `tracking_loss`, `application_pause`, `connection_loss`, `unexpected_exit`.

### 9.15 Quality as part of the analysis

Quality shouldn't be treated only as a later cleanup step — it should be present at collection, validation, storage, processing, metric calculation, and analysis. The earlier an inconsistency is caught, the lower the risk it gets silently baked into results.

---

## 10. Game Analytics at CIATEC

At CIATEC, Game Analytics must connect the experiment's scientific design to game execution and the data produced during interaction:

```
Paradigm → Construct → Experimental Variable → Game Mechanic
→ Behaviour → Telemetry → Metric → Biomarker
```

The game operationalizes the paradigm through its mechanics; telemetry preserves the data needed for later analysis.

### 10.1 The game's role

The game isn't just an interface for presenting a test — its core mechanic must implement the relevant structure of the experimental paradigm. In CIATEC's model:

```
Research System → Configuration → Game → Gameplay → Raw Telemetry → Research System → Evaluation
```

The client receives a structured configuration, runs the mechanic, and returns raw telemetry; evaluation logic stays separate from gameplay execution, so new analysis methods can be applied later to already-collected data.

### 10.2 From paradigm to game

Development should start from the paradigm and construct under investigation:

```
Paradigm → Construct → Experimental Variables → Game Mechanic → Player Behaviour → Telemetry → Metric
```

Each step should relate explicitly to the one before it. Example, for a reaction task:

```
Paradigm             → Simple Reaction Time
Construct            → sensorimotor response speed
Experimental Variables → stimulus modality, temporal uncertainty
Game Mechanic         → present stimulus and request a response
Behaviour             → responding to the stimulus
Telemetry             → stimulus_timestamp, response_timestamp
Metric                → reaction_time
```

CIATEC's paradigm file lays out this structure for different paradigms, including Simple Reaction Time, Go/No-Go, Stroop, Flanker, spatial-navigation tasks, and mental rotation.

### 10.3 Experimental variables

Experimental variables must be defined before implementing the mechanic — the game needs to know which parameters it must receive to run the defined condition: `stimulus_type`, `stimulus_position`, `stimulus_duration`, `target_size`, `target_distance`, `number_of_options`. Not every gameplay parameter is an experimental variable — a variable counts as experimental when changing it matters for the task or the hypothesis under study. In Go/No-Go, No-Go stimulus frequency can change the nature of the task; in Stroop, the proportion of incongruent trials can influence the observed effect.

### 10.4 Telemetry as the interface between game and research

Telemetry is the main interface between game execution and the research system: the game produces **Raw Telemetry**, the research system can then produce **Derived Metrics**, and later **Biomarkers**. This reduces coupling between game mechanics and evaluation algorithms, and lets different clients (Unity, Flutter) share the same server-side evaluation logic.

### 10.5 What's common across all games

Not every game needs the same variables, but some conceptual elements recur: Session, Condition, Level, Trial (when applicable), Stimulus (when applicable), Response (when applicable), Event, Timestamp, Context. A purely decisional task may depend mainly on events and timestamps; a motor task may need time series of position, velocity, or pose.

### 10.6 What's paradigm-specific

Paradigm-specific telemetry should follow the experimental question:

```
Reaction Time      → stimulus onset, response timestamp
Go/No-Go           → stimulus type, response, omission, commission
Fitts              → target position, target size, pointer trajectory
Spatial Navigation → position over time, target location, path
```

Don't force every possibility into one mandatory standard — the standard should define a common structure for relating data, while leaving each paradigm free to log what's scientifically necessary.

### 10.7 Raw data as an analytical asset

CIATEC should prioritize preserving raw telemetry:

```
Raw Telemetry → Metric A → Metric B → Metric C
```

One collection can produce different metrics as the research develops. If only aggregated results are stored, new analysis may require a new data collection; if raw data is preserved, new algorithms can be applied retrospectively.

### 10.8 Results and evaluation

The game's results screen shouldn't be confused with full scientific analysis. The game can show immediate feedback to the participant (score, completion, feedback, performance), while the research system calculates `reaction_time`, `accuracy`, `trajectory_metrics`, `variability`, `biomarkers`. This separation lets participant experience and scientific evaluation serve different purposes.

### 10.9 Game Analytics and accessibility

At CIATEC, accessibility and inclusion aren't external to the analysis. A change in interface or interaction method can change observed behaviour — touch, keyboard, mouse, camera, alternative response modality. When the interaction modality can affect the measure, log it as experimental or technical context. The ATGCP-TEA project's PPI highlights the importance of considering usage context, including differences in device access and interaction adaptation needs.

### 10.10 Game Analytics and validity

Detailed telemetry doesn't guarantee scientific validity — data quality, measurement, construct validity, and scientific validation are distinct steps:

```
Data Quality → Measurement → Construct Validity → Scientific Validation
```

CIATEC's paradigm document notes that gamification can introduce confounds related to engagement, prior gaming experience, and virtual rewards — validating each game as a measurement instrument requires dedicated studies, including convergent validity and test–retest reliability. Game Analytics provides the observation and analysis infrastructure — it doesn't replace instrument validation.

### 10.11 Minimum CIATEC model

As a practical reference, an implementation should be able to represent, when applicable:

```
Session
 ├── Context
 ├── Condition
 ├── Level
 │    └── Trial
 │         ├── Stimulus
 │         ├── Response
 │         ├── Events
 │         └── Continuous Telemetry
 └── Derived Metrics
```

This isn't a mandatory database schema for every game — it's a conceptual reference to keep the data a game produces tied to the experiment that generated it.

---

The point of Game Analytics at CIATEC isn't collecting as much data as possible — it's building a traceable chain from research question to biomarker:

```
Research Question → Paradigm → Construct → Experimental Variables
→ Mechanic → Behaviour → Telemetry → Metric → Biomarker
```

When that chain holds, the game stops being just an interactive application and becomes an observable system inside an experiment. The student builds the game; the CIATEC platform defines the experiment.