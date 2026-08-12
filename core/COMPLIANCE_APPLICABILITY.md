# Compliance Applicability

External policy is selected based on the project, not loaded indiscriminately.

## Determine Applicability From

- application/platform type;
- app distribution channels;
- countries/regions where users are located;
- countries/regions where the business operates;
- personal/sensitive data processed;
- product/business model;
- payment model;
- regulated financial activity;
- external providers;
- user-generated content;
- messaging/social functionality;
- AI/LLM capability;
- age/children audience;
- health/financial/identity/KYC data;
- permissions and device capabilities;
- physical vs digital goods/services.

## Examples

### Android app accepting payment

Determine first whether the purchase is:

- a physical good/service;
- a digital good/service;
- peer-to-peer;
- another policy category.

Do not assume an external gateway is allowed simply because the integration
works technically.

### Nigerian marketplace using Paystack

Likely policy layers include:

- universal payment security;
- current Paystack requirements;
- Google Play and/or Apple policy if distributed through their stores;
- Nigeria data protection/consumer requirements;
- CBN analysis only if the product itself conducts an activity that may be
  regulated as a payment service rather than merely acting as a merchant.

### Digital lending application in Nigeria

In addition to general privacy/consumer controls, determine applicability of
current FCCPC digital lending regulation and other financial-sector rules.

## Output

Record the resolved policy set in the project profile or policy register.

Classify each external policy as:

- Applicable
- Potentially applicable — human review required
- Not applicable
- Deferred
- Current verification required
