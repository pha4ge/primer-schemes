[![Tests](https://github.com/pha4ge/primer-schemes/actions/workflows/test.yml/badge.svg)](https://github.com/pha4ge/primer-schemes/actions/workflows/test.yml)

# Primer schemes

A versioned and schematised repository of tiling amplicon PCR primer scheme definitions (created with e.g. [Primal Scheme](https://primalscheme.com)) for pathogen sequencing, made with the objective of eliminating ambiguity in scheme naming and versioning in order to facilitate accurate analysis and reuse of amplicon sequence data.



## Scheme specification

A scheme definition has three components:

1.  A reference sequence ([`reference.fasta`](https://github.com/pha4ge/primer-schemes/blob/main/sars-cov-2/artic/v4.1/reference.fasta))
2.  A seven column BED file of primer sequences & positions in reference coordinates ([`primer.bed`](https://github.com/pha4ge/primer-schemes/blob/main/sars-cov-2/artic/v4.1/primer.bed))
3.  A metadata file in YAML format adhering to [this schema](https://github.com/pha4ge/primer-schemes/blob/main/schema/primer_scheme.yml) ([`info.yml`](https://github.com/pha4ge/primer-schemes/blob/main/sars-cov-2/artic/v4.1/info.yml))



## Contributing new schemes

We welcome contributions of new primer schemes! We're working to make this process easier, but in the meantime please either follow the instructions below and create a pull request, or else [open a GitHub issue](https://github.com/pha4ge/primer-schemes/issues) attaching or linking to a BED file so that we can help.

### Instructions

1. Choose an appropriate scheme name, e.g. `schemename-v1`, where `v1` indicates the version of the scheme. Avoid including the organism name in the scheme name if possible.

2. Create a directory named `schemename-v1` containing a text file `info.yml` containing:
   ```yaml
   schema_version: 0.9.0
   name: schemename-v1
   organism: sars-cov-2
   developers:
   - person_name: Jane Doe
     orcid: 1234-5678-9876-5432
   amplicon_size: 1200
   repository_url: https://github.com/pha4ge/primer-schemes/tree/main/sars-cov-2/schemename/v1
   ```
   
3. Copy your scheme's BED file into this directory, naming it `primer.bed`

4. Copy your scheme's reference sequence into this directory, naming it `reference.fasta` 
5. Optionally run `primaschema build schemename-v1/` to create a finished scheme bundle  

5. Either **open a pull request** adding your scheme directory (e.g. inside `sars-cov-2/schemename/v1`), or else **open a GitHub issue** attaching a zip file containing your scheme.



## Tooling

The companion tool [Primaschema](https://github.com/pha4ge/primaschema) can be used to validate scheme definitions and automatically checks and updates this repository via GitHub Actions. Primaschema adds primer and reference sequence checksums to `info.yml` at build time to help catch identical primer schemes. A six column scheme.bed file is also generated at build time for legacy compatibility.



## Documented schemes (24)

### SARS-CoV-2 (22)

 - `artic-v1`
 - `artic-v2`
 - `artic-v3`
 - `artic-v4`
 - `artic-v4.1`
 - `artic-v5.0.0_400`
 - `artic-v5.1.0_400`
 - `artic-v5.2.0_1200`
 - `artic-v5.2.0_400`
 - `artic-v5.3.2_400`
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

### NiV (1)

- `nipah-v1`
