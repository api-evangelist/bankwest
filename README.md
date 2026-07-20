# Bankwest (bankwest)

Bankwest is an Australian retail and business bank headquartered in Perth, Western Australia. Founded in 1895 as the Agricultural Bank of Western Australia (later the Bank of Western Australia), it has been a wholly owned subsidiary of Commonwealth Bank of Australia (CBA) since December 2008. In March 2024 Bankwest announced it would close its remaining branches and operate as a digital-only bank under the Bankwest brand. Under Australia's Consumer Data Right (CDR / Open Banking) regime, Bankwest exposes a public, unauthenticated Product Reference Data (PRD) API conforming to the Data Standards Body Consumer Data Standards.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/bankwest/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/bankwest/refs/heads/main/apis.yml)

## Tags

- Financial
- Banks
- Open Banking
- CDR
- Consumer Banking
- Australia
- Product Reference Data
- Digital Bank

## Timestamps

- **Created:** 2026-07-20
- **Modified:** 2026-07-20

## APIs

### Bankwest CDR Product Reference Data API

Public, unauthenticated Product Reference Data (PRD) API returning the features, rates, fees and eligibility for Bankwest's publicly offered banking products (transaction and savings accounts, term deposits, credit cards, personal loans and home loans). Confirmed live at HTTP 200 with `x-v: 5`, returning 19 products. Conforms to the DSB Consumer Data Standards CDS-AU/v1 banking schema; `GET /banking/products` and `GET /banking/products/{productId}` require the `x-v` version header (v4 and v5 supported).

- **Human URL:** [https://www.bankwest.com.au/support/open-banking/developers](https://www.bankwest.com.au/support/open-banking/developers)
- **Base URL:** `https://open-api.bankwest.com.au/bwpublic/cds-au/v1/banking/products`

#### Tags

- CDR
- Open Banking
- Product Reference Data
- Banking
- Public API

#### Properties

- [Documentation](https://www.bankwest.com.au/support/open-banking/developers)
- [API Reference](https://consumerdatastandardsaustralia.github.io/standards/#cdr-banking-api_get-products)
- [OpenAPI](openapi/bankwest-cds-banking-products-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

## Common Properties

- [Website](https://www.bankwest.com.au/)
- [Developer Portal](https://www.bankwest.com.au/support/open-banking/developers)
- [Documentation](https://www.bankwest.com.au/support/open-banking)
- [API Reference](https://consumerdatastandardsaustralia.github.io/standards/#cdr-banking-apis)
- [LinkedIn](https://www.linkedin.com/company/bankwest)
- [Privacy Policy](https://www.bankwest.com.au/legal-stuff/bankwest-privacy-statement)
- [Support](https://www.bankwest.com.au/support)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
