# Clarity Ingredient Safety API

[![4M+ products](https://img.shields.io/badge/products-4M%2B-0D9E8F)](https://www.healthai.com/clarity/api)
[![25+ safety dimensions](https://img.shields.io/badge/safety%20dimensions-25%2B-0D9E8F)](https://www.healthai.com/clarity/api)
[![Published DOIs](https://img.shields.io/badge/methodology-published%20DOIs-091509)](https://doi.org/10.5281/zenodo.19423468)
[![9 languages](https://img.shields.io/badge/languages-9-C4A24E)](https://www.healthai.com/clarity/api)

Clarity is a research-backed ingredient safety API built by [Health AI](https://www.healthai.com).

Scan **4M+ products** across food, supplements, skincare, and medications. Every ingredient is evidence-graded across **25+ safety dimensions** for breastfeeding, pregnancy, histamine intolerance, MCAS, rosacea, HS, allergies, fertility, and more.

Published methodology with DOIs. Database-first architecture. Same question, same answer, every time.

## What It Does

- Check a single ingredient for evidence-graded safety signals
- Scan a product barcode and return ingredient-level safety context
- Support multilingual ingredient lookup and fuzzy matching
- Cover maternal health, inflammatory conditions, allergens, and consumer product safety in one API

## Quick Start

### POST `/api/check`

```bash
curl -X POST https://clarity-mu-green.vercel.app/api/check \
  -H "Content-Type: application/json" \
  -d '{"q":"fenugreek"}'
```

### GET `/api/scan`

```bash
curl "https://clarity-mu-green.vercel.app/api/scan?barcode=0016000264601&mode=lactation"
```

## Use Cases

- Pregnancy and breastfeeding apps
- Nutrition and wellness platforms
- Allergy and intolerance tools
- Dermatology and inflammatory-condition products
- Barcode scanning and product-safety workflows
- Clinical and research support tools

## Published Methodology

- [Clarity Methodology](https://doi.org/10.5281/zenodo.19423468)
- [Beta-Glucan as a Galactagogue](https://doi.org/10.5281/zenodo.19389747)
- [CMPA Formula Comparative Analysis](https://doi.org/10.5281/zenodo.19391415)

## Docs

- [API page](https://www.healthai.com/clarity/api)
- [Methodology](https://www.healthai.com/clarity/about)
- [RapidAPI listing](https://rapidapi.com/ClarityHealthAI/api/clarity-ingredient-safety)
- [OpenAPI spec](./openapi-spec.json)

## Built By

**[Health AI](https://www.healthai.com)** - Olga Lavinda, PhD  
NIH NRSA Fellow - Farber Award, Society for Investigative Dermatology  
[ORCID](https://orcid.org/0000-0003-3577-5984) - [Google Scholar](https://scholar.google.com/citations?user=xJULhsYAAAAJ)

## License

API access is subject to [terms of service](https://www.healthai.com/privacy-policy). The database methodology is published and auditable. Data is proprietary to Health AI LLC.
