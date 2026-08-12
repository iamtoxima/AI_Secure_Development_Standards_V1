# Nigeria Consumer Protection Baseline

Verified against Federal Competition & Consumer Protection Commission sources:
2026-08-12

Primary general framework: Federal Competition and Consumer Protection Act
(FCCPA) 2018 and current FCCPC regulations/guidance.

## Engineering/Product Controls

For consumer-facing products, design so that:

- prices, fees, material limitations, renewal/subscription terms, and key product
  behavior are not misleading;
- the UI does not falsely report success, payment, delivery, refund, or account
  state;
- error/retry behavior does not manipulate users into duplicate purchase/action;
- material terms are accessible before commitment;
- support/complaint/redress channels can be documented and operated;
- marketing claims reflect actual product capability;
- users are not forced through deceptive or exploitative interaction patterns.

## Change Rule

When pricing, fees, subscriptions, refund behavior, delivery promises, or
marketing claims change:

- update product requirements;
- update consumer-facing copy;
- update terms/policies;
- update payment/refund state logic;
- update app-store metadata where affected;
- update tests for misleading/incorrect state.

## Sector Rules

Consumer law may be supplemented by sector-specific regulation.

Do not infer that the general FCCPA baseline is the only applicable rule for:

- lending;
- payments;
- telecom;
- health;
- insurance;
- other regulated sectors.

## Official Sources

- https://fccpc.gov.ng/about-us/our-mandate/
- https://fccpc.gov.ng/businesses/business-obligations/
- https://fccpc.gov.ng/resources-library/regulations/
- https://fccpc.gov.ng/resources-library/guidelines/
