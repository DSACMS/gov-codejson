# Procedures

The CMS Open Source Program Office developed various tools that can automate detecting, adding, and updating metadata to repositories.

## Creating a code.json file

### Using repo-scaffolder

[repo-scaffolder](https://github.com/DSACMS/repo-scaffolder) is a tool for creating repositories that adhere to repository hygiene standards. It provides file templates detailing project information, contributing guidance, maintainer roles, community involvement, and **project metadata**.

For repositories created using repo-scaffolder, the tool can assist with adding code.json to the repository. Navigate to your project's `.github` directory and run the following cookiecutter command. You will be asked questions about the project in order to collect and store this metadata in code.json.

```
cookiecutter . --directory=codejson
```

For more information on repo-scaffolder, check out the [documentation](https://github.com/DSACMS/repo-scaffolder?tab=readme-ov-file#metadata-collection-using-codejson).

### Using form site

Users can fill out a web form that creates a code.json file to be uploaded to a project's source code repository: https://dsacms.github.io/codejson-generator.

## Updating project metadata

<!-- TODO: Add explainer on codejson-index-generator -->
