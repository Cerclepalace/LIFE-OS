# SPEC-000 — Canonical Domain Model

Status: DRAFT / ENGINEERING BASELINE

## 1. Objective

Define the minimum canonical objects shared by the LIFE-OS runtime, evidence system, memory layer and operational propagation engine.

## 2. Core objects

### Evidence
An observed or imported artifact that can support, weaken or invalidate an assertion.

Required conceptual fields:
- `evidence_id`
- `source_id`
- `observed_at`
- `recorded_at`
- `content_ref`
- `integrity_ref`
- `reliability`

### Assertion
A machine-readable proposition about an entity or state, linked to one or more evidence items.

Required conceptual fields:
- `assertion_id`
- `subject_id`
- `predicate`
- `value`
- `status`
- `evidence_refs`
- `valid_from`
- `valid_to`
- `version`

### State
A versioned representation of an entity at a point or interval in time.

Required conceptual fields:
- `state_id`
- `entity_id`
- `version`
- `valid_from`
- `valid_to`
- `derived_from`
- `status`

### Dependency
A typed semantic relationship indicating that a downstream object may be affected by a change in an upstream object.

Required conceptual fields:
- `dependency_id`
- `upstream_id`
- `downstream_id`
- `dependency_type`
- `consequence_policy`

### Consequence
A typed operational effect produced when a relevant upstream state changes.

Examples:
- recompute
- qualify
- suspend
- reschedule
- require_review
- invalidate
- create_candidate_action

Consequences do not execute privileged or transactional actions automatically in the foundation layer.

## 3. Canonical relationship

```text
Evidence
   |
   v
Assertion
   |
   v
Personal State
   |
   v
Semantic Dependency
   |
   v
Typed Consequence
```

## 4. Invariants

1. An assertion cannot claim stronger evidentiary support than its linked evidence permits.
2. A state version is immutable once committed; a new state is represented by a new version.
3. Every state transition must identify its upstream cause or evidence basis.
4. Dependency edges are typed rather than treated as generic lineage.
5. A consequence is proposed or routed through policy before any consequential action.
6. Historical state must remain reconstructable from recorded versions/events.
7. Evidence timestamps distinguish observation time from recording time.
8. Unknown and unresolved states are first-class values.

## 5. Research boundary

This model is an engineering baseline and a research hypothesis. It does not establish novelty, inventive step, patentability or freedom-to-operate.
