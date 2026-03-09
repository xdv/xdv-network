# Deterministic Framing

`xdv-network` implements deterministic message framing in `src/network_frame.ds`.

## Frame Model

A frame header is encoded from:

- domain
- layer
- transport mode
- logical timestamp
- node id
- process rank
- sequence
- fault epoch

A frame token is derived by binding header + payload hash bucket.

## Determinism Guarantees

- identical inputs produce identical header/token values
- stable decode/re-encode round trip validation
- ordering key generation is independent of wall-clock state

## Key APIs

- `encode_header(...)`
- `encode_frame_token(...)`
- `decode_*` field readers
- `frame_order_key(...)`
- `validate_frame_token(...)`
