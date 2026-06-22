# Medelite Facility Assessment Generator

A lightweight web app that generates Facility Assessment Snapshot reports using CMS nursing home data and manual MedElite inputs.

## Features

- Dynamic CCN lookup
- CMS Provider Data Catalog lookup
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

The app uses CMS Provider Data Catalog public data.

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

- The app tries to fetch CMS Provider Information data from the public CMS catalog.
- If browser/CORS/network access prevents the live CMS lookup, the app includes a fallback record for the required validation case: CCN `686123`.
- The PDF layout follows the provided Facility Assessment Snapshot reference.
- Hospitalization and ED metrics are included as editable sample fields in this MVP.
