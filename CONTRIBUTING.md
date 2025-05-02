# How to Contribute

We're so thankful you're considering contributing to an [open source project of
the U.S. government](https://code.gov/)! If you're unsure about anything, just
ask -- or submit the issue or pull request anyway. The worst that can happen is
you'll be politely asked to change something. We appreciate all friendly
contributions.

We encourage you to read this project's CONTRIBUTING policy (you are here), its
[LICENSE](LICENSE.md), and its [README](README.md).

## Getting Started

If you would like to comment and provide feedback on the metadata standard, please let us know by filing an **issue on our GitHub repository.**

We encourage agencies to contribute by submitting a pull request to [include their extended schema in the repository](../schemas). This helps foster collaboration and ensures shared improvements benefit the wider community.

For CMS, we are open to adding more fields to CMS code.json for any metadata the agency sees value in collecting. Request new metadata fields by filing a metadata field addition issue [here](https://github.com/DSACMS/gov-codejson/issues/new?template=metadata-field-addition.md).

### Team Specific Guidelines

The project is led by the CMS Open Source Program Office team as detailed in [MAINTAINERS.md](/MAINTAINERS.md)

### Building dependencies

N/A

### Building the Project

N/A

### Workflow and Branching

We follow the [GitHub Flow Workflow](https://guides.github.com/introduction/flow/)

1.  Fork the project
2.  Check out the `main` branch
3.  Create a feature branch
4.  Write changes
5.  From your branch, make a pull request against `DSACMS/gov-codejson/main`
6.  Work with repo maintainers to get your change reviewed
7.  Wait for your change to be pulled into `DSACMS/gov-codejson/main`
8.  Delete your feature branch

### Testing Conventions

N/A

### Coding Style and Linters

N/A

### Writing Issues

If you would like to comment on the metadata standard, please let us know by filing an **issue on our GitHub repository.**

For CMS, we are open to adding more fields to CMS code.json for any metadata the agency sees value in collecting. Request new metadata fields by filing a metadata field addition issue [here](https://github.com/DSACMS/gov-codejson/issues/new?template=metadata-field-addition.md).

### Writing Pull Requests

Comments should be formatted to a width no greater than 80 columns.

Files should be exempt of trailing spaces.

We adhere to a specific format for commit messages. Please write your commit
messages along these guidelines. Please keep the line width no greater than 80
columns (You can use `fmt -n -p -w 80` to accomplish this).

    module-name: One line description of your change (less than 72 characters)

    Problem

    Explain the context and why you're making that change.  What is the problem
    you're trying to solve? In some cases there is not a problem and this can be
    thought of being the motivation for your change.

    Solution

    Describe the modifications you've done.

    Result

    What will change as a result of your pull request? Note that sometimes this
    section is unnecessary because it is self-explanatory based on the solution.

Some important notes regarding the summary line:

- Describe what was done; not the result
- Use the active voice
- Use the present tense
- Capitalize properly
- Do not end in a period — this is a title/subject
- Prefix the subject with its scope

## Reviewing Pull Requests

Pull requests will be reviewed by the CMS Open Source Program Office team as detailed in [MAINTAINERS.md](/MAINTAINERS.md)

<!--
## Shipping Releases

<!-- TODO: What cadence does your project ship new releases? (e.g. one-time, ad-hoc, periodically, upon merge of new patches) Who does so?
-->

## Documentation

Refer to [/docs](./docs/) for information about code.json metadata standard.

## Policies

### Open Source Policy

We adhere to the [CMS Open Source
Policy](https://github.com/CMSGov/cms-open-source-policy). If you have any
questions, just [shoot us an email](mailto:opensource@cms.hhs.gov).

### Security and Responsible Disclosure Policy

_Submit a vulnerability:_ Vulnerability reports can be submitted through [Bugcrowd](https://bugcrowd.com/cms-vdp). Reports may be submitted anonymously. If you share contact information, we will acknowledge receipt of your report within 3 business days.

For more information about our Security, Vulnerability, and Responsible Disclosure Policies, see [SECURITY.md](SECURITY.md).

## Public domain

This project is in the public domain within the United States, and copyright and related rights in the work worldwide are waived through the [CC0 1.0 Universal public domain dedication](https://creativecommons.org/publicdomain/zero/1.0/).

All contributions to this project will be released under the CC0 dedication. By submitting a pull request or issue, you are agreeing to comply with this waiver of copyright interest.
