<!-- SPDX-License-Identifier: Apache-2.0 -->

# Compatibility

Version 1.0.3 requires Python 3.12 or newer. Its installation requirements are
`meridian-storage-core>=1,<2` and
`meridian-storage-semantics>=2,<3`.

Core's V1 Expression, Operation, ResourceRef, Catalog provider/discovery,
CapabilityRequirement and error APIs are the consumed boundary. The lower
bound retains the Core 1.0.1 baseline previously tested with Object Common
1.0.2; Core 1.1.0 preserves those APIs. Semantics supplies the V2 Catalog,
Schema, Object metadata/reference/profile and canonical JSON APIs. Semantics
2.0.1 is the first V2 repair that admits Core 1.1.0 through normal dependency
resolution. Its predecessor 2.0.0 pinned Core 1.0.1 exactly. Major upper bounds
exclude unreviewed breaking API families. These are package API constraints,
not a promise that every future release has passed conformance.

`requirements-validation.txt` locks the complete runtime dependency closure to
public Core 1.1.0 and Semantics 2.0.1 with wheel and sdist SHA-256 values.
`compatibility.json` records those artifacts and their release commits. Its
version fields and the public API ledger's `core`/`semantics` fields describe
this tested recipe, not runtime release membership predicates. The `design`
field retains the historical contract baseline; the approved compatibility
repair is linked from the Feishu Object design. Deployment owners select their
own exact artifact locks and verify their integrity independently.

CI tests Core 1.0.1 and 1.1.0, each with Semantics 2.0.1, on Python 3.12–3.14.
Release validation installs the hashed runtime lock, normally resolves the
built wheel and its test extra, runs `pip check`, and runs the full regression
suite against installed wheel code with pytest's source-path injection disabled.
No dependency overrides, no-deps installs or sibling source are used.

The Object Catalog and all eight Operation contracts remain version `1.0.0`.
Payload tokens, digest verification, immutable identity, conditional creation,
wire schemas, logical references and shared S3/OCI conformance fixtures remain
unchanged. No data migration is needed: update the deployment's dependency lock
and its selected artifact/configuration fingerprints. Preserve capability,
physical Schema, placement and drift checks; release equality alone is not
behavioral compatibility evidence.

This provider-neutral package has no real storage engine gate. Its in-memory
conformance target validates the shared adapter fixtures; S3/OCI engine and
ConfigArtifact integration remain acceptance of their owning downstream
packages. Untested combinations remain unverified.

Changes to serialized fields, exact method membership, stable error codes,
public exports, operation guarantees or capability names require a versioned
contract update and approved design write-back.
