# Ecore Documentation

This is a template repository for generating ecore documentation from ecore metamodels.
Documentation can be generated manually using [Nasdanika CLI](https://docs.nasdanika.org/nsd-cli/index.html) and then published to GitHub pages if desired.
It can also be generated using GitHub actions calling Nasdanika CLI. 

To use the first approach set up [GitHub Pages source](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site) to "Deploy from a branch", select a branch and then "docs" folder.

To use [publish with a GitHub Actions workflow](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site#publishing-with-a-custom-github-actions-workflow) set the source to "GitHub Actions".

The generator creates `my.drawio` Draw.io diagram and publishes it to the root of the site.
You can download it, edit it and include into the site. 
All of this can be done in the browser if you don't want to clone the repository to your local environment. 
To generate and commit doc stubs you will have to either clone the repository to you local environment or use [GitHub Codespaces](https://github.com/features/codespaces).

## Manual generation

Once you install Nasdanika CLI the first step isto generate the web site ([HTML Application](https://html-app.models.nasdanika.org/index.html)) model with [model/ecore/doc/save](https://docs.nasdanika.org/nsd-cli/nsd/model/ecore/doc/save/index.html) command pipeline:

```
nsd model My.ecore ecore doc --diagram=my.drawio --doc-stubs --doc-dir=doc save my.xmi
```

Remove `--diagram=my.drawio` if you've already generated a diagram file before and manually adjusted it. 
You may re-generate a diagram file if there are changes in the source file - added or deleted classifiers.

`--doc-stubs` option works with `--doc-dir`` option and tells the command to generate empty markdown files for model elements.
You can then write documentation file-by-file, possibly collaborating with others.

Then generate a web site from the XMI file using [model/labels/site](https://docs.nasdanika.org/nsd-cli/nsd/model/labels/site/index.html) command pipeline:

```
nsd model root-action.yml labels site -r=-1 -F page-template.yml docs
```

You can also mount it to a larger site.

## Action generation

GitHub actions generate a documentation site, a diagram, and a doc stubs zip:

* Documentation: https://nasdanika-templates.github.io/ecore-doc/index.html
* Generated diagram file: https://nasdanika-templates.github.io/ecore-doc/my.drawio
* Doc stubs zip: https://nasdanika-templates.github.io/ecore-doc/doc-stubs.zip - unzip and upload using GitHub Web interface if you are not using a local repository clone.

## SQL Metadata

Generation of SQL metadata documentation can be done by:

* Generating an ecore model from SQL metadata and then a documentation model using [sql/metadata/sql-to-ecore/ecore/doc/save](https://docs.nasdanika.org/nsd-cli/nsd/sql/metadata/sql-to-ecore/ecore/doc/save/index.html) command pipeline
* Generating and publishing a documentation site

## Upgrade to code generation

This template repository generates just documentation. 
You can "upgrade" it to also generate Java code and model documentation in addition to metamodel documentation.
You can use the [SQL Model](https://github.com/Nasdanika-Models/sql) as a template/reference.

