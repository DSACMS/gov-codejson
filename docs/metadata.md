# Code.json

`code.json` is a metadata standard created to collect information on the agency's software projects. This is composed of:

- federal code.json standard, created as part of [M-16-21](https://obamawhitehouse.archives.gov/sites/default/files/omb/memoranda/2016/m_16_21.pdf)
- required metadata outlined in the [SHARE IT ACT](https://www.congress.gov/bill/118th-congress/house-bill/9566/text/ih) (e.g. repository visibility, contract number)
- publiccode.yml metadata, an international metadata standard

By harmonizing various standards, this opens up the opportunity to share our work not just on an agency level but also on a national and international level.

The generic code.json schema can be found in the [`schemas` directory](../schemas/schema-1.0.0.json).

### Extending the schema for agency use

The generic schema is designed to be extensible, allowing agencies to add metadata fields that are relevant to their specific needs.

For example, CMS has their [own schema](../schemas/cms/) that includes new fields such as FISMA level, subset in healthcare, and systems.

We encourage agencies to contribute by [submitting an agency schema addition issue](https://github.com/DSACMS/gov-codejson/issues) to [include their extended schema in the repository](../schemas). This helps foster collaboration and ensures shared improvements benefit the wider community.

### code.json Fields

**Legend**

<table>
  <thead>
    <tr>
      <th>Metadata Standard</th>
      <th>Origin</th>
      <th>Icon</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="https://github.com/GSA/code-gov-data/blob/master/schemas/schema-2.0.0.json">code.json</a></td>
      <td>Federal</td>
      <td>🇺🇸</td>
    </tr>
    <tr>
      <td><a href="https://yml.publiccode.tools/">publiccode.yml</a></td>
      <td>International</td>
      <td>🌎</td>
    </tr>
    <tr>
    <td><a href="https://www.congress.gov/bill/118th-congress/house-bill/9566/text/ih">SHARE IT Act</a></td>
      <td>Federal</td>
      <td>📜</td>
    </tr>
  </tbody>
</table>

<table>
  <thead>
    <tr>
      <th>Field</th>
      <th>Presence</th>
      <th>Source</th>
      <th>Type</th>
      <th>Description</th>
      <th>Options/Examples</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>name</td>
      <td>required</td>
      <td>🇺🇸🌎</td>
      <td>str</td>
      <td>Name of the project or software</td>
      <td></td>
    </tr>
    <tr>
      <td>description</td>
      <td>required</td>
      <td>🇺🇸</td>
      <td>str</td>
      <td>A short description of the project. It should be a single line containing a single sentence. Maximum 150 characters are allowed.</td>
      <td></td>
    </tr>
    <tr>
      <td>status</td>
      <td>required</td>
      <td>🇺🇸📜</td>
      <td>str</td>
      <td>Development status of the project</td>
      <td>
        - Ideation<br>
        - Development<br>
        - Alpha<br>
        - Beta<br>
        - Release Candidate<br>
        - Production<br>
        - Archival
      </td>
    </tr>
    <tr>
      <td>permissions/license/url <br> permissions/license/name</td>
      <td>required</td>
      <td>🇺🇸🌎</td>
      <td>obj</td>
      <td>
        An object containing description of the usage/restrictions regarding the release.<br><br>
        An abbreviation for the name of the license. The URL of the release license.
      </td>
      <td></td>
    </tr>
    <tr>
      <td>permissions/usageType</td>
      <td>required</td>
      <td>🇺🇸📜</td>
      <td>str</td>
      <td>A list of enumerated values which describes the usage permissions for the release: (1) openSource: Open source; (2) governmentWideReuse: Government-wide reuse; (3) exemptByNationalSecurity: The source code is primarily for use in national security system as defined in section 11103 of title 40, USC; (4) exemptByNationalIntelligence: The source code is developed by an agency or part of an agency that is an element of the intelligence community, as defined in section 3(4) of the National Security Act of 1947; (5) exemptByFOIA: The source code is exempt under the Freedom of Information Act; (6) exemptByEAR: The source code is exempt under the Export Administration Regulations; (7) exemptByITAR: The source code is exempt under the the International Traffic in Arms Regulations; (8) exemptByTSA: The source code is exempt under the regulations of the Transportation Security Administration relating to the protection of Sensitive Security Information; (9) exemptByClassifiedInformation: The source code is exempt under the Federal laws and regulations governing the sharing of classified information not covered by exemptByNationalSecurity, exemptByNationalIntelligence, exemptbyFOIA, exemptByEAR, exemptByITAR, and exemptByTSA; (10) exemptByPrivacyRisk: The sharing or public accessibility of the source code would create an identifiable risk to the privacy of an individual; (11) exemptByIPRestriction: The sharing of the source code is limited by patent or intellectual property restrictions; (12) exemptByAgencySystem: The sharing of the source code would create an identifiable risk to the stability, security, or integrity of the agency’s systems or personnel; (13) exemptByAgencyMission: The sharing of the source code would create an identifiable risk to agency mission, programs, or operations;  (14) exemptByCIO: The CIO believes it is in the national interest to exempt sharing the source code;  (15) exemptByPolicyDate: The release was created prior to the M-16-21 policy (August 8, 2016)",
      </td>
      <td>
        - openSource<br>
        - governmentWideReuse<br>
        - exemptByNationalSecurity<br>
        - exemptByNationalIntelligence<br>
        - exemptByFOIA<br>
        - exemptByEAR<br>
        - exemptByITAR<br>
        - exemptByTSA<br>
        - exemptByClassifiedInformation<br>
        - exemptByPrivacyRisk<br>
        - exemptByIPRestriction<br>
        - exemptByAgencySystem<br>
        - exemptByAgencyMission<br>
        - exemptByCIO<br>
        - exemptByPolicyDate
      </td>
    </tr>
    <tr>
      <td>permissions/exemptionText</td>
      <td>optional</td>
      <td>🇺🇸📜</td>
      <td>str</td>
      <td>If an exemption is listed in the 'usageType' field, this field should include a one- or two- sentence justification for the exemption used.</td>
      <td></td>
    </tr>
    <tr>
      <td>organization</td>
      <td>required</td>
      <td>🇺🇸</td>
      <td>str</td>
      <td>The organization or component within the agency to which the releases listed belong.</td>
      <td>Centers for Medicare & Medicaid Services, 18F, Navy</td>
    </tr>
    <tr>
      <td>repositoryURL</td>
      <td>required</td>
      <td>🇺🇸📜</td>
      <td>str</td>
      <td>The URL of the public release repository for open source repositories. This field is not required for repositories that are only available as government-wide reuse or are closed (pursuant to one of the exemptions). It can be listed as 'private' for repositories that are closed.</td>
      <td></td>
    </tr>
    <tr>
      <td>repositoryVisibility</td>
      <td>required</td>
      <td>📜</td>
      <td>str</td>
      <td>Visibility of repository</td>
      <td>
        - public<br>
        - private
      </td>
    </tr>
    <tr>
      <td>vcs</td>
      <td>required</td>
      <td>🇺🇸</td>
      <td>str</td>
      <td>Version control system used</td>
      <td>
        - git<br>
        - hg<br>
        - svn<br>
        - rcs<br>
        - bzr
      </td>
    </tr>
    <tr>
      <td>laborHours</td>
      <td>required</td>
      <td>🇺🇸</td>
      <td>int</td>
      <td>Labor hours invested in the project. Calculated through <a href="https://github.com/boyter/scc">COCOMO & SCC tool</a></td>
      <td></td>
    </tr>
    <tr>
      <td>reuseFrequency/forks <br> reuseFrequency/clones</td>
      <td>required</td>
      <td>📜</td>
      <td>obj</td>
      <td>Measures frequency of code reuse in various forms</td>
      <td></td>
    </tr>
    <tr>
      <td>maintenance</td>
      <td>required</td>
      <td>🌎📜</td>
      <td>str</td>
      <td>The dedicated staff that keeps the software up-to-date, if any</td>
      <td>
        - internal<br>
        - contract<br>
        - community<br>
        - none
      </td>
    </tr>
    <tr>
      <td>contractNumber</td>
      <td>required</td>
      <td>📜</td>
      <td>array</td>
      <td>Contract number</td>
      <td></td>
    </tr>
    <tr>
      <td>date/created <br> date/lastModified date/metadataLastUpdated</td>
      <td>required</td>
      <td>🇺🇸</td>
      <td>obj</td>
      <td>A date object describing the release</td>
      <td></td>
    </tr>
    <tr>
      <td>tags</td>
      <td>required</td>
      <td>🇺🇸</td>
      <td>arr</td>
      <td>Topics and keywords associated with the project to improve search and discoverability</td>
      <td></td>
    </tr>
    <tr>
      <td>contact/email <br> contact/name</td>
      <td>required</td>
      <td>🇺🇸🌎</td>
      <td>obj</td>
      <td>Point of contact for the release<br>Email of point of contact<br>Name of point of contact</td>
      <td></td>
    </tr>
    <tr>
      <td>feedbackMechanisms</td>
      <td>required</td>
      <td>📜</td>
      <td>str</td>
      <td>Method a repository receives feedback from the community (i.e. URL to GitHub repository issues page)</td>
      <td>
        - Submitting issues to repo<br>
      </td>
    </tr>
    <tr>
      <td>AIUseCaseInventory</td>
      <td>required</td>
      <td>📜</td>
      <td>bool</td>
      <td>Indicates if the software is included in the agency's AI use case inventory</td>
      <td>
        - true<br>
        - false
      </td>
    </tr>
  </tbody>
</table>

Full schema can be found in [schema-1.0.0.json](../schemas/schema-1.0.0.json).

### CMS code.json Fields

**Legend**

<table>
  <thead>
    <tr>
      <th>Metadata Standard</th>
      <th>Origin</th>
      <th>Icon</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="https://github.com/GSA/code-gov-data/blob/master/schemas/schema-2.0.0.json">code.json</a></td>
      <td>Federal</td>
      <td>🇺🇸</td>
    </tr>
    <tr>
      <td><a href="https://yml.publiccode.tools/">publiccode.yml</a></td>
      <td>International</td>
      <td>🌎</td>
    </tr>
    <tr>
      <td>CMS fields</td>
      <td>Agency</td>
      <td><img src="../assets/cms-logo.jpg" alt="CMS Logo"></td>
    </tr>
    <tr>
    <td><a href="https://www.congress.gov/bill/118th-congress/house-bill/9566/text/ih">SHARE IT Act</a></td>
      <td>Federal</td>
      <td>📜</td>
    </tr>
  </tbody>
</table>

<table>
  <thead>
    <tr>
      <th>Field</th>
      <th>Presence</th>
      <th>Source</th>
      <th>Type</th>
      <th>Description</th>
      <th>Options/Examples</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>name</td>
      <td>required</td>
      <td>🇺🇸🌎</td>
      <td>str</td>
      <td>Name of the project or software</td>
      <td></td>
    </tr>
    <tr>
      <td>description</td>
      <td>required</td>
      <td>🇺🇸</td>
      <td>str</td>
      <td>A short description of the project. It should be a single line containing a single sentence. Maximum 150 characters are allowed.</td>
      <td></td>
    </tr>
    <tr>
      <td>longDescription</td>
      <td>required</td>
      <td>🌎</td>
      <td>str</td>
      <td>Provide longer description of the software, between 150 and 10000 chars. It is meant to provide an overview of the capabilities of the software for a potential user.</td>
      <td></td>
    </tr>
    <tr>
      <td>status</td>
      <td>required</td>
      <td>🇺🇸📜</td>
      <td>str</td>
      <td>Development status of the project</td>
      <td>
        - Ideation<br>
        - Development<br>
        - Alpha<br>
        - Beta<br>
        - Release Candidate<br>
        - Production<br>
        - Archival
      </td>
    </tr>
    <tr>
      <td>permissions/license/url <br> permissions/license/name</td>
      <td>required</td>
      <td>🇺🇸🌎</td>
      <td>obj</td>
      <td>
        An object containing description of the usage/restrictions regarding the release.<br><br>
        An abbreviation for the name of the license. The URL of the release license.
      </td>
      <td></td>
    </tr>
    <tr>
      <td>permissions/usageType</td>
      <td>required</td>
      <td>🇺🇸📜</td>
      <td>str</td>
      <td>A list of enumerated values which describes the usage permissions for the release: (1) openSource: Open source; (2) governmentWideReuse: Government-wide reuse; (3) exemptByLaw: The sharing of the source code is restricted by law or regulation, including—but not limited to—patent or intellectual property law, the Export Asset Regulations, the International Traffic in Arms Regulation, and the Federal laws and regulations governing classified information; (4) exemptByNationalSecurity: The sharing of the source code would create an identifiable risk to the detriment of national security, confidentiality of Government information, or individual privacy; (5) exemptByAgencySystem: The sharing of the source code would create an identifiable risk to the stability, security, or integrity of the agency’s systems or personnel, (6) exemptByAgencyMission: The sharing of the source code would create an identifiable risk to agency mission, programs, or operations; (7) exemptByCIO: The CIO believes it is in the national interest to exempt sharing the source code; (8) exemptByPolicyDate: The release was created prior to the M-16-21 policy (August 8, 2016)</td>
      <td>
        - openSource<br>
        - governmentWideReuse<br>
        - exemptByLaw<br>
        - exemptByNationalSecurity<br>
        - exemptByAgencySystem<br>
        - exemptByAgencyMission<br>
        - exemptByCIO<br>
        - exemptByPolicyDate
      </td>
    </tr>
    <tr>
      <td>permissions/exemptionText</td>
      <td>optional</td>
      <td>🇺🇸📜</td>
      <td>str</td>
      <td>If an exemption is listed in the 'usageType' field, this field should include a one- or two- sentence justification for the exemption used.</td>
      <td></td>
    </tr>
    <tr>
      <td>organization</td>
      <td>required</td>
      <td>🇺🇸</td>
      <td>str</td>
      <td>Organization responsible for the project</td>
      <td>Centers for Medicare & Medicaid Services</td>
    </tr>
    <tr>
      <td>repositoryURL</td>
      <td>required</td>
      <td>🇺🇸📜</td>
      <td>str</td>
      <td>The URL of the public release repository for open source repositories. This field is not required for repositories that are only available as government-wide reuse or are closed (pursuant to one of the exemptions). It can be listed as 'private' for repositories that are closed.</td>
      <td></td>
    </tr>
    <tr>
      <td>projectURL</td>
      <td>optional</td>
      <td><img src="../assets/cms-logo.jpg" alt="CMS Logo"></td>
      <td>str</td>
      <td>URL to landing page, demo, or production instance of project</td>
      <td></td>
    </tr>
    <tr>
      <td>repositoryHost</td>
      <td>required</td>
      <td><img src="../assets/cms-logo.jpg" alt="CMS Logo"></td>
      <td>str</td>
      <td>Location where source code is hosted</td>
      <td>
        - github.com/CMSgov<br>
        - github.com/CMS-Enterprise<br>
        - github.com/Enterprise-CMCS<br>
        - github.com/DSACMS<br>
        - github.cms.gov<br>
        - CCSQ GitHub
      </td>
    </tr>
    <tr>
      <td>repositoryVisibility</td>
      <td>required</td>
      <td>📜</td>
      <td>str</td>
      <td>Visibility of repository</td>
      <td>
        - public<br>
        - private
      </td>
    </tr>
    <tr>
      <td>vcs</td>
      <td>required</td>
      <td>🇺🇸</td>
      <td>str</td>
      <td>Version control system used</td>
      <td>
        - git<br>
        - hg<br>
        - svn<br>
        - rcs<br>
        - bzr
      </td>
    </tr>
    <tr>
      <td>laborHours</td>
      <td>required</td>
      <td>🇺🇸</td>
      <td>int</td>
      <td>Labor hours invested in the project. Calculated through <a href="https://github.com/boyter/scc">COCOMO & SCC tool</a></td>
      <td></td>
    </tr>
    <tr>
      <td>reuseFrequency/forks <br> reuseFrequency/clones</td>
      <td>required</td>
      <td>📜</td>
      <td>obj</td>
      <td>Measures frequency of code reuse in various forms</td>
      <td></td>
    </tr>
    <tr>
      <td>platforms</td>
      <td>required</td>
      <td>🌎</td>
      <td>arr</td>
      <td>Platforms supported by the project</td>
      <td>
        - web<br>
        - windows<br>
        - mac<br>
        - linux<br>
        - ios<br>
        - android<br>
        - other
      </td>
    </tr>
    <tr>
      <td>categories</td>
      <td>required</td>
      <td>🌎</td>
      <td>arr</td>
      <td>Categories the project belongs to.</td>
      <td>Select from: <a href="https://yml.publiccode.tools/categories-list.html">categories list</a></td>
    </tr>
    <tr>
      <td>softwareType</td>
      <td>required</td>
      <td>🌎</td>
      <td>str</td>
      <td>Type of software</td>
      <td>
        - standalone/mobile<br>
        - standalone/iot<br>
        - standalone/desktop<br>
        - standalone/web<br>
        - standalone/backend<br>
        - standalone/other<br>
        - addon<br>
        - library<br>
        - configurationFiles
      </td>
    </tr>
    <tr>
      <td>languages</td>
      <td>required</td>
      <td>🇺🇸</td>
      <td>str</td>
      <td>Programming languages that make up the codebase</td>
      <td></td>
    </tr>
    <tr>
      <td>maintenance</td>
      <td>required</td>
      <td>🌎📜</td>
      <td>str</td>
      <td>The dedicated staff that keeps the software up-to-date, if any</td>
      <td>
        - internal<br>
        - contract<br>
        - community<br>
        - none
      </td>
    </tr>
        <tr>
      <td>contractNumber</td>
      <td>required</td>
      <td>📜</td>
      <td>array</td>
      <td>Contract number</td>
      <td></td>
    </tr>
    <tr>
      <td>date/created <br> date/lastModified date/metadataLastUpdated</td>
      <td>required</td>
      <td>🇺🇸</td>
      <td>obj</td>
      <td>A date object describing the release</td>
      <td></td>
    </tr>
    <tr>
      <td>tags</td>
      <td>required</td>
      <td>🇺🇸</td>
      <td>arr</td>
      <td>Topics and keywords associated with the project to improve search and discoverability</td>
      <td></td>
    </tr>
    <tr>
      <td>contact/email <br> contact/name</td>
      <td>required</td>
      <td>🇺🇸🌎</td>
      <td>obj</td>
      <td>Point of contact for the release<br>Email of point of contact<br>Name of point of contact</td>
      <td></td>
    </tr>
    <tr>
      <td>feedbackMechanisms</td>
      <td>required</td>
      <td>📜</td>
      <td>str</td>
      <td>Method a repository receives feedback from the community (i.e. URL to GitHub repository issues)</td>
      <td>
        - Submitting issues to repo<br>
      </td>
    </tr>
    <tr>
      <td>localisation</td>
      <td>required</td>
      <td>🌎</td>
      <td>bool</td>
      <td>Indicates if the project supports multiple languages</td>
      <td>
        - true<br>
        - false
      </td>
    </tr>
    <tr>
      <td>repositoryType</td>
      <td>required</td>
      <td><img src="../assets/cms-logo.jpg" alt="CMS Logo"></td>
      <td>str</td>
      <td>Purpose and functionality of the repository</td>
      <td>
        - package<br>
        - website<br>
        - standards<br>
        - libraries<br>
        - data<br>
        - application<br>
        - tools<br>
        - APIs
      </td>
    </tr>
    <tr>
      <td>userInput</td>
      <td>required</td>
      <td><img src="../assets/cms-logo.jpg" alt="CMS Logo"></td>
      <td>bool</td>
      <td>Does the software accept user input?</td>
      <td>
        - true<br>
        - false
      </td>
    </tr>
    <tr>
      <td>fismaLevel</td>
      <td>required</td>
      <td><img src="../assets/cms-logo.jpg" alt="CMS Logo"></td>
      <td>str</td>
      <td>Level of security categorization assigned to an information system under the Federal Information Security Modernization Act (FISMA): <a href="https://security.cms.gov/learn/federal-information-security-modernization-act-fisma">link</a></td>
      <td>
        - low<br>
        - moderate<br>
        - high
      </td>
    </tr>
    <tr>
      <td>group</td>
      <td>required</td>
      <td><img src="../assets/cms-logo.jpg" alt="CMS Logo"></td>
      <td>str</td>
      <td>Home Department / Org / Group associated with the project</td>
      <td></td>
    </tr>
    <tr>
      <td>project</td>
      <td>required</td>
      <td><img src="../assets/cms-logo.jpg" alt="CMS Logo"></td>
      <td>arr</td>
      <td>Project(s) that is associated or related to the repository, if any.</td>
      <td>Bluebutton, MPSM, codejson</td>
    </tr>
    <tr>
      <td>systems</td>
      <td>optional</td>
      <td><img src="../assets/cms-logo.jpg" alt="CMS Logo"></td>
      <td>arr</td>
      <td>CMS systems that the repository interfaces with or depends on, if any.</td>
      <td>IDR, PECOS</td>
    </tr>
    <tr>
      <td>upstream</td>
      <td>optional</td>
      <td><img src="../assets/cms-logo.jpg" alt="CMS Logo"></td>
      <td>arr</td>
      <td>Link of the upstream repositories and dependencies used, in the form of a Software Bill of Materials/SBOM (https://github.com/$ORG_NAME/$REPO_NAME/network/dependencies)</td>
      <td>augur, uswds</td>
    </tr>
        <tr>
      <td>subsetInHealthcare</td>
      <td>required</td>
      <td><img src="../assets/cms-logo.jpg" alt="CMS Logo"></td>
      <td>arr</td>
      <td>Healthcare-related subset</td>
      <td>
        - policy<br>
        - operational<br>
        - medicare<br>
        - medicaid
      </td>
    </tr>
    <tr>
      <td>userType</td>
      <td>required</td>
      <td><img src="../assets/cms-logo.jpg" alt="CMS Logo"></td>
      <td>arr</td>
      <td>Types of users who interact with the software</td>
      <td>
        - providers<br>
        - patients<br>
        - government
      </td>
    </tr>
    <tr>
      <td>maturityModelTier</td>
      <td>required</td>
      <td><img src="../assets/cms-logo.jpg" alt="CMS Logo"></td>
      <td>int</td>
      <td>Maturity model tier</td>
      <td>0, 1, 2, 3, 4</td>
    </tr>
  </tbody>
</table>

Full schema can be found in [schema-1.0.0.json](../schemas/schema-1.0.0.json).

### Adding new metadata fields

For CMS, we are open to adding more fields to CMS code.json for any metadata the agency sees value in collecting. Request new metadata fields by filing a metadata field addition issue [here](https://github.com/DSACMS/gov-codejson/issues/new?template=metadata-field-addition.md).
