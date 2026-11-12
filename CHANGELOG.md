# Changelog

All notable changes to the `code.json` schemas in this repository — the generic, government-wide schema (`schemas/schema-*.json`), the CMS-specific schema (`schemas/cms/schema-*.json`), and the agency-index schema (`schemas/agency-index/schema-*.json`) — are documented in this file, so changes are easy to track across releases.

This project follows a `major.minor.patch`-style versioning scheme for each schema file.

> [!IMPORTANT]  
> This repository is no longer actively maintained and has been migrated to the [GSA-SHARE-IT organization](https://github.com/GSA-SHARE-IT/codejson-schemas). Going forward, visit the [codejson-schemas repository](https://github.com/GSA-SHARE-IT/codejson-schemas) for latest updates on the code.json metadata standard along with the latest schema releases.

## Government-Wide Generic `code.json` Schema

### [schema-2.0.0.json](./schemas/schema-2.0.0.json)

#### Added

- `feedbackMechanism` (singular)
- `version`, `homepageURL`, `downloadURL`, `disclaimerURL`, `disclaimerText`, `relatedCode`, `reusedCode`, `partners` added as optional fields, taken from original [M-16-21 code.json schema](https://github.com/GSA/code-gov-data/tree/master/schemas)
- `AIUseCaseID` added for assisting with agency collection of their AI Use Case Inventory as part of M-25-21 compliance
- `SBOM` added to include software's SBOM in metadata as part of EO 14028

#### Changed

- Migrated `$schema` dialect from `draft-04` to `2020-12` and introduced a formal `$id` (`https://dsacms.github.io/code-json-schema.json`).
- Corrected a structural bug from `schema-1.0.0.json`, where all field definitions were incorrectly nested one level too deep under a top-level `items` key instead of directly under `properties`.
- `permissions.usageType` changed from a single `string` value to an `array` of strings, allowing multiple exemption reasons to be declared simultaneously.
- Expanded and refined the exemption enum taxonomy: the old `exemptByLaw` was split into `exemptByNationalSecurity`, `exemptByNationalIntelligence`, `exemptByFOIA`, `exemptByEAR`, `exemptByITAR`, `exemptByTSA`, and `exemptByClassifiedInformation`; the old `exemptByNationalSecurity` (covering national security, confidentiality, _and_ individual privacy risk) was split so privacy risk became its own value, `exemptByPrivacyRisk`; `exemptByIPRestriction` was also added.
- `organization`: changed from a CMS-specific enum restriction to a free-text string with an example (`'18F'` or `'Navy'`) suitable for any agency.
- Top-level `additionalProperties` changed from `false` to `true`, allowing agencies to extend the schema with their own custom fields.
- `reuseFrequency` description updated for clarity: _"Measures frequency of code reuse in various forms. (e.g. forks, downloads, clones)"_

#### Required

- `name`, `description`, `status`, `permissions`, `organization`, `repositoryURL`, `repositoryVisibility`, `vcs`, `laborHours`, `reuseFrequency`, `languages`, `maintenance`, `contractNumber`, `SBOM`, `date`, `tags`, `contact`, `feedbackMechanism`, and `AIUseCaseID` are required.

### [schema-1.0.0.json](./schemas/schema-1.0.0.json)

Initial generic (government-wide) `code.json` schema (`draft-04`). Known issues, later fixed in `schema-2.0.0.json`:

- Field definitions are nested one level too deep under `properties.items` instead of directly under `properties`.
- `permissions.usageType` is a single `string` value (not an array), so only one exemption reason could be declared per release, with a smaller 8-value exemption enum (`openSource`, `governmentWideReuse`, `exemptByLaw`, `exemptByNationalSecurity`, `exemptByAgencySystem`, `exemptByAgencyMission`, `exemptByCIO`, `exemptByPolicyDate`).
- `organization` field not present in this version.

## CMS Agency-Specific `code.json` Schema

### [schema-2.1.0.json](/schemas/cms/schema-2.1.0.json)

#### Changed (enum value additions only — no properties added/removed)

- `repositoryHost`: added `github.com/MeasureAuthoringTool`.
- `subsetInHealthcare`: added `SNAP`, `TANF`, `human-benefit-services`.
- `userType`: added `applicants`, `beneficiaries`, `enrollees`.

### [schema-2.0.0.json](/schemas/cms/schema-2.0.0.json)

#### Added

- `version`, `homepageURL`, `downloadURL`, `disclaimerURL`, `disclaimerText`, `relatedCode`, `reusedCode`, `partners` added as optional fields, taken from original [M-16-21 code.json schema](https://github.com/GSA/code-gov-data/tree/master/schemas)

#### Removed

- `projectURL` (superseded by `homepageURL`/`downloadURL`).

#### Changed

- Migrated `$schema` dialect from `draft-04` to `2020-12` and introduced a formal `$id` (`https://dsacms.github.io/code-json-schema.json`).

### [schema-0.2.0.json](/schemas/cms/schema-0.2.0.json)

#### Added

- `feedbackMechanism` (singular).
- `AIUseCaseID` added for assisting with agency collection of their AI Use Case Inventory as part of M-25-21 compliance
- `SBOM` added to include software's SBOM in metadata as part of EO 14028

#### Removed

- `feedbackMechanisms` (plural, replaced by singular `feedbackMechanism`), `upstream`.

#### Changed

- Migrated `$schema` dialect from `draft-04` to `2020-12` and introduced a formal `$id` (`https://dsacms.github.io/code-json-schema.json`).

### [schema-0.1.0.json](/schemas/cms/schema-0.1.0.json)

#### Added

- `contractNumber`, `feedbackMechanisms`, `repositoryVisibility`, `reuseFrequency` added as required metadata fields as per the SHARE IT Act
- `projectURL`, `projects`, `systems`, `upstream` added to better track repository's relationship with its project, CMS systems, and dependencies

#### Fixed

- Corrected a structural bug from `schema-0.0.0` where all field definitions were incorrectly nested one level too deep under a top-level `items` key instead of directly under `properties`.

### [schema-0.0.0.json](/schemas/cms/schema-0.0.0.json)

Initial CMS `code.json` schema (`draft-04`). Note: this version has a known structural issue — field definitions are nested under `properties.items` instead of directly under `properties`, so the schema does not validate `name`, `status`, etc. as intended.

## `agency-index.json` Schema

### [schema-2.0.0.json](/schemas/agency-index/schema-2.0.0.json)

> [!IMPORTANT]  
> This is the latest version of the agency-index schema. Note: The described improvements (enum constraint on `agency` and removal of `measurementType`) are planned but **not yet implemented** in the current schema file.

#### Planned Changes

- `agency` field will use an `enum` constraint with valid Clinger Cohen Act agency acronyms, ensuring data consistency and validation. Valid values include: USDA, DOC, DOD, ED, DOE, HHS, HUD, DHS, DOI, DOJ, DOL, DOS, DOT, TREASURY, VA, CFPB, EPA, FEC, GSA, NARA, NASA, NRC, NSF, OPM, SBA, SSA, USAID.
- `description` to be updated from "Agency source code catalog" to "A centralized inventory of an agency's software portfolio" for clarity.
- `$id` field to be removed from schema (no longer explicitly defined).
- `measurementType` object to be removed entirely — this field is no longer part of the schema as a result of the pilot program ending and SHARE IT Act requirements superceding.
- `required` array to be simplified from `["version", "measurementType", "agency", "releases"]` to `["version", "agency", "releases"]`.

#### Current Structure

The current schema-2.0.0.json retains the following from the M-16-21 pilot:

- `measurementType` property containing `method` and `ifOther` fields for specifying how the open source requirement was measured ("linesOfCode", "modules", "cost", "projects", "systems", "other").
- `required` array: `["version", "measurementType", "agency", "releases"]`.
- `agency` accepts any string value (no enum constraint).

### [schema-0.1.0.json](/schemas/agency-index/schema-0.1.0.json) [Not Present in Repository]

Initial agency-index.json schema established as part of the [M-16-21 Federal Source Code Policy](https://github.com/GSA/code-gov-data). Includes `agency`, `releases`, and `version` as required fields. The `agency` field accepts any string value (no enum constraint). M-16-21 required federal agencies, as part of a three-year pilot program, to release at least 20% of new custom-developed source code to the public as Open Source Software. `measurementType` field was created to track this and dictate the method in which this is measured ("linesOfCode", "modules", "cost", "projects", "systems", "other")
