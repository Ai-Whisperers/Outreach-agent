# Pricing

Audience: **internal team**. Client-ready quotations live in the market subfolders.

## Folder layout

```
Pricing/
├── Europe/              ← € EUR — AI consulting rates (NL / EU clients)
│   ├── Quotation – Mark – De Vastgoedbegeleider.md
│   └── Quotation – Wesley van de Camp.md
├── Paraguay/            ← Gs. — local-market pricing (PY SMB clients)
│   ├── Quotation – Bichos Gym.md
│   ├── Quotation – Cerveza Trentina (B2B Paraguay).md
│   ├── Quotation – Cocodrilo Fitness.md
│   ├── Quotation – Magnolia Peluquería.md
│   ├── Quotation – Mantra Spa.md
│   └── Quotation – Pitchy Glass (Paraguay construction).md
├── Pricing Table – Lead Pipeline Overview.md   ← consolidated bands + lead table
└── README.md
```

## Pricing philosophy

| Market | Currency | Approach |
|--------|----------|----------|
| **Europe** | EUR (€) | Value-based AI consulting. Project fees + optional retainer. Competes with NL agencies (€1.5K–75K). |
| **Paraguay** | Gs. | Monthly subscription model. Entry-level website Gs. 150K/mes. Setup fees for implementation. |

## Conventions

- **Language:** Europe files in English (client-facing). Paraguay files in Spanish (client-facing).
- **Rate source:** Market benchmarks (2026) + internal estimates. No closed deals yet to validate.
- **Versioning:** When numbers change, add date suffix or short changelog at top of file.
- **Secrets:** Do not store API keys, bank details, or signed PDFs. See vault/CRM for ultra-sensitive data.

## Related

- Lead briefings capture **signals** and **hypotheses**: [`Leads/`](../Leads/README.md)
- After a number is agreed, CRM remains the legal source of truth; this folder is for prep and consistency.
