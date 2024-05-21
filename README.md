[![Package Status](https://github.com/bcgov/mlg-test-repo15/actions/workflows/publish.yaml/badge.svg)](https://github.com/bcgov/mlg-test-repo15/actions/workflows/publish.yaml)


# mlg-title-test

mlg desc test

## About

This is a default [README.md](README.md) file generated by the template. Customize it for your project.


## Adding documentation

The homepage of your documentation is in the [docs/index.md](docs/index.md) file. Edit it to suit your usage. Warning: do not delete this file. 

Add documentation pages by  adding more markdown (.md) files to the [docs](docs) folder.

## Table of contents

The Table of Contents on the right is dynamically generated based on the set of hierarchy
of headings in your markdown files. Only use one H1 (`#` in Markdown) per file.

## Site navigation

It is optional, but ***highly recommended*** that you create define the navigation structure for your documentation by creating a `nav` section in your [mkdocs.yml](mkdocs.yml) file. Without a `nav` section,  navigation for your documentation will be dynamically created when viewed within DevHub, but you won't have control over the order in which the pages show and the text will be generated based on the headings in the pages themselves.

Creating a `nav` section will allow you to completely control how the navigation for your documentation displays in DevHub, including the text that is shown, grouping pages in categories and sub-categories and including links to external content.

We've includes some example `mkdocs.yml` files below which demonstrate how to configure the `nav` section. You may also wish to consult the [MkDocs documentation](https://www.mkdocs.org/user-guide/writing-your-docs/#configure-pages-and-navigation) for detailed information about navigation and other aspects of mkdocs.yml.

### `nav` with categories

Below is an example of a `mkdocs.yml` file with a `nav` section. This `nav` section is structure to arrange the files in categories. In this case the categories are `Getting Started` and `Usage`.

```yaml
site_name: My TechDocs
site_description: Documentation for my project
docs_dir: "docs"
edit_uri: edit/main/docs/
plugins:
    - techdocs-core
    - ezlinks
markdown_extensions:
    - markdown_inline_mermaid
    - md_in_html
    -   mkpatcher:
            location: patcher.py
nav:
- Getting Started:
  - Introduction: index.md
  - Create an account: account.md
  - Setup environment: setup.md
- Usage:
  - Deploy locally: local.md 
  - Deploy to OpenShift: openshift.md
```

### Flat `nav`

Below is another example of a `mkdocs.yml` file. It does not use categories to arrange the documentation pages.

```yaml
site_name: My Techdocs
site_description: Documentation for my project
docs_dir: "docs"
plugins:
    - techdocs-core
    - ezlinks
markdown_extensions:
    - markdown_inline_mermaid
    - md_in_html
    -   mkpatcher:
            location: patcher.py
nav:
    - Introduction: index.md
    - Create an account: account.md
    - Setup environment: setup.md
    - Deploy locally: local.md
    - Deploy to OpenShift: openshift.md
```

## Notes

Note that MkDocs uses `mkdocs.yml`, not `mkdocs.yaml`, although both appear to work.
Refer to the [mkdocs user guide](https://www.mkdocs.org/user-guide/configuration/) for more details.

## Previewing documentation locally

You will likely want to preview your documentation on your computer. Follow [these instructions](https://github.com/bcgov/devhub-techdocs-publish/blob/main/docs/index.md#how-to-use-the-docker-image-to-preview-content-locally) to do so.

## Building and publishing your documentation

The [GitHub Action workflow file](.github/workflows/publish.yaml) can validate, build (produce browser-friendly HTML from Markdown) and publish your documentation to DevHub automatically.  Initially, it is set up just to validate and build your documentation. 

The portion of the workflow file that publishes your documentation is commented out because it requires addition set up with the Developer Experience team. When you'd like to have your documentation published in DevHub, [contact the Developer Experience Team](mailto:developer.experience@gov.bc.ca) who will work with you to set things up. 

### The publishing workflow

DevHub has a "preview" environment and a production environment, and once the Developer Experience team has you set up, and you've uncommented the publishing sections in the [workflow file](.github/workflows/publish.yaml) you'll be in control of how and when your content is published to each. You'll be able to control this by modifying the [workflow file](.github/workflows/publish.yaml) to suit your process and team.

The configuration provided in the [workflow file](.github/workflows/publish.yaml) behaves as follows: 

* A pull request to your repo will build and publish the code to the [DevHub preview](https://dev.developer.gov.bc.ca) site. This is a development site where you can preview your changes.
* A push to the `main` branch in your repository (a direct push or a PR merge) will publish the code to the [production DevHub website](http://developer.gov.bc.ca).

## Getting help or reporting an issue

To report bugs/issues/features requests, please email the Developer Experience team at [Developer.Experience@gov.bc.ca](mailto:Developer.Experience@gov.bc.ca)

The full documentation for MkDocs (which is powering the DevHub TechDocs function) is at the [MkDocs website](https://www.mkdocs.org/user-guide/writing-your-docs/). Note that not all content on the site will be applicable to DevHub's use of MkDocs.

## Contributing
If you would like to contribute, please see our [contributing](CONTRIBUTING.md) guidelines.

Please note that this project is released with a [Contributor Code of Conduct](CODE-OF-CONDUCT.md). By participating in this project you agree to abide by its terms.

## License

© 2024 Province of British Columbia

Refer to the [LICENSE](LICENSE.md) file for more information.

