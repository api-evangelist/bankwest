---
name: Get Bankwest product detail
description: Fetch full detail for a single Bankwest banking product by productId, including rates, fees, features, constraints and eligibility.
api: openapi/bankwest-cds-banking-products-openapi.yml
operations: [getBankingProductDetail]
---

# Get Bankwest product detail

Public and unauthenticated, like the list endpoint. Use this after you have a
`productId` from `listBankingProducts`.

## Endpoint

`GET https://open-api.bankwest.com.au/bwpublic/cds-au/v1/banking/products/{productId}`
(operation `getBankingProductDetail`)

## Required header

- `x-v: 7` — product detail is at payload version 7. Mandatory; an unsupported
  value returns `406` (Header/UnsupportedVersion).

## Path parameter

- `productId` — an ASCII string returned by the product list endpoint.

## Steps

1. Send the GET request to `/banking/products/{productId}` with `x-v: 7`.
2. Parse `data` (a `BankingProductDetailV7`) for the nested collections:
   `features`, `constraints`, `eligibility`, `fees` (each fee may carry
   `discounts`), `depositRates`, `lendingRates` (each rate may carry tiered
   `applicabilityConditions`), and `bundles`.
3. A missing or unknown `productId` returns `404` (Resource/NotFound); a malformed
   id returns `404` (Resource/Invalid).

## Notes

- Read-only: there are no write operations and no idempotency contract on this API.
- Entity relationships are mapped in `data-model/bankwest-data-model.yml`.
