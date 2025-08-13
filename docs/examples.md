# Examples of code.json

Below are good examples of metadata in CMS code.json files. We hope it helps when creating your repository-level code.json file.

## Example 1: [DedupliFHIR](https://github.com/DSACMS/dedupliFHIR)

DedupliFHIR is a desktop app tool that uses AI deduplication to identify duplicates in patient records. It is a [tier 3](https://github.com/DSACMS/repo-scaffolder/blob/dev/maturity-model-tiers.md#tier-information) project launched in production that receives user input.

```
{
  "name": "dedupliFHIR",
  "description": "Prototype for basic deduplication and aggregation of eCQM data",
  "longDescription": "A CLI bundled with an electron front-end that provides data-linkage and AI deduplication for reported ACO data at scale.",
  "status": "Production",
  "permissions": {
    "license": [
      {
        "name": "CC0 1.0 Universal",
        "URL": "https://github.com/DSACMS/dedupliFHIR/blob/main/LICENSE"
      }
    ],
    "usageType": "openSource",
    "exemptionText": ""
  },
  "organization": "Centers for Medicare & Medicaid Services",
  "repositoryURL": "https://github.com/DSACMS/dedupliFHIR",
  "projectURL": "",
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
  "feedbackMechanisms": "https://github.com/DSACMS/dedupliFHIR/issues",
  "AIUseCaseInventory": true,
  "localisation": false,
  "repositoryType": "application",
  "userInput": "true",
  "fismaLevel": "Moderate",
  "group": "CMS/OA/DSAC",
  "projects": [],
  "systems": [],
  "upstream": "https://github.com/DSACMS/dedupliFHIR/network/dependencies",
  "subsetInHealthcare": [
    "Operational"
  ],
  "userType": [
    "Providers"
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
        "name": "CC0 1.0 Universal",
        "URL": "https://github.com/DSACMS/metrics/blob/main/LICENSE.md"
      }
    ],
    "usageType": "openSource",
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
  "feedbackMechanisms": "https://github.com/DSACMS/metrics/issues",
  "AIUseCaseInventory": true,
  "localisation": false,
  "repositoryType": "website",
  "userInput": "No",
  "fismaLevel": "Low",
  "group": "CMS/OA/DSAC",
  "projects": [],
  "systems": [],
  "upstream": "https://github.com/DSACMS/metrics/network/dependencies",
  "subsetInHealthcare": [
    "Operational"
  ],
  "userType": [
    "Government"
  ],
  "maturityModelTier": 3
}
```
