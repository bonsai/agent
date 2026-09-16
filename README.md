# agent

## Definition

An **Agent** is an actor that observes a State, selects or performs an Action, and causes a State Transition toward a Goal.

```text
Goal
  ↓
State
  ↓
Agent
  ↓
Action
  ↓
State'
  ↓
Done?
```

The Agent is not the Goal, and it is not the Workflow itself.

- **Goal** — defines the desired completion state.
- **State** — describes the current state, including uncertainty and what is known or unknown.
- **Agent** — decides what to do next based on State and Goal.
- **Action** — changes or observes the world.
- **Workflow** — defines how Actions may be composed or repeated.
- **Evidence** — records why a State transition can be considered valid.

## Core Principle

> **Agent = State → Decision → Action → State**

An Agent continuously reduces the gap between the current State and the Goal, but does not assume that every gap can or should be eliminated in advance.

```text
Current State
   │
   ├─ known
   ├─ unknown
   └─ uncertain
        ↓
     Decision
        ↓
      Action
        ↓
   New State
        ↓
  Goal satisfied?
    ├─ yes → Done
    └─ no  → continue
```

## Agent and ambiguity

Ambiguity belongs primarily to **State**. An Agent does not merely "execute a task"; it uses the current State to determine what remains unclear and chooses an appropriate next action.

```text
Vague State
    ↓
observe / clarify / test / research / act
    ↓
more explicit State
    ↓
repeat
    ↓
Goal State
```

Therefore an Agent may perform actions whose purpose is not immediately to complete the Goal, but to make the State more certain.

## Minimal model

```yaml
agent:
  observes: state
  reasons_from:
    - goal
    - state
    - constraints
  selects: action
  produces: state_transition
  requires_evidence: true
```

## Decision loop

```text
while not goal.done(state):
    state = observe(state)
    decision = decide(goal, state, constraints)
    action = select(decision)
    result = execute(action)
    state = update(state, result)
    evidence = record(result)
```

The loop stops when the **Goal's completion state is satisfied**, not merely when an Action has been executed.

## Relationship to solve

`solve` is the process that transforms an ambiguous request into an actionable Goal and a sequence of State transitions.

```text
Request
  ↓
Solve
  ↓
Intent / Goal
  ↓
State
  ↓
Agent
  ↓
Action
  ↓
State'
  ↓
Evidence
  ↓
Done
```

The Agent is therefore the **decision-and-action actor inside the solving loop**.
