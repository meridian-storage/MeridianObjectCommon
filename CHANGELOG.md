<!-- SPDX-License-Identifier: Apache-2.0 -->

# Changelog

## 1.0.3 — 2026-09-08

- Replace historical exact dependency recipes with Core `>=1.0.1,<2` and
  Semantics `>=2.0.1,<3` public API compatibility bounds.
- Lock release validation to public Core 1.1.0 and Semantics 2.0.1 with artifact
  hashes; retain exact Object V1 APIs, payloads, fixtures and provider neutrality.
- Test both Core 1.0.1 and 1.1.0 on Python 3.12–3.14; require normal clean wheel
  installation, dependency checks and the full installed-wheel regression suite.

## 1.0.2

- Consume released Core 1.0.1 and Semantics 2.0.0 through exact dependency pins.
- Refresh compatibility evidence and CI clean-install inputs while preserving the
  Object V1 API, wire formats, streaming rules, and shared conformance fixtures.

## 1.0.1

- Generate signing nonces with an alphabet accepted by the existing opaque-token contract.

- Share default process-local payload handles between Object consumers and discovered Adapters; explicitly constructed registries remain isolated.


## 1.0.0 - 2026-08-25

- Publish the exact eight-method Meridian V1 Object Catalog surface and manifest.
- Add deterministic Core Operation normalization and provider-neutral capability requirements.
- Add bounded streaming payload references, SHA-256 content identity, ranges, and put state machine.
- Add multipart Adapter SPI, immutability and retention inputs, signed logical references, and stable errors.
- Add language-neutral contracts, fixtures, downstream Adapter conformance, CI, release, and packaging evidence.
