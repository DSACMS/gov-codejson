## agency-index.json

The SHARE IT Act requires federal agencies to publish metadata for their software projects. This metadata is compiled into an **agency-index.json** file, which serves as a centralized inventory of the agency's software portfolio.

View the agency-index.json schema here: https://github.com/DSACMS/gov-codejson/tree/main/schemas/agency-index/schema-2.0.0.json

To create an agency-index.json:
1. Identify GitHub organizations and other platforms where source code is hosted
2. Generate the agency-index.json using the tools below. Learn more about usage in [procedures.md](https://github.com/DSACMS/gov-codejson/blob/main/docs/procedures.md#generate-an-agency-indexjson-file-for-agencies)
  - [index-generator-website](https://dsacms.github.io/index-generator-website/)
  - [index-generator python tool](https://github.com/DSACMS/codejson-index-generator)
3. Provide the index at:
  - Agency's top level domain (TLD)
  - A GitHub repository

More examples of agency index files can be found here: https://github.com/DSACMS/code-gov/tree/main/agency-indexes