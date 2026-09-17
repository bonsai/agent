# agent

## Definition

An **Agent** is an operational entity that arrives in an environment, senses it, acts upon it, and improves the environment.

> **Agent = 環境に降り立ち、感知し、働きかけ、環境を改善する稼働体**

An Agent does not merely execute a predefined task. It exists in an environment, senses the current state, interprets what it senses, decides what to do, acts through available interfaces, and changes the environment.

```text
Environment
    ↓
  Sensing
    ↓
Observation
    ↓
Cognition
    ↓
Decision
    ↓
Action
    ↓
Environment Change
    ↓
Improved / Updated Environment
    ↺
```

## Type and Implementation

**Type is a concept. JSON and YAML are formats used to describe and implement that concept.**

```text
Type
  ↓
Concept
  ↓
Type Definition
  ↓
JSON / YAML
  ↓
Implementation / Validation
```

Therefore:

- **Type** — defines what something is as a concept.
- **Type Definition** — formalizes that concept.
- **JSON / YAML** — represent the definition in machine-readable form.
- **Agent** — the concept of an environment-operating entity.
- **Running Agent** — an implementation/instance of that concept.

The canonical type system is maintained in [`bonsai/TYPE`](https://github.com/bonsai/TYPE).

## Core Principle

```text
Agent × Environment
        ↓
     Sensing
        ↓
    Cognition
        ↓
     Decision
        ↓
      Action
        ↓
Environment Change
        ↓
  Environment Update
        ↺
```

The environment may be physical, digital, social, organizational, or computational.

## Agent, Goal, State, Action

- **Goal** — defines a desired state or direction of change.
- **Environment** — the world in which the Agent operates.
- **State** — describes the current condition of the environment and what is known, unknown, or uncertain.
- **Agent** — senses the environment, decides what to do, and operates within it.
- **Action** — changes or observes the environment.
- **Workflow** — defines how Actions may be composed or repeated.
- **Evidence** — records what supports an observed state or transition.

```text
Goal
  ↓
Environment / State
  ↓
Agent
  ↓
Decision
  ↓
Action
  ↓
Environment / State'
  ↓
Improvement / Update
  ↺
```

## Agent and Interface

An Agent interacts with its environment through **Interfaces**.

```text
Agent
  ↓
Interface
  ↓
Environment
```

Interfaces can be physical or digital:

```text
Eye       ↔ Light / Air
Ear       ↔ Sound / Air
Voice     ↔ Air
Keyboard  ↔ Computer
API       ↔ Software
Agent     ↔ Agent
```

Therefore an Agent's operation depends on what it can **sense**, what it can **understand**, and what it can **change** through its available interfaces and actions.

## Relation to TYPE

- **TYPE** — defines what an Agent is as a Type.
- **Agent** — defines the operational concept and environment loop.
- **Action** — defines what the Agent does.
- **Interface** — defines how different Types interact.
- **xX** — defines the experience produced through Subject × World interaction.

```text
TYPE
  ↓
Agent Type
  ↓
Agent Instance
  ↓
Environment
  ↓
Sensing
  ↓
Cognition
  ↓
Decision
  ↓
Action
  ↓
Environment Change
  ↓
xX / Experience Update
```

See:

- [`bonsai/TYPE`](https://github.com/bonsai/TYPE)
- [`bonsai/TYPE/agent.md`](https://github.com/bonsai/TYPE/blob/main/agent.md)

## Minimal JSON / YAML representation

```yaml
type: Agent
definition: >
  環境に降り立ち、感知し、働きかけ、環境を改善する稼働体
environment:
  - Environment
sensing:
  - Observation
cognition:
  - Reason
  - Decide
actions:
  - Action
output:
  - StateChange
  - EnvironmentImprovement
```

## Operational Loop

```text
arrive
  ↓
sense
  ↓
understand
  ↓
decide
  ↓
act
  ↓
improve
  ↓
sense again
  ↺
```

> **Agent = an operational entity that arrives in an environment, senses it, acts upon it, and improves the environment.**
