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
  "vcs": "git",
  "laborHours": 4252,
  "platforms": ["windows", "mac", "linux"],
  "categories": ["data-analytics", "application-development", "data-collection"],
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
  "date": {
    "created": "2023-06-22T17:08:19Z",
    "lastModified": "2025-02-10T19:13:19Z",
    "metaDataLastUpdated": "2025-02-10T19:14:29.970Z"
  },
  "tags": ["AI", "deduplication", "data", "ACA", "FHIR"],
  "contact": {
    "email": "opensource@cms.hhs.gov",
    "name": "CMS Open Source Team"
  },
  "localisation": false,
  "repositoryType": "application",
  "userInput": "Yes",
  "fismaLevel": "Moderate",
  "group": "CMS/OA/DSAC",
  "subsetInHealthcare": "Operational",
  "userType": "Providers",
  "repositoryHost": "Github.com",
  "maturityModelTier": "3",
  "projectType": "Tools"
}
```

## Example 2: [CMS Metrics Website](https://github.com/DSACMS/metrics)

The CMS Metrics Website is a [tier 3](https://github.com/DSACMS/repo-scaffolder/blob/dev/maturity-model-tiers.md#tier-information) project where government employees can view repository metrics on CMS open source projects, currently maintained by the CMS OSPO.

```
{
"name": "metrics",
"description": "Experimentations in Open Source Repository Metrics",
"longDescription": "The CMS Repository Metrics Website shows an overview of software development activity across open source projects within a specified organization. This webpage is meant to be used by developers and program managers interested in repository health within CMS open source projects.",
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
"vcs": "git",
"laborHours": 20475,
"platforms": ["web"],
"categories": ["data-visualization", "data-analytics"],
"softwareType": "standalone/web",
"languages": [
"Liquid",
"JavaScript",
"CSS",
"Shell",
"Python"
],
"maintenance": "internal",
"date": {
"created": "2023-07-18T14:10:58Z",
"lastModified": "2025-02-11T19:10:14Z",
"metaDataLastUpdated": "2025-02-11T19:20:16.212Z"
},
"tags": ["metrics", "ospo", "repository"],
"contact": {
"email": "opensource@cms.hhs.gov",
"name": "CMS/OA/DSAC"
},
"localisation": false,
"repositoryType": "website",
"userInput": "No",
"fismaLevel": "Low",
"group": "CMS/OA/DSAC",
"subsetInHealthcare": "Operational",
"userType": "Government",
"repositoryHost": "Github.com",
"maturityModelTier": 3,
"projectType": "Website"
}
```
