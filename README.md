# Shareworks

Shareworks by Morgan Stanley is an equity compensation management platform providing REST APIs for managing stock option plans, RSU grants, ESPP, and employee equity administration for public and private companies.

## Overview

The Shareworks Public API is organized around REST with predictable resource-oriented URLs, JSON-encoded responses, and standard HTTP response codes. The platform serves both private and public companies across all stages of maturity, and together with Equity Edge Online (EEO), Morgan Stanley at Work serves roughly 40% of the S&P 500.

## API Access

API access requires initial setup with Morgan Stanley at Work including:
- IP whitelisting of API client machines
- Client ID and Secret Key provisioned via admin portal
- RSA 2048-bit key pair generation

Authentication uses JWT bearer tokens with RS256 signing, valid for 90 minutes (5400 seconds).

## Environments

| Environment | Base URL |
|---|---|
| Development | `https://sum-qa02.shareworks.com/` |
| Production | `https://shareworks-api.solium.com/` |

## Rate Limits

| Request Type | Burst Threshold | Sustained Threshold |
|---|---|---|
| Non-POST (read) | 18 req / 5 seconds | 12 req / 2 minutes |
| POST (write) | 5 req / 5 seconds | 3 req / 2 minutes |

HTTP 429 is returned when limits are exceeded.

## Resources

- [API Documentation](https://downloads.shareworks.com/api/index.html)
- [Morgan Stanley at Work - Shareworks](https://www.morganstanley.com/atwork/shareworks)
- [Support Portal](https://support.solium.com/hc/en-us)
- [LinkedIn - Morgan Stanley at Work](https://www.linkedin.com/company/morgan-stanley-at-work)

## Repository Structure

```
shareworks/
  apis.yml                              # APIs.json index
  plans/
    shareworks-plans-pricing.yml        # API Commons Plans 0.1
  rate-limits/
    shareworks-rate-limits.yml          # API Commons Rate Limits 0.1
  finops/
    shareworks-finops.yml               # FinOps Framework 1.0
```

## Maintainer

Kin Lane - kin@apievangelist.com
