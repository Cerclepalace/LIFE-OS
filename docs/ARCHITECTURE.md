# LIFE-OS Architecture

## Core model

LIFE-OS is organized around five conceptual layers:

1. Evidence
2. Epistemic state
3. Temporal state
4. World model
5. Operational propagation

## Planes

### Business Plane
Company, departments, roles, people, processes, tasks, systems, customers, suppliers, policies, KPIs and dependencies.

### Control Plane
Agent registry, prompt compiler, tool registry, policy engine, workflow compiler, evaluation factory, deployment manager, version manager and permission manager.

### Runtime Plane
Orchestrator, model gateway, agent runtime, memory layer, tool gateway, workflow runtime and approval service.

### Evidence Plane
Event log, trace store, audit log, cost ledger, evaluation results, business outcomes and incident register.

## Safety boundary

Consequential actions should pass through explicit policy, permission and approval controls. Transactional functionality is intentionally absent from the initial foundation.

## Current research direction

Primary candidate area:

Evidence -> assertion state -> personal state -> semantic dependency graph -> type-specific operational consequence.

This is a research hypothesis, not a statement of patentability.
