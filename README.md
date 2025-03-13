# gov-codejson

CMS code.json: An agency-wide metadata standard for software projects

## About the Project

This repository contains documentation on CMS code.json, a metadata standard used to collect information on the agency's software projects in compliance with [M-16-21](https://obamawhitehouse.archives.gov/sites/default/files/omb/memoranda/2016/m_16_21.pdf) and the [SHARE IT Act](https://www.congress.gov/bill/118th-congress/house-bill/9566/text/ih).

- [metadata.md](./docs/metadata.md): Overview on CMS code.json metadata standard
- [schemas](./schemas): code.json schema
- [procedures.md](./docs/procedures.md): Procedures and tools on creating and updating metadata
- [examples.md](./docs/metadata_examples.md): Good examples of metadata in current agency code.json files
- [faq.md](./docs/faq.md): Frequently Asked Questions

### Project Vision

To streamline federal agencies' compliance with open source requirements that ensures consistent, accurate, and automated collection of software project metadata enabling transparency, traceability, and efficient risk management across the government.

### Project Mission

To develop and implement a standardized metadata framework for collecting and managing software project information across the agency.

<!--
### Agency Mission
TODO: Good to include since this is an agency-led project -->

<!--
### Team Mission
TODO: Good to include since this is an agency-led project -->

## Core Team

An up-to-date list of core team members can be found in [MAINTAINERS.md](MAINTAINERS.md). At this time, the project is still building the core team and defining roles and responsibilities. We are eagerly seeking individuals who would like to join the community and help us define and fill these roles.

## Documentation Index

- [docs](./docs)

## Repository Structure

##### Documentation

- [schemas](./schemas)
- [docs](./docs)

##### Files

- [CONTRIBUTING.md](./CONTRIBUTING.md)
- [MAINTAINERS.md](./MAINTAINERS.md)
- [CODEOWNERS.md](./CODEOWNERS.md)
- [COMMUNITY_GUIDELINES.md](./COMMUNITY_GUIDELINES.md)
- [CODE_OF_CONDUCT.md](./CODE_OF_CONDUCT.md)
- [SECURITY.md](./SECURITY.md)
- [LICENSE](./LICENSE)

# Development and Software Delivery Lifecycle

The following guide is for members of the project team who have access to the repository as well as code contributors. The main difference between internal and external contributions is that external contributors will need to fork the project and will not be able to merge their own pull requests. For more information on contributing, see: [CONTRIBUTING.md](./CONTRIBUTING.md).

## Local Development

Clone the project to update the documentation files. Send a PR for review.

```
git clone https://github.com/DSACMS/gov-codejson
```

## Coding Style and Linters

N/A

## Branching Model

This project follows [trunk-based development](https://trunkbaseddevelopment.com/), which means:

- Make small changes in [short-lived feature branches](https://trunkbaseddevelopment.com/short-lived-feature-branches/) and merge to `main` frequently.
- Be open to submitting multiple small pull requests for a single ticket (i.e. reference the same ticket across multiple pull requests).
- Treat each change you merge to `main` as immediately deployable to production. Do not merge changes that depend on subsequent changes you plan to make, even if you plan to make those changes shortly.
- Ticket any unfinished or partially finished work.
- Tests should be written for changes introduced, and adhere to the text percentage threshold determined by the project.

This project uses **continuous deployment** using [Github Actions](https://github.com/features/actions) which is configured in the [./github/workflows](.github/workflows) directory.

Pull-requests are merged to `main` and the changes are immediately deployed to the development environment. Releases are created to push changes to production.

## Contributing

Thank you for considering contributing to an Open Source project of the US Government! For more information about our contribution guidelines, see [CONTRIBUTING.md](CONTRIBUTING.md).

## Codeowners

The contents of this repository are managed by the CMS Open Source Program Office. Those responsible for the code and documentation in this repository can be found in [CODEOWNERS.md](CODEOWNERS.md).

## Community

The gov-codejson team is taking a community-first and open source approach to the product development of this tool. We believe government software should be made in the open and be built and licensed such that anyone can download the code, run it themselves without paying money to third parties or using proprietary software, and use it as they will.

We know that we can learn from a wide variety of communities, including those who will use or will be impacted by the tool, who are experts in technology, or who have experience with similar technologies deployed in other spaces. We are dedicated to creating forums for continuous conversation and feedback to help shape the design and development of the tool.

We also recognize capacity building as a key part of involving a diverse open source community. We are doing our best to use accessible language, provide technical and process documents, and offer support to community members with a wide variety of backgrounds and skillsets.

### Community Guidelines

Principles and guidelines for participating in our open source community are can be found in [COMMUNITY_GUIDELINES.md](COMMUNITY_GUIDELINES.md). Please read them before joining or starting a conversation in this repo or one of the channels listed below. All community members and participants are expected to adhere to the community guidelines and code of conduct when participating in community spaces including: code repositories, communication channels and venues, and events.

<!--
## Governance
Information about how the gov-codejson community is governed may be found in [GOVERNANCE.md](GOVERNANCE.md).
-->

## Feedback

If you would like to comment on the metadata standard, please let us know by filing an **issue on our GitHub repository.**

We are open to adding more fields to CMS code.json for any metadata the agency sees value in collecting. Request new metadata fields by filing a metadata field addition issue [here](https://github.com/DSACMS/gov-codejson/issues/new?template=metadata-field-addition.md).

If you have ideas for how we can improve or add to our capacity building efforts and methods for welcoming people into our community, please let us know at opensource@cms.hhs.gov.

## Policies

### Open Source Policy

We adhere to the [CMS Open Source
Policy](https://github.com/CMSGov/cms-open-source-policy). If you have any
questions, just [shoot us an email](mailto:opensource@cms.hhs.gov).

### Security and Responsible Disclosure Policy

_Submit a vulnerability:_ Vulnerability reports can be submitted through [Bugcrowd](https://bugcrowd.com/cms-vdp). Reports may be submitted anonymously. If you share contact information, we will acknowledge receipt of your report within 3 business days.

For more information about our Security, Vulnerability, and Responsible Disclosure Policies, see [SECURITY.md](SECURITY.md).

### Software Bill of Materials (SBOM)

A Software Bill of Materials (SBOM) is a formal record containing the details and supply chain relationships of various components used in building software.

In the spirit of [Executive Order 14028 - Improving the Nation’s Cyber Security](https://www.gsa.gov/technology/it-contract-vehicles-and-purchasing-programs/information-technology-category/it-security/executive-order-14028), a SBOM for this repository is provided here: https://github.com/DSACMS/gov-codejson/network/dependencies.

For more information and resources about SBOMs, visit: https://www.cisa.gov/sbom.

## Public domain

This project is in the public domain within the United States, and copyright and related rights in the work worldwide are waived through the [CC0 1.0 Universal public domain dedication](https://creativecommons.org/publicdomain/zero/1.0/) as indicated in [LICENSE](LICENSE).

All contributions to this project will be released under the CC0 dedication. By submitting a pull request or issue, you are agreeing to comply with this waiver of copyright interest.
