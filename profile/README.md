# Secure and Privacy-Preserving Credentials for E-ID

This organization holds the public results of the Innosuisse grant 101.292 IP-ICT
_Secure and Privacy-Preserving Credentials for E-ID_, a collaboration between
[EPFL/C4DT](https://c4dt.epfl.ch) and [SICPA](https://www.sicpa.com/expertise/identity/digital-identity).

The project explored how zero-knowledge proofs (ZKP) can add unlinkability,
selective disclosure, and holder binding to the Swiss e-ID (SWIYU) and similar
SD-JWT / ECDSA-P256 based credential systems, running on a phone.

⚠️ All code here is research / demo code. It is not meant for production use.

## Documentation

| Repository | Content |
| --- | --- |
| [eid-privacy.github.io](https://github.com/eid-privacy/eid-privacy.github.io) | Technical blog of the project: [eid-privacy.github.io](https://eid-privacy.github.io/). |
| [zkp-vault](https://github.com/eid-privacy/zkp-vault) | Knowledge vault on ZKP papers, proof systems, primitives, and tooling. Rendered at [eid-privacy.github.io/zkp-vault](https://eid-privacy.github.io/zkp-vault/). |
| [zkp-reports](https://github.com/eid-privacy/zkp-reports) | Grant reports (MS2, final MS4), the [Taxonomy of Digital Identity Systems](https://github.com/eid-privacy/zkp-reports/releases/download/latest/taxonomy-eid-paper.pdf) draft paper (first part of a "Systematization of Knowledge" paper on e-ID), and the zkSecurity security review. Report PDFs in the [latest release](https://github.com/eid-privacy/zkp-reports/releases/tag/latest). |

## Our Code

| Repository | Content |
| --- | --- |
| [spartan-backend](https://github.com/eid-privacy/spartan-backend) | Spartan backend for Noir, with the e-ID circuits (SD-JWT verification, ECDSA-P256 holder binding over Tom-256). |
| [zkp-pocs](https://github.com/eid-privacy/zkp-pocs) | Proofs of concept for privacy-preserving e-ID: BBS + Bulletproofs (docknetwork/crypto) and Noir/UltraHONK circuits, with benchmarks. |
| [zkp-android](https://github.com/eid-privacy/zkp-android) | Android app generating and verifying Noir proofs (UltraHONK via mopro) on the phone. |
| [zkp-android-spartan](https://github.com/eid-privacy/zkp-android-spartan) | Android app benchmarking proof generation and verification with the Spartan backend. |
| [ark-tom256](https://github.com/eid-privacy/ark-tom256) | The Tom-256 curve for arkworks, whose order equals the base field of P-256. |
| [knowledge-graph](https://github.com/eid-privacy/knowledge-graph) | Python tool building a citation knowledge graph of ZKP papers from CrossRef and OpenCitations. |
| [flakes](https://github.com/eid-privacy/flakes) | Nix flakes (with a Cachix binary cache) for pinned Noir, Barretenberg, and `nargo-t256` versions, usable from devbox. |
| [SWIYU-Demo](https://github.com/eid-privacy/SWIYU-Demo) | Issuer / verifier proof of concept on top of the SWIYU infrastructure. |

## Forked and Modified

| Repository | Content |
| --- | --- |
| [noir](https://github.com/eid-privacy/noir/tree/tom-256) | Fork of [noir-lang/noir](https://github.com/noir-lang/noir). The `tom-256` branch adds the Tom-256 / P-256 support used by `spartan-backend` (`nargo-t256`). |
| [vega-prover](https://github.com/eid-privacy/vega-prover/tree/raw-serde) | Fork of [microsoft/vega-prover](https://github.com/microsoft/vega-prover). The `raw-serde` branch stores the precomputed prover state as zstd-framed raw memory, so it loads ~5x faster in `spartan-backend`. |
