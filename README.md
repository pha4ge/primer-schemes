# Primer-schemes

A collection of primer scheme definitions for sequencing viral pathogens. A definition minimally comprises a reference sequence (`reference.fasta`), YAML metadata (`info.yaml`), and a Primal Scheme-like BED file describing primer sequences and their positions in reference coordinates (`primer.bed`). Each scheme is assigned an identifier consisting of the scheme family and version, e.g. `artic-v4.1`, `midnight-v2`. Checksums of primer and reference sequence composition are generated at build time and added to `scheme.yaml`.

Use [Primaschema](https://github.com/pha4ge/primaschema) to build primer scheme bundles from a `info.yaml`, `reference.fasta` and a 7 column `primer.bed` file.

*The schema definition format has not been finalised and should be considered unstable until initial release. Thereafter the `schema_version` will be incremented by any further changes.*



## Supported schemes

### SARS-CoV-2

 - `artic-v1`
 - `artic-v2`
 - `artic-v3`
 - `artic-v4`
 - `artic-v4.1`
 - `artic-v5.0.0_400`
 - `artic-v5.1.0_400`
 - `artic-v5.2.0_1200`
 - `artic-v5.2.0_400`
 - `midnight-bccdc-v1`
 - `midnight-bccdc-v2`
 - `midnight-bccdc-v3`
 - `midnight-bccdc-v4`
 - `midnight-ont-v3`
 - `varskip-vsl1a`
 - `varskip-vss1a`
 - `varskip-vss2a`
 - `varskip-vss2b`

### MPXV

- `yale-v3`



## Contributing

Pull requests containing new schemes or modifications to existing schemes are encouraged! We wish to make contributing new schemes as easy as possible and are working on UI to simplifty submissions.

