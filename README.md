# A repository to try out SKOS-vocabulary maintenance on GitHub

This repository was created from the template [voc4cat-template](https://github.com/nfdi4cat/voc4cat-template).

It uses the [voc4cat-tool](https://github.com/nfdi4cat/voc4cat-tool) and GitHub features like gh-actions, pull requests etc. to reduce the maintenance workload for contributors and editors.
The template is maintained as part of the [NFDI4Cat](http://www.nfdi4cat.org) initiative.

## How to start?

### Trying out the workflow

All vocabularies based on this template have the same standard contribution process of

- get and update the vocabulary file (xlsx),
- submit a pull request with the updated file,
- collaborate on the pull request with editors or other github users,
- approval and merge of the pull request

and finally land in the folder `vocabularies` as SKOS-vocabulary files in turtle-format.

The Excel/xlsx files submitted as pull request are automatically checked and (if all is good) converted to turtle.
By using a vocabulary-specific configuration more thorough validation can be activated,
e.g. if terms get removed in a PR or if correct IRIs are used.
To validate IRIs the configuration supports ID-ranges (similar to [OBO idrange](https://oboacademy.github.io/obook/howto/idrange/) but we use toml-format).
The idea is that every author gets their own range of IDs to consume.
This allows independent work and avoids using the same ID repeatedly.

In addition, HTML-documentation is created automatically and published on GitHub-pages.

- The general url is `https://{gh-org-name}.github.io/{repository-name}/{vocabulary-name}/`
- In repository `nfdi4cat/voc4cat-template` the vocabulary `vocab_example` is documented at [https://nfdi4cat.github.io/voc4cat-template/vocab_example/](https://nfdi4cat.github.io/voc4cat-template/vocab_example/)
 
### Creating vocabularies for catalysis or catalytic reaction engineering

Please strongly consider contributing to [voc4cat](https://github.com/nfdi4cat/voc4cat) instead of creating your own.

## Contributing to vocabularies

To contribute new concepts or collections or change existing ones, you may either submit your contributions as Excel/xlsx-file or (as an expert) as new/changed turtle file.

Here are the steps, for submitting updates in Excel including the git commands.

- Get the Excel/xlsx-vocabulary file
  - For an existing vocabulary, the latest version of the vocabulary is always available via github-pages.
    - The general url is `https://{gh-org-name}.github.io/{repository-name}/{vocabulary-name}.xlsx`
    - For example in nfdi4cat/voc4cat-template the vocabulary `vocab_example` can be downloaded from [https://nfdi4cat.github.io/voc4cat-template/vocab_example.xlsx](https://nfdi4cat.github.io/voc4cat-template/vocab_example.xlsx)
  - For setting up a new vocabulary, use the xlsx-file from the templates-folder.
- Make changes to the Excel file
- Add the xlsx file to your clone of the repository into the folder `inbox-excel-vocabs`
  - The name of the file must match the vocabulary that you want to update (e.g. myvoc.xlsx to update a vocabulary named "myvoc").
  - New vocabularies will be named like the xlsx-file (minus the `.xlsx`-extension).
- Create a pull request with the updated Excel-file on GitHub.
  - Please describe your changes and the motivation for the changes in the pull request note or link to an issue with this information. This will help reviewers to understand the proposed change and decide about it.
- Your pull request will be processed automatically by a CI/CD pipeline that typically runs less than a minute.
- Review the artifacts/logs generated by the CI pipeline.
  - The [workflow artifact](https://docs.github.com/en/actions/managing-workflow-runs/downloading-workflow-artifacts) will contain an updated xlsx file that is recreated from the updated turtle-file.
- If all is good your contribution will be either
  - directly merged by the maintainers
  - or a discussion will be started about what else is needed
  - or why the proposed change may not fit.
- If you need to fix something update the pull request branch. This will trigger the pipeline to run again.

Finally, when the proposed merge request is accepted, your changes will be integrated in the vocabularies in the folder `vocabularies`.

**The playground is configured to require one approval before a pull request can be merged.** So the complete contribution workflow inlcuding approval can be tested. Please create an issue if would prefer that we change this setting to no approval.

See [inbox-excel-vocabs/README.md](inbox-excel-vocabs/README.md) for a minimal example how to test the submission process.

## How to suggest improvements to the tooling & template?

To discuss about the workflow for maintaining SKOS vocabularies based on this template, create an [voc4cat-template issue](https://github.com/nfdi4cat/voc4cat-template/issues).

To discuss about the tool that converts Excel to SKOS in gh-actions of this template, create an [voc4cat-tool issue](https://github.com/nfdi4cat/voc4cat-tool/issues).


## Authors and acknowledgment

### Vocabularies

- *List all contributors.*

### Voc4cat template

- David Linke (ORCID: 0000-0002-5898-1820) - Initial setup of repository and CI/CD pipelines

## License

### Vocabularies

All vocabularies in this repository are CC0 licensed, see [LICENSE](LICENSE) for details.

### Voc4cat template

The template itself is CC0 licensed, see [LICENSE](LICENSE). Although there is no obligation, we nevertheless appreciate if our work is acknowledged in any derivative work.

## Acknowledgement

This work was funded by the German Research Foundation (DFG) through the project "[NFDI4Cat](https://www.nfdi4cat.org) - NFDI for Catalysis-Related Sciences" (DFG project no. [441926934](https://gepris.dfg.de/gepris/projekt/441926934)), within the National Research Data Infrastructure ([NFDI](https://www.nfdi.de)) programme of the Joint Science Conference (GWK).
