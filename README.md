# XDV Network

Version: 0.1.0
Status: planned
Language: Dust Programming Language (DPL)

## Specification Alignment

Primary specification: XDV-040 in xdv-spec.

## Purpose

Cross-domain deterministic network stack for K/Q/Phi orchestration.

## Scope

This project is responsible for:

- Implementing normative requirements defined by XDV-040.
- Publishing deterministic behavior contracts for integration with xdv-os.
- Providing reusable modules for cross-repo integration.
- Supplying verification and conformance fixtures for regression control.

## Planned Deliverables

- knl, qdl, psl, stl
- Public APIs in src/
- Test fixtures in tests/
- Design and interface docs in docs/

## Repository Layout

- src/ : core module implementations.
- tests/ : deterministic unit/integration/conformance fixtures.
- docs/ : architecture, protocol, and usage documentation.
- State.toml : workspace manifest.
- changelog.md : release and milestone notes.

## Initial Module Plan

- src/main.ds: project entrypoint and top-level orchestration.
- src/contracts.ds: normative contract models and validators.
- src/protocol.ds: wire/protocol semantics for external interfaces.
- src/errors.ds: canonical error model and deterministic mapping.
- src/tests.ds: local test harness entry surface.

## Dependencies

Current planned dependencies:

- xdv-kernel, xdv-runtime, xdv-sdbm, xdv-lib
- dust runtime/toolchain packages as required by integration profile

## Integration Contracts

- Must preserve deterministic ordering semantics.
- Must avoid implicit cross-domain state mutation.
- Must emit structured metadata for replay and audit paths.
- Must remain compatible with xdv-os build and boot/runtime contracts.

## Build

dust check xdv-network/src

## Test

dust test xdv-network/tests

## Milestones

1. M1: scaffold + contract models.
2. M2: core pipeline implementation.
3. M3: deterministic behavior and fixture hardening.
4. M4: xdv-os integration and conformance gating.

## Notes

This project is initialized as a skeleton template and intentionally starts with minimal source implementation.
