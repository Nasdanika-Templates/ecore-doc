# Ecore Documentation

This is a template repository for generating ecore documentation from multiple sources - ecore, xcore, plantuml, xsd.
Documentation can be generated manually using [Nasdanika CLI](https://docs.nasdanika.org/nsd-cli/index.html) and then published to GitHub pages if desired.
It can also be generated using GitHub actions calling Nasdanika CLI. 
This template uses the second approach and generates documentation for several supported sources as explained below.
You can choose one of them and edit the [.github/workflows/site.yml](.github/workflows/site.yml) to generate documentation just for the type you need
and publish to the root of the pages.

The generator creates and publishes Draw.io diagrams.
You can edit it and include into the site. 
All of this can be done in the browser if you don't want to clone the repository to your local environment. 
To generate and commit doc stubs you will have to either clone the repository to you local environment or use [GitHub Codespaces](https://github.com/features/codespaces).

## Ecore

```
model My.ecore ecore doc --diagram=my.drawio --doc-stubs --doc-dir=doc save my.xmi
```


mounting to other sites,

* Documentation: https://nasdanika-templates.github.io/ecore-doc/index.html
* Generated diagram file: https://nasdanika-templates.github.io/ecore-doc/my-ecore.drawio



TODO...

* Manual generation -> Pages
* Action generation

## Xcore

## PlantUML Class Diagrams

## XML Schemas

## SQL Metadata

Generation of SQL metadata documentation is not part of this repository.
It can be done by generating an ecore model from SQL metadata and then a documentation model using [sql/metadata/sql-to-ecore/ecore/doc/save](https://docs.nasdanika.org/nsd-cli/nsd/sql/metadata/sql-to-ecore/ecore/doc/save/index.html) command pipeline and then generating and publishing a documentation site.

## Upgrade to code generation

This template repository generates just documentation. 
You can "upgrade" it to also generate Java code and model documentation in addition to metamodel documentation.
You can use the [SQL Model](https://github.com/Nasdanika-Models/sql) as a template/reference.

