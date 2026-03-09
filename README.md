# XDV Network

Version: 0.1.0
Status: active
Language: Dust Programming Language (DPL)

## Specification Alignment

Primary specification: XDV-040 in `xdv-spec`.

Implemented focus for this milestone:

1. Deterministic framing and secure transport hooks.
2. Domain-aware K/Q/Phi channels.
3. Ordering validation under network faults.

## Purpose

Cross-domain deterministic network stack for K/Q/Phi orchestration.

## Modules

- `src/network_contracts.ds`
  Defines normative domain/layer/mode/capability/operation guards.

- `src/network_frame.ds`
  Deterministic frame header/token encode/decode and validation.

- `src/network_secure_transport.ds`
  STL session model with attestation verification and send/receive hook checks.

- `src/network_channels.ds`
  K/Q/Phi channel routing with policy checks, frame construction, and hook invocation.

- `src/network_order.ds`
  Deterministic ordering and fault-path reconciliation logic.

- `src/network_tests.ds`
  Behavior tests for framing, transport, channel policy, and fault ordering.

- `src/main.ds`
  Startup validation, smoke send, and self-test entrypoints.

## Design Notes

- Q channel rejects raw-state transfer operations.
- Phi channel rejects implicit merge operations.
- Q/Phi session establishment requires attestation token validation.
- Fault ordering reconciliation uses deterministic epoch selection and stable order keys.

## Build

```bash
dust check xdv-network/src
```

## Test

```bash
dust check xdv-network/src/network_tests.ds
dust check xdv-network/tests/network_fault_ordering_e2e.ds
```

## Integration Contracts

- Preserve deterministic ordering semantics under fault paths.
- Preserve capability-scope validation per domain.
- Keep transport hook checks in path for all channel sends.
- Keep behavior replay-equivalent for identical inputs.
