# XDV Network Tests

Deterministic tests and fixtures for `xdv-network`.

## Covered Behaviors

- Deterministic message framing and token validation.
- Secure transport session/attestation hooks.
- Domain-aware K/Q/Phi channel policy enforcement.
- Ordering stability under network fault paths.

## Entrypoints

- `xdv-network/src/network_tests.ds` : core unit/integration checks.
- `xdv-network/tests/network_fault_ordering_e2e.ds` : aggregate test entrypoint.

## Run

```bash
dust check xdv-network/src
dust check xdv-network/tests/network_fault_ordering_e2e.ds
```
