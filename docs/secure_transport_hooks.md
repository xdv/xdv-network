# Secure Transport Hooks

Secure transport hooks are implemented in `src/network_secure_transport.ds`.

## Scope

- deterministic attestation token format
- per-domain attestation validation
- hybrid key material derivation
- session open/validate semantics
- pre-send and post-receive verification hooks

## Hook Path

1. open session
2. pre-send hook validates session + frame token + domain binding
3. post-receive hook validates scope/domain compatibility

## Key APIs

- `build_attestation_token(...)`
- `verify_attestation_for_domain(...)`
- `open_session(...)`
- `session_is_valid(...)`
- `stl_pre_send_hook(...)`
- `stl_post_receive_hook(...)`
