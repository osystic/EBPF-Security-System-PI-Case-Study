# Technical Overview

## System objective

Provide lightweight Linux endpoint visibility and controlled policy response on Raspberry Pi 5 / ARM64 while keeping the kernel-space collector small and moving filtering, classification, JSON handling, policy evaluation, and response logic into user space.

## Public architecture summary

```text
Linux tracepoints
  -> eBPF programs
  -> BPF ring buffer
  -> C++17 loader/event processor
  -> filtering + severity classification
  -> rotating local JSON Lines telemetry
  -> optional outbound HTTP JSON forwarding
  -> process-policy evaluation
  -> protected-process safeguards
  -> controlled userspace enforcement
  -> enforcement audit trail
```

## Publicly supportable capabilities

- process execution/lifecycle telemetry
- file/syscall activity telemetry
- IPv4 connect activity
- privilege-change signals
- ring-buffer event delivery
- noise suppression and rate controls
- structured severity mapping
- rotating JSON telemetry
- optional outbound HTTP forwarding
- reviewed alert/controlled-terminate policies
- protected-process safeguards
- enforcement audit logging
- local validated command-ingestion bridge with dry-run behavior

## Boundary

The public showcase contains architecture and evidence only. It intentionally excludes source code, operational configurations, client context, production endpoints, credentials, and private delivery history.
