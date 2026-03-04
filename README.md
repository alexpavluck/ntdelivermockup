# NTD Donated Medicines — PO Chatbot Demo

An interactive browser-based chatbot for querying NTD (Neglected Tropical Diseases) donated medicine purchase order data. Covers **1,721 purchase orders** across **105 countries**, **5 donors**, and **6 drug types** from 2014–2027.

## Files

| File | Description |
|---|---|
| `ntd_chatbot_demo.html` | Self-contained interactive chatbot demo (open in browser) |
| `ntd_summaries.json` | Pre-computed aggregation summaries by drug, donor, country, and year |
| `ntd_chatbot_system_prompt.md` | System prompt for wiring this up to the Claude API |

## How to Use the Demo

1. Open `ntd_chatbot_demo.html` in any modern browser (Chrome, Firefox, Safari)
2. Type a natural language query in the input box, or click any of the pre-built query chips
3. Results are returned as a summary card + detail table

### Example Queries

- `GSK summary` — stats for GSK across all countries
- `Which countries does Eisai support?` — full country list sorted by volume
- `Praziquantel in Nigeria` — filtered PO list + summary
- `Show POs in transit` — all currently in-transit shipments
- `Tanzania` — full country drill-down with all POs
- `J&J 2022` — J&J purchase orders for programme year 2022
- `What has Merck donated?` — handled with disambiguation prompt

## Drugs Covered

| Code | Drug | Donor |
|---|---|---|
| ALB | Albendazole | GSK |
| DEC | Diethylcarbamazine | Eisai |
| IVM | Ivermectin | Merck USA |
| MEB | Mebendazole | J&J |
| PZQ | Praziquantel | Merck KGaA |
| TCZ | Triclabendazole | Merck USA |

## Connecting to the Claude API

Use `ntd_chatbot_system_prompt.md` as the system prompt. The prompt documents:
- Full database schema (SQLite `ntd_purchase_orders.db`)
- Pre-built SQL views for all common query patterns
- Example queries with corresponding SQL
- Drug/donor synonym handling
- Pipeline stage reference

---
*Data covers NTD donated medicine programme, 2014–2027*
