# Procedures

The CMS Open Source Program Office developed various tools that can automate detecting, adding, and updating metadata to repositories.

> **Learn more about our SHARE IT Act tools**: https://dsacms.github.io/share-it-act-lp/

**Procedures for Project Teams**:
[Creating a code.json file in your repository](#creating-a-codejson-file-in-your-repository)
- [code.json generator form site](#using-form-site)
- [automated-codejson-generator GitHub Action](#using-automated-codejson-generator)
- [repo-scaffolder](#using-repo-scaffolder)

***Procedures for Agencies**:
[Generate an agency-index.json file for submission](#generate-an-agency-indexjson-file-for-agencies)
- [codejson-index-generator](#using-codejson-index-generator)

[Tools created by other teams and agencies](#tools-created-by-other-teams-and-agencies)
- [CMS CMCS](#cms-cmcs-codejson-aggregator)
- [CDC](#cdc-share-it-act-repository-scanner-tool)


## Creating a code.json file in your repository

### Using form site
*This method works best for all repositories on all platforms.*

Users can fill out a web form that creates a code.json file to be uploaded to a project's source code repository: https://dsacms.github.io/codejson-generator.


### Using automated-codejson-generator
*This method works best for repositories hosted on GitHub with GitHub Actions enabled.*

The [automated-codejson-generator](https://github.com/DSACMS/automated-codejson-generator) is a GitHub Action that automatically generates and maintains code.json files for federal open source repositories. It ensures schema consistency and automates metadata calculations, including:

- Labor hours
- Programming languages used
- Repository information
- Timestamps

### Using repo-scaffolder
*This method is most effective when GitHub Actions are unavailable, allowing cookiecutter to be installed locally with Python.*

[repo-scaffolder](https://github.com/DSACMS/repo-scaffolder) is a tool for creating repositories that adhere to repository hygiene standards. It provides file templates detailing project information, contributing guidance, maintainer roles, community involvement, and **project metadata**.

For repositories created using repo-scaffolder, the tool can assist with adding code.json to the repository. Navigate to your project's `.github` directory and run the following cookiecutter command. You will be asked questions about the project in order to collect and store this metadata in code.json.

```
cookiecutter . --directory=codejson
```

For more information on repo-scaffolder, check out the [documentation](https://github.com/DSACMS/repo-scaffolder?tab=readme-ov-file#metadata-collection-using-codejson).

#### Setting up the GitHub Action

To use the automated-codejson-generator in your repository, create a workflow file with the following configuration:

```yaml
name: Update Code.json
on:
  workflow_dispatch:

permissions:
  contents: write
  pull-requests: write

jobs:
  update-code-json:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Repository
        uses: actions/checkout@v4
        with:
          fetch-depth: 0  
      
      - name: Setup Node.js
        uses: actions/setup-node@v4
        with:
          node-version: '20'

      - name: Setup Go
        uses: actions/setup-go@v5
        with:
          go-version: '1.22'
      
      - name: Install SCC
        run: go install github.com/boyter/scc/v3@latest
      
      - name: Update code.json
        uses: DSACMS/automated-codejson-generator@main
        with:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

This action will create a pull request to add or update a compliant code.json file in your repository.

## Generate an agency-index.json file for agencies

### Using codejson-index-generator

The [codejson-index-generator](https://github.com/DSACMS/codejson-index-generator) is a Python-based tool that helps federal agencies compile and maintain their code.json files for code.gov compliance. It scans specified GitHub organizations, finds repositories containing code.json files, and combines them into a single indexed file.

The tool can be run using the [index-generator-website](https://dsacms.github.io/index-generator-website/). 

Alternatively, follow the instructions below to run locally.

#### Prerequisites

- Python 3.x
- GitHub Personal Access Token (recommended for higher rate limits)

#### Installation

1. Clone the repository:
```bash
git clone https://github.com/DSACMS/codejson-index-generator.git
cd codejson-index-generator
```

2. Install required dependencies:
```bash
pip install PyGithub
```

3. Set up your GitHub Personal Access Token:
```bash
export GITHUB_KEY="your-token-here"
```

#### Usage

Run the script from the command line with the following options:

```bash
python main.py --agency AGENCY_NAME --orgs "org1,org2" --output code.json --version VERSION_NUMBER
```

##### Required arguments:
- `--agency`: The name of your agency
- `--orgs`: Comma-separated list of GitHub organizations to scan (no spaces)

##### Optional arguments:
- `--output`: Output filename (default: code.json)
- `--version`: Code.json file version (default: 1.0.0)

##### Example:
```bash
python3 main.py --agency CMS --orgs "DSACMS,CMSgov,CMS-Enterprise" --output code.json --version 1.0.0
```

## Tools created by other teams and agencies

Below are tools other teams and agencies developed to create a consolidated software inventory for the SHARE IT Act. They include methods to retrieve necessary metadata from private and internal repositories.

### CMS CMCS code.json aggregator

mac-fc-aggregate-codejson aggregates code.json files from all private and internal repositories in a GitHub organization
https://github.com/Enterprise-CMCS/mac-fc-aggregate-code-json

## CDC SHARE IT Act Repository Scanner Tool

The CDC SHARE IT Act Repository gathers and consolidates repository metadata from various code environments by generating code.json files in all repositories, having project teams review and correct information for accuracy, then creating an index file containing all aggregated code.json metadata.
https://github.com/CDCgov/ShareIT-Act
https://github.com/OCIO-ricky/ShareITAct_RepoScanning
