# Primer schemes

A versioned and schematised community repository of tiled amplicon primer scheme definitions (created with e.g. [Primal Scheme](https://primalscheme.com)) for pathogen sequencing, made with the objective of eliminating ambiguity in scheme naming and versioning and maximising the findability, accessibility, interoperability and reusability ([FAIRness](https://www.go-fair.org/fair-principles/)) of primer schemes and associated sequencing data. An example of a canonical primer scheme name is `artic-sars-cov-2/400/v4.1.0`.

The repository includes a top-level machine readable [index](https://github.com/pha4ge/primer-schemes/blob/main/index.json) of available primer scheme definitions.



## Scheme specification

A scheme definition has three components:

1.  A reference sequence (e.g. [`reference.fasta`](https://github.com/pha4ge/primer-schemes/blob/main/schemes/artic-sars-cov-2/400/v4.1.0/reference.fasta))
2.  A seven column Primal Scheme-like BED file of primer sequences & coordinates (e.g. [`primer.bed`](https://github.com/pha4ge/primer-schemes/blob/main/schemes/artic-sars-cov-2/400/v4.1.0/primer.bed)) that complies with the formatting specified in the [ARTIC primer scheme specification](https://github.com/artic-network/primerscheme-specs/blob/main/pdf/primerscheme.pdf)
3.  A metadata file in JSON format adhering to a [schema](https://github.com/pha4ge/primaschema/blob/main/src/primaschema/schema/info.yml) (e.g. [`info.json`](https://github.com/pha4ge/primer-schemes/blob/main/schemes/artic-sars-cov-2/400/v4.1.0/info.json))



## Tooling

The repository's companion tool [Primaschema](https://github.com/pha4ge/primaschema) is used to automatically validate schemes in this repository, create graphics and manage checksums. It may be installed standalone using `pip install` for fetching, validating and interrogating primer schemes.



## Contributing new scheme definitions

We encourage contributions of any schemes the others might wish to use, especially if sequencing data has been or will be deposited publicly. We're working to make this process easier, but in the meantime please either follow the instructions below to send us a draft scheme, or create a pull request using GitHub if comfortable doing so.

A scheme definition comprises *i)* a reference sequence (`reference.fasta`), *ii)* a BED file of primer sequences & reference coordinates (`primer.bed`), and *iii)*, a metadata file in JSON format adhering to [this schema](https://github.com/pha4ge/primaschema/blob/main/src/primaschema/schema/info.yml), called `info.json`. If you've created a scheme you probably already have i) and ii), and need to make `info.json`. It's easiest to begin by modifying a copy of an existing `info.json` [such as this one](https://github.com/pha4ge/primer-schemes/blob/main/schemes/eden/2500/v1.0.0/info.json).

1. Check that the `primer_scheme_target_organism` field in your scheme's `info.json` references the correct pathogen. If there are no existing schemes for the target pathogen, please [open a GitHub issue](https://github.com/pha4ge/primer-schemes/issues) to request it be added.
2. Choose a scheme name and version, e.g `midnight-sars-cov-2` and `v1.0.0`. The name should not include special characters except hyphens.
    - If adding a new scheme, choose any name.
    - If updating your existing scheme, keep the same name and update the version:
      - Versions must take the form `v{major}.{minor}.{patch}`, optionally followed by a hyphenated suffix
      - For primer changes beyond adding primers, increment the *major* version
      - If only adding primers with respect to an existing version, increment the *minor* version
      - For smaller technical changes, the *patch* version may be incremented
    - If updating a third party's existing scheme, you may propose a new scheme name with version `v1.0.0` rather than increment the existing scheme's version.
3. Complete the `primer_scheme_name` and `primer_scheme_version` fields inside your new scheme's `info.json`, along with the other required fields:
    - `schema_version`: the version of the metadata schema, currently `1.0.0-alpha`
    - `amplicon_size`: the approximate integer amplicon length in bp
    - `primer_scheme_contributor`: a list of contributor names or organisations
    - `primer_scheme_target_organism`: a list of target organisms
    - `primer_scheme_development_status`: one of `DRAFT`, `TESTED`, `VALIDATED` or `DEPRECATED`
4. [Open a GitHub issue](https://github.com/pha4ge/primer-schemes/issues) attaching or linking to your `reference.fasta`, `primer.bed` and `info.json` files.
5. If you wish, you may install [primaschema](https://github.com/pha4ge/primaschema) and run `primaschema rebuild --path {scheme-directory}/info.json` to normalise your newly created scheme and add checksums, then `primaschema validate --path {scheme-directory}/info.json` to check it. However this is not necessary.
