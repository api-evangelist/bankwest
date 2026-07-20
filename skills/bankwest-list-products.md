---
name: List Bankwest banking products
description: Retrieve Bankwest's publicly offered banking products via the CDR Product Reference Data API, with filtering and pagination.
api: openapi/bankwest-cds-banking-products-openapi.yml
operations: [listBankingProducts]
---

# List Bankwest banking products

Bankwest's Product Reference Data (PRD) API is **public and unauthenticated** — no
API key, token, or accreditation is needed to read product data.

## Endpoint

`GET https://open-api.bankwest.com.au/bwpublic/cds-au/v1/banking/products`
(operation `listBankingProducts`)

## Required header

- `x-v: 5` — the payload version. This header is **mandatory**. Omitting it returns
  `400` (Header/Missing); an unsupported value returns `406`
  (Header/UnsupportedVersion). Supported versions are 4 and 5.

## Optional query parameters

- `effective` — `CURRENT` (default), `FUTURE`, or `ALL`.
- `updated-since` — DateTimeString; only products updated after this time.
- `brand` — filter by brand.
- `product-category` — e.g. `TRANS_AND_SAVINGS_ACCOUNTS`, `TERM_DEPOSITS`,
  `CRED_AND_CHRG_CARDS`, `PERS_LOANS`, `RESIDENTIAL_MORTGAGES`.
- `page` (default 1) and `page-size` (default 25) — standard page pagination.

## Steps

1. Send the GET request with `x-v: 5`.
2. Read `data.products[]` for the product summaries and `meta.totalRecords` /
   `meta.totalPages` to size the result set.
3. If `meta.totalPages > 1`, follow `links.next` or increment `page` until done.
4. Capture each `productId` to fetch full detail (see the get-product-detail skill).

## Errors

Errors use the CDS-AU envelope: a top-level `errors[]` array of
`{code, title, detail}` where `code` is a `urn:au-cds:error:...` URN. See
`errors/bankwest-problem-types.yml`.
