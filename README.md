# Primer-schemes

A versioned and schematised repository of tiling amplicon PCR primer scheme definitions (created with e.g. [Primal Scheme](https://primalscheme.com)) for pathogen sequencing, made with the objective of eliminating ambiguity in scheme naming and versioning in order to facilitate accurate analysis and reuse of amplicon sequence data.

A scheme definition has three components:

1.  A reference sequence ([`reference.fasta`](https://github.com/pha4ge/primer-schemes/blob/main/sars-cov-2/artic/v4.1/reference.fasta))
2. A seven column BED file of primer sequences & positions in reference coordinates ([`primer.bed`](https://github.com/pha4ge/primer-schemes/blob/main/sars-cov-2/artic/v4.1/primer.bed))
3. A metadata file in YAML format ([`info.yaml`](https://github.com/pha4ge/primer-schemes/blob/main/sars-cov-2/artic/v4.1/reference.fasta))

*The schema definition format should be considered unstable until initial release. Thereafter the `schema_version` will be incremented by any further changes.*



## Contributing

We welcome contributions of new primer schemes! We're working on making this process as simple as possible, but in the meantime please open a pull request adding your scheme's bed file into an appropriately named directory (e.g. `sars-cov-2/schemename-v1/primer.bed`) and we should be able to take care of the rest.



## Tooling

Checksums of primer and reference sequence composition are generated at build time (using [Primaschema](https://github.com/pha4ge/primaschema)) and added to `info.yaml` to help distinguish between similar and identical schemes. A six column scheme.bed file is also generated at build time for legacy tool compatibility.



## Documented schemes (22)

### SARS-CoV-2 (21)

 - `artic-v1`
 - `artic-v2`
 - `artic-v3`
 - `artic-v4`
 - `artic-v4.1`
 - `artic-v5.0.0_400`
 - `artic-v5.1.0_400`
 - `artic-v5.2.0_1200`
 - `artic-v5.2.0_400`
 - `eden-v1`
 - `midnight-bccdc-v1`
 - `midnight-bccdc-v2`
 - `midnight-bccdc-v3`
 - `midnight-bccdc-v4`
 - `midnight-ont-v3`
 - `midnight-v1`
 - `midnight-v2`
 - `varskip-vsl1a`
 - `varskip-vss1a`
 - `varskip-vss2a`
 - `varskip-vss2b`



### MPXV (1)

- `yale-v3`





