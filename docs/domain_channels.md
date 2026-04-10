# Domain Channels

Domain-aware channels are implemented in `src/network_channels.ds`.

## Domain Rules

- K channel: classical process/control/trace traffic
- Q channel: allows entangle/teleport/measure/contract-sync; rejects raw-state operations
- Phi channel: allows window/transform/stability operations; rejects implicit merge

## Channel Flow

1. validate domain + capability + operation
2. open secure session
3. build deterministic frame token
4. invoke secure pre-send/post-receive hooks
5. reconcile fault ordering when fault code is present

## Key APIs

- `send_k_channel(...)`
- `send_q_channel(...)`
- `send_phi_channel(...)`
- `send_domain_operation(...)`
