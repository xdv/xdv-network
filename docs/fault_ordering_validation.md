# Fault Ordering Validation

Fault ordering logic is implemented in `src/network_order.ds`.

## Fault Codes

- none
- link drop
- retry timeout
- partitioned path

## Behavior

- map fault code to deterministic fault epoch
- build base/fault headers from stable input tuple
- enforce monotonic progression on fault transition
- fail validation when ordering diverges

## Key APIs

- `fault_epoch(...)`
- `compare_headers(...)`
- `validate_monotonic_order_under_fault(...)`
- `reconcile_fault_path(...)`

## Test Coverage

`src/network_tests.ds` validates fault-path ordering for all implemented fault codes.
