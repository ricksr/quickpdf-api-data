# Quick PDF Tools — API open data

[![OpenAPI 3.1](https://img.shields.io/badge/OpenAPI-3.1-green)](openapi.yaml)
[![License: CC0-1.0](https://img.shields.io/badge/License-CC0%201.0-lightgrey.svg)](LICENSE)

Public **CC0** metadata and sample files for the [Quick PDF Tools](https://quickpdftools.net) **REST API v1** (server-side PDF **protect**, **unlock**, **repair**).

| | |
|---|---|
| **Human docs & API keys** | https://quickpdftools.net/developers/ |
| **Blog walkthrough** | https://quickpdftools.net/blog/quick-pdf-tools-api-protect-unlock-repair/ |
| **Live capabilities** (no key) | `GET https://api.quickpdftools.net/api/v1/capabilities` |
| **OpenAPI (live)** | https://quickpdftools.net/developers/openapi.yaml |

**This repo does not include API keys.** Sign in and create a key on the developer portal.

## Contents

| File | Description |
|------|-------------|
| `manifest.json` | Index of assets + production URLs |
| `openapi.yaml` | OpenAPI 3.1 spec (mirror of live) |
| `error-codes.json` | Stable error `code` values |
| `rate-limits.json` | Documented limits |
| `capabilities.snapshot.json` | Example capability catalog at publish time |
| `postman-collection.json` | Postman / Insomnia import |
| `fixtures/` | Sample PDFs (locked, damaged, multi-page) |

## Quick start

```bash
# Capabilities (public)
curl -sS https://api.quickpdftools.net/api/v1/capabilities | jq .operations[].id

# Protect (requires API key from developer portal)
curl -sS -X POST "https://api.quickpdftools.net/api/v1/pdf/protect" \
  -H "Authorization: Bearer qpdf_live_YOUR_KEY" \
  -F "file=@fixtures/single.pdf" \
  -F "password=YourPassword8" \
  -o protected.pdf
```

## Discoverability

- [Developer portal](https://quickpdftools.net/developers/) · [Blog](https://quickpdftools.net/blog/quick-pdf-tools-api-protect-unlock-repair/)
- Public APIs list — search “Quick PDF Tools API” on [publicapis.dev](https://publicapis.dev/)
- APIs.guru — OpenAPI directory (see [openapi-directory issues](https://github.com/APIs-guru/openapi-directory/issues))

## License

CC0 1.0 — see [LICENSE](./LICENSE).
