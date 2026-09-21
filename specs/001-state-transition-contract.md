# SPEC-001 — State Transition Contract

Status: DRAFT / ENGINEERING BASELINE

## Objective

Make state changes explicit, attributable and testable.

## Transition

```text
PREVIOUS STATE
      |
      +-- triggering evidence/assertion change
      |
      +-- dependency impact
      |
      +-- policy evaluation
      v
TRANSITION CONTRACT
      |
      +-- eligibility
      +-- consequence type
      +-- required review
      +-- resulting state version
      v
NEW STATE / DEFERRED STATE
```

## Contract fields

- `transition_id`
- `entity_id`
- `from_state_version`
- `trigger_refs`
- `dependency_refs`
- `transition_type`
- `eligibility_status`
- `policy_decision`
- `to_state_version`
- `created_at`

## Required behavior

A transition must be deterministic with respect to its recorded inputs and policy version. If required evidence is missing, the system may produce `deferred` or `needs_review` rather than inventing a state.

## Audit requirement

The transition record must support reconstruction of:

`trigger -> dependency impact -> policy evaluation -> resulting version`

No transactional side effect is part of this specification.
