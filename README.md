# Clarity Ingredient Safety API

[![1,500+ ingredients](https://img.shields.io/badge/ingredients-1%2C500%2B-0D9E8F)](https://www.healthai.com/clarity/api)
[![15 safety dimensions](https://img.shields.io/badge/dimensions-15-0D9E8F)](https://www.healthai.com/clarity/api)
[![Published DOIs](https://img.shields.io/badge/methodology-published%20DOIs-C4A24E)](https://doi.org/10.5281/zenodo.19389747)
[![Free tier](https://img.shields.io/badge/free%20tier-100%20lookups%2Fmo-091509)](https://www.healthai.com/clarity/api)

The only ingredient safety API built on **published research methodology with DOIs**. Evidence-graded for breastfeeding, pregnancy, toddler nutrition, histamine, DAO enzyme, CMPA, ADHD additives, heavy metals, blood pressure, and more.

## Quick Start

```bash
curl -X POST https://clarity-mu-green.vercel.app/api/check \
  -H "Content-Type: application/json" \
  -d '{"q": "fenugreek"}'
```

Response:
```json
{
  "ok": true,
  "query": "fenugreek",
  "result": {
    "name": "Fenugreek",
    "verdict": "Caution",
    "source_type": "Gold",
    "lactation_safety": "Caution — may increase milk supply but significant histamine and DAO concerns",
    "pregnancy_safety": "Avoid — uterine stimulant",
    "histamine": {
      "liberator": "Yes — triggers mast cell degranulation",
      "severity": "High"
    },
    "dao": {
      "inhibitor": "Yes",
      "severity": "Moderate"
    },
    "flags": {
      "cmpa_risk": false,
      "adhd_risk": false,
      "heavy_metal_risk": false
    }
  }
}
```

## What It Covers

Every ingredient is assessed across **15 safety dimensions**:

| Dimension | What You Get |
|---|---|
| **Lactation Safety** | Verdict + breast milk transfer risk |
| **Pregnancy Safety** | Trimester-specific cautions |
| **Toddler Safety** | ADHD additive flags, pediatric dose limits |
| **Histamine** | Liberator detection + severity rating |
| **DAO Enzyme** | Inhibitor status + mechanism |
| **CMPA** | Cow's milk cross-reactivity mapping |
| **Blood Pressure** | Hypotensive/hypertensive classification |
| **Heavy Metals** | Arsenic, lead, cadmium, mercury alerts |
| **Allergens** | FDA Big 9 classification |
| **Glycemic Index** | GI value + category |
| **Cycle Phase** | Menstrual cycle sensitivity |
| **Galactagogue** | Evidence vs folk tradition |
| **Interactions** | 28 clinically curated pairs |
| **Contaminants** | 174 brand-specific products |
| **FDA Recalls** | 103 tracked recalls |

## Database Stats

- **1,500+** validated ingredients
- **658** Gold-tier (primary source verified)
- **900+** PubMed citations
- **174** brand-specific contaminant products
- **103** FDA recalls tracked
- **18** infant formula profiles
- **9** languages supported

## Evidence Tiers

| Tier | Meaning |
|---|---|
| **Gold** | Cross-referenced against LactMed, InfantRisk, or MilkSafe with PubMed citations |
| **Silver** | PubMed confirmed but not cross-referenced to a primary lactation database |
| **Bronze** | Limited evidence. Never displayed as "Research-Backed" |

## Endpoints

### POST `/api/check` — Ingredient Lookup

Look up any ingredient by name, brand name, or alias. Supports 9 languages.

```bash
curl -X POST https://clarity-mu-green.vercel.app/api/check \
  -H "Content-Type: application/json" \
  -d '{"q": "retinol"}'
```

Alias matching works — try `"q": "accutane"`, `"q": "vaseline"`, `"q": "differin"`.

### GET `/api/scan` — Barcode Product Scan

Scan a product by UPC/EAN barcode. Returns per-ingredient safety verdicts.

```bash
curl "https://clarity-mu-green.vercel.app/api/scan?barcode=0016000264601"
```

## Pricing

| Plan | Price | Requests/Month |
|---|---|---|
| **Free** | $0 | 100 |
| **Pro** | $49/mo | 2,000 |
| **Ultra** | $199/mo | 10,000 |
| **Mega** | $499/mo | 50,000 |

[Subscribe →](https://www.healthai.com/clarity/api)

## Published Research

This API is backed by published methodology — not a black box:

- [Beta-Glucan as a Galactagogue](https://doi.org/10.5281/zenodo.19389747) — DOI: 10.5281/zenodo.19389747
- [CMPA Formula Comparative Analysis](https://doi.org/10.5281/zenodo.19391415) — DOI: 10.5281/zenodo.19391415

Data sourced from: NIH LactMed, InfantRisk, PubMed, DSLD, SIGHI, MilkSafe, DermNet.

## OpenAPI Spec

Full OpenAPI 3.0 specification: [`openapi-spec.json`](./openapi-spec.json)

## Built By

**[Health AI](https://www.healthai.com)** — Olga Lavinda, PhD
NIH NRSA Fellow · Farber Award, Society for Investigative Dermatology
[ORCID](https://orcid.org/0000-0003-3577-5984) · [Google Scholar](https://scholar.google.com/citations?user=xJULhsYAAAAJ)

## License

API access is subject to [terms of service](https://www.healthai.com/privacy-policy). The database methodology is published and auditable. Data is proprietary to Health AI LLC.
