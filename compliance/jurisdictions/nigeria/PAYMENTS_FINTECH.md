# Nigeria Payments and Fintech Applicability Baseline

Verified against Central Bank of Nigeria sources: 2026-08-12

This file is an applicability guide, not a licensing opinion.

## Merchant vs Regulated Payment Activity

A normal application using a licensed payment gateway to collect payment for its
own goods/services is not automatically equivalent to operating a licensed
payment-service business.

However, products involving capabilities such as:

- wallets/stored value;
- payment switching/processing;
- merchant acquiring;
- money transfer;
- payment service bank activity;
- open-banking service roles;
- mobile money;
- other regulated payment-system functions;

may trigger CBN licensing/regulatory analysis.

## AI Rule

Do not tell the user "you need a CBN licence" or "you do not need a CBN licence"
solely from a feature name.

Instead:

1. describe the actual funds flow;
2. identify who receives/holds/moves value;
3. identify whether the product acts as merchant, marketplace, intermediary,
   wallet, lender, processor, or another role;
4. identify provider licences/roles;
5. consult current CBN rules;
6. flag uncertain licensing/applicability questions for qualified Nigerian
   regulatory/legal review.

## Engineering Baseline

Regardless of licensing status:

- use licensed/approved providers appropriate to the product;
- verify gateway/provider status through current official sources when material;
- keep provider credentials server-side;
- design financial state for idempotency and reconciliation;
- preserve audit trails;
- segregate sandbox and production;
- do not let client-controlled provider selection determine privileged money
  flow without trusted server validation.

## Current CBN Context

CBN maintains current PSP licence listings and payment-system frameworks.
Payments System Vision 2028 was launched in 2026 and emphasizes security,
interoperability, inclusion, innovation, trust, and collaboration.

Treat strategic policy documents as context, not a substitute for binding
licensing/regulatory instruments.

## Official Sources

- https://www.cbn.gov.ng/PaymentsSystem/
- https://www.cbn.gov.ng/PaymentsSystem/PSPs.html
- https://www.cbn.gov.ng/PaymentsSystem/PSV2028.html
