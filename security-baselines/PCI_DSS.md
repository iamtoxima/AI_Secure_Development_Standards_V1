# PCI DSS Applicability Baseline

Verified: 2026-08-12

At the verification date, PCI Security Standards Council lists PCI DSS v4.0.1
as the current PCI DSS publication.

## Applicability First

Do not force the complete PCI DSS standard into every project that uses a
payment gateway.

Determine whether the application's architecture stores, processes, or
transmits cardholder data or otherwise places systems in PCI scope.

Prefer architectures that reduce exposure to cardholder data through
provider-hosted/tokenized payment experiences where appropriate.

## AI Rule

Do not claim:

- "PCI compliant";
- "SAQ X applies";
- "out of PCI scope";

without evidence and the required organizational/payment-flow analysis.

If cardholder-data scope may exist:

1. map the card-data flow;
2. identify every system/provider that handles it;
3. verify the current PCI DSS version and applicable validation approach;
4. obtain appropriate PCI/compliance expertise.

## Official Source

- https://www.pcisecuritystandards.org/document_library/
