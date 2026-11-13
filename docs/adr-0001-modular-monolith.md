# ADR 0001 — Start with a modular monolith (illustrative)

**Status:** Example / not an actual project decision  
**Date:** 2026-11-13

## Context

We are designing an illustrative B2B order-management product. A small team will own order, inventory, account, and notification features. Individual services do not yet require independent deployment. Integration reliability, authorization, and correct business transactions are important.

## Options considered

1. **Unstructured monolith:** Simpler initial implementation, but blurred boundaries make future change difficult.
2. **Modular monolith:** One deployable application with explicit business modules and tested dependency boundaries.
3. **Microservices from day one:** Independent deployment and scaling opportunities, but increased operational and data-consistency complexity.

## Example decision

Choose a **modular monolith** initially. Define interfaces and business ownership between modules; keep integration-provider details in adapters. Evaluate service extraction later only when measurements or organizational requirements justify it.

## Consequences

**Benefits**
- Easier end-to-end testing and deployment for a small team.
- Local transactions can simplify consistency within one database boundary.
- Explicit modules preserve options for future restructuring.

**Costs and risks**
- Shared deployment and runtime failure domain.
- Boundaries may erode without code review and automated dependency checks.
- Some scaling requirements could eventually warrant separate components.

## Signals to revisit

- An independent deployment need becomes real and frequent.
- One workload has materially different operational requirements.
- Different teams can own stable service boundaries and their operations.
- Performance and reliability evidence demonstrates a benefit after accounting for distributed-systems costs.

## Validation

Create one end-to-end order workflow, test module dependencies, simulate a provider timeout, and verify permission checks, idempotency, and observable retry behavior.
