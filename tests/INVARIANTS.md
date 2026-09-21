# LIFE-OS Invariants

These invariants define the first validation gate for the canonical model.

| ID | Invariant | Initial test strategy |
|---|---|---|
| INV-001 | State versions are immutable | Attempt update; require new version |
| INV-002 | Transition has a trigger | Reject transition without trigger reference |
| INV-003 | Transition identifies prior state | Reject transition without `from_state_version` |
| INV-004 | Evidence records observation and recording time separately | Schema validation |
| INV-005 | Assertion references evidence | Reject unsupported assertion |
| INV-006 | Unknown is representable | Enum/schema test |
| INV-007 | Dependency is typed | Reject untyped dependency |
| INV-008 | Consequence passes policy | Reject direct privileged execution |
| INV-009 | Historical state is reconstructable | Replay/version test |
| INV-010 | Policy version is traceable | Transition audit test |

## Gate

The specification is not considered implementation-complete until these invariants have executable tests.
