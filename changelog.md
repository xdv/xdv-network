# Changelog

## 0.1.1 - XDV-040 Network Core Implementation

- Implemented deterministic network contracts in `src/network_contracts.ds`.
- Implemented deterministic frame/token encode/decode/validation in `src/network_frame.ds`.
- Implemented secure transport attestation/session hooks in `src/network_secure_transport.ds`.
- Implemented domain-aware K/Q/Phi channel routing in `src/network_channels.ds`.
- Implemented deterministic fault ordering reconciliation in `src/network_order.ds`.
- Added behavior tests in `src/network_tests.ds`.
- Added aggregate test entrypoint `tests/network_fault_ordering_e2e.ds`.
- Updated README and test documentation for current behavior.

## 0.1.0 - Initial Skeleton

- Created project scaffold for XDV Network.
- Added State.toml, README.md, and docs/test placeholders.
- Imported LICENSE from xdv-os/LICENSE.
