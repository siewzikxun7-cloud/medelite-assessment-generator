# Medelite Facility Assessment Generator

A lightweight web app that generates Facility Assessment Snapshot reports using CMS nursing home data and manual MedElite inputs.

## Features

- Dynamic CCN lookup
- CMS Provider Data Catalog CSV lookup
- Facility name override
- Manual MedElite operational inputs
- Print-ready PDF export
- Medicare Care Compare hyperlink
- INFINITE — Managed by MEDELITE branding

## Test Case

Use CCN:

```text
686123
```

Expected facility:

```text
Kendall Lakes Healthcare and Rehab Center
```

## Tech Stack

- React
- Vite
- TypeScript
- jsPDF
- PapaParse

## CMS Data Source

The app uses the CMS Provider Data Catalog `data.json` catalog to locate the latest **Provider Information** CSV for nursing homes.

Catalog URL:

```text
https://data.cms.gov/provider-data/data.json
```

Dataset used:

```text
Provider Information
Identifier: 4pq5-n9py
```

## Local Setup

```bash
npm install
npm run dev
```

## Build

```bash
npm run build
```

## Deploy

Deploy to Vercel or Netlify as a Vite app.

## Notes / Assumptions

- CMS CSV data is fetched client-side from the public CMS Provider Data Catalog.
- If the live CMS file cannot be fetched because of browser/CORS/network limitations, the app includes a Kendall Lakes fallback record for the required test CCN `686123`.
- The PDF layout follows the provided Facility Assessment Snapshot reference.
- Hospitalization and ED metrics are included as optional manual / fallback report fields in this MVP.
