# Examples of code.json

Below are examples of well-structured and comprehensive metadata in CMS code.json files. These examples demonstrate best practices for repository-level metadata documentation.

For additional reference, the [test directory](../schemas/test) contains unit tests of code.json files from various DSACMS repositories. These tests help ensure consistency and compliance as we make future updates to the schemas.

We encourage you to review these examples and tests when creating or updating your repository-level code.json file to maintain consistency with federal standards.

## Example 1: [DedupliFHIR](https://github.com/DSACMS/dedupliFHIR)

DedupliFHIR is a desktop app tool that uses AI deduplication to identify duplicates in patient records. It is a [tier 3](https://github.com/DSACMS/repo-scaffolder/blob/dev/maturity-model-tiers.md#tier-information) project launched in production that receives user input.

```
{
  "name": "dedupliFHIR",
  "description": "Prototype for basic deduplication and aggregation of eCQM data",
  "longDescription": "A CLI bundled with an Electron.js front-end that provides data-linkage and AI deduplication for reported Accountable Care Organization (ACO) data at scale.",
  "status": "Production",
  "permissions": {
    "license": [
      {
        "name": "CC0 1.0",
        "URL": "https://github.com/DSACMS/dedupliFHIR/blob/main/LICENSE"
      }
    ],
    "usageType": ["openSource"],
    "exemptionText": ""
  },
  "organization": "Centers for Medicare & Medicaid Services",
  "repositoryURL": "https://github.com/DSACMS/dedupliFHIR",
  "repositoryHost": "github.com/DSACMS",
  "repositoryVisibility": "public",
  "vcs": "git",
  "laborHours": 4271,
  "reuseFrequency": {
    "forks": 3,
    "clones": 0
  },
  "platforms": [
    "windows",
    "mac",
    "linux"
  ],
  "categories": [
    "data-analytics",
    "application-development",
    "data-collection"
  ],
  "softwareType": "standalone/desktop",
  "languages": [
    "Python",
    "JavaScript",
    "HTML",
    "CSS",
    "Shell",
    "Makefile"
  ],
  "maintenance": "internal",
  "contractNumber": [],
  "date": {
    "created": "2023-06-22T17:08:19Z",
    "lastModified": "2025-02-13T18:44:26Z",
    "metaDataLastUpdated": "2025-06-10T14:55:32.836Z"
  },
  "tags": [
    "AI",
    "deduplication",
    "data",
    "ACA",
    "FHIR",
    "featured"
  ],
  "contact": {
    "email": "opensource@cms.hhs.gov",
    "name": "CMS Open Source Team"
  },
  "feedbackMechanism": "https://github.com/DSACMS/dedupliFHIR/issues",
  "AIUseCaseID": "0",
  "localisation": false,
  "repositoryType": "application",
  "userInput": true,
  "fismaLevel": "moderate",
  "group": "CMS/OA/DSAC",
  "projects": [],
  "systems": [],
  "upstream": "https://github.com/DSACMS/dedupliFHIR/network/dependencies",
  "subsetInHealthcare": [
    "operational"
  ],
  "userType": [
    "providers"
  ],
  "maturityModelTier": "3"
}
```

## Example 2: [CMS Metrics Website](https://github.com/DSACMS/metrics)

The CMS Metrics Website is a [tier 3](https://github.com/DSACMS/repo-scaffolder/blob/dev/maturity-model-tiers.md#tier-information) project where government employees can view repository metrics on CMS open source projects, currently maintained by the CMS OSPO.

```
{
  "name": "metrics",
  "description": "CMS Open Source Repository Metrics Website",
  "longDescription": "The CMS Repository Metrics Website shows an overview of software development activity across open source projects within a specified organization. It is designed for developers and program managers interested in monitoring health and activity of CMS open source repositories.",
  "status": "Production",
  "permissions": {
    "license": [
      {
        "name": "CC0 1.0",
        "URL": "https://github.com/DSACMS/metrics/blob/main/LICENSE.md"
      }
    ],
    "usageType": ["openSource"],
    "exemptionText": ""
  },
  "organization": "Centers for Medicare & Medicaid Services",
  "repositoryURL": "https://github.com/DSACMS/metrics",
  "projectURL": "https://dsacms.github.io/metrics/",
  "repositoryHost": "github.com/DSACMS",
  "repositoryVisibility": "public",
  "vcs": "git",
  "laborHours": 20722,
  "reuseFrequency": {
    "forks": 4,
    "clones": 0
  },
  "platforms": [
    "web"
  ],
  "categories": [
    "data-visualization",
    "data-analytics"
  ],
  "softwareType": "standalone/web",
  "languages": [
    "Liquid",
    "JavaScript",
    "CSS",
    "Python",
    "Shell"
  ],
  "maintenance": "internal",
  "contractNumber": [],
  "date": {
    "created": "2023-07-18T14:10:58Z",
    "lastModified": "2025-06-01T11:36:12Z",
    "metaDataLastUpdated": "2025-06-06T16:36:38.949Z"
  },
  "tags": [
    "metrics",
    "ospo",
    "repository",
    "featured"
  ],
  "contact": {
    "email": "opensource@cms.hhs.gov",
    "name": "CMS/OA/DSAC/OSPO"
  },
  "feedbackMechanism": "https://github.com/DSACMS/metrics/issues",
  "AIUseCaseID": "0",
  "localisation": false,
  "repositoryType": "website",
  "userInput": false,
  "fismaLevel": "low",
  "group": "CMS/OA/DSAC",
  "projects": [],
  "systems": [],
  "upstream": "https://github.com/DSACMS/metrics/network/dependencies",
  "subsetInHealthcare": [
    "operational"
  ],
  "userType": [
    "government"
  ],
  "maturityModelTier": 3
}
```
