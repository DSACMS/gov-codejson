# Code.json

CMS `code.json` is a metadata standard created to collect information on the agency's software projects. This is composed of:

- federal code.json standard, created as part of [M-16-21](https://obamawhitehouse.archives.gov/sites/default/files/omb/memoranda/2016/m_16_21.pdf)
- metadata CMS would like to collect (e.g. FISMA level, repository host, group)
- required metadata outlined in the [SHARE IT ACT](https://www.congress.gov/bill/118th-congress/house-bill/9566/text/ih) (e.g. repository visibility, contract number)
- publiccode.yml metadata, an international metadata standard

By harmonizing various standards, this opens up the opportunity to share our work not just on an agency level but also on a national and international level.

### Fields

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
      <td><img src="assets/cms-logo.jpg" alt="CMS Logo"></td>
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
      <td>A list of enumerated values which describes the usage permissions for the release.</td>
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
      <td>The URL of the public release repository for open source repositories. This field is not required for repositories that are only available as government-wide reuse or are closed (pursuant to one of the exemptions).</td>
      <td></td>
    </tr>
    <tr>
      <td>vcs (version control system)</td>
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
      <td>platform</td>
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
      <td>Maintenance status</td>
      <td>
        - internal<br>
        - contract<br>
        - community<br>
        - none
      </td>
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
      <td>Tags associated with the project</td>
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
      <td><img src="assets/cms-logo.jpg" alt="CMS Logo"></td>
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
      <td><img src="assets/cms-logo.jpg" alt="CMS Logo"></td>
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
      <td><img src="assets/cms-logo.jpg" alt="CMS Logo"></td>
      <td>str</td>
      <td>FISMA security level <a href="https://security.cms.gov/learn/federal-information-security-modernization-act-fisma">link</a></td>
      <td>
        - low<br>
        - moderate<br>
        - high
      </td>
    </tr>
    <tr>
      <td>group</td>
      <td>required</td>
      <td><img src="assets/cms-logo.jpg" alt="CMS Logo"></td>
      <td>str</td>
      <td>Home Department / Org / Group associated with the project</td>
      <td></td>
    </tr>
    <tr>
      <td>subsetInHealthcare</td>
      <td>required</td>
      <td><img src="assets/cms-logo.jpg" alt="CMS Logo"></td>
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
      <td><img src="assets/cms-logo.jpg" alt="CMS Logo"></td>
      <td>arr</td>
      <td>Types of users who interact with the software</td>
      <td>
        - providers<br>
        - patients<br>
        - government
      </td>
    </tr>
    <tr>
      <td>repositoryHost</td>
      <td>required</td>
      <td><img src="assets/cms-logo.jpg" alt="CMS Logo"></td>
      <td>str</td>
      <td>Location where source code is hosted</td>
      <td>
        - github.com/CMSgov<br>
        - github.com/CMS-Enterprise<br>
        - github.com/DSACMS<br>
        - github.cms.gov<br>
        - CCSQ GitHub
      </td>
    </tr>
    <tr>
      <td>maturityModelTier</td>
      <td>required</td>
      <td><img src="assets/cms-logo.jpg" alt="CMS Logo"></td>
      <td>int</td>
      <td>Maturity model tier</td>
      <td>1, 2, 3, 4</td>
    </tr>
    <tr>
      <td>contractNumber</td>
      <td>required</td>
      <td>📜</td>
      <td>int</td>
      <td>Contract number</td>
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
      <td>reuseFrequency/forks <br> reuseFrequency/downloads</td>
      <td>required</td>
      <td>📜</td>
      <td>obj</td>
      <td>Measures frequency of code reuse in various forms</td>
      <td></td>
    </tr>
    <tr>
      <td>feedbackMechanisms</td>
      <td>required</td>
      <td>📜</td>
      <td>arr</td>
      <td>Array of methods repositories receive feedback. Default value is the URL to GitHub repository issues</td>
      <td>
        - Submitting issues to repo<br>
        - Submitting PRs to repo<br>
        - Project website<br>
        - Email
      </td>
    </tr>
    <tr>
      <td>project</td>
      <td>required</td>
      <td><img src="assets/cms-logo.jpg" alt="CMS Logo"></td>
      <td>arr</td>
      <td>Maps repositories to projects</td>
      <td>bluebutton, codejson</td>
    </tr>
    <tr>
      <td>systems</td>
      <td>optional</td>
      <td><img src="assets/cms-logo.jpg" alt="CMS Logo"></td>
      <td>arr</td>
      <td>Maps repositories to CMS systems</td>
      <td>idr</td>
    </tr>
    <tr>
      <td>upstream</td>
      <td>optional</td>
      <td><img src="assets/cms-logo.jpg" alt="CMS Logo"></td>
      <td>arr</td>
      <td>List of upstream repos used</td>
      <td>augur, uswds</td>
    </tr>
  </tbody>
</table>
