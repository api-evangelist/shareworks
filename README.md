# Shareworks

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
