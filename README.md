# Ecore Documentation

This is a template repository for generating ecore documentation from multiple sources - ecore, xcore, plantuml, xsd.
Documentation can be generated manually using [Nasdanika CLI](https://docs.nasdanika.org/nsd-cli/index.html) and then published to GitHub pages if desired.
It can also be generated using GitHub actions calling Nasdanika CLI. 
This template uses the second approach and generates documentation for several supported sources as explained below.
You can choose one of them and edit the [.github/workflows/site.yml](.github/workflows/site.yml) to generate documentation just for the type you need
and publish to the root of the pages.

The generator creates and publishes ad Draw.io diagram.
You can edit it and include into the site. All of this can be done in the browser if you don't want to clone the repository to your local environment. 

```
model My.ecore ecore doc --diagram=my.drawio --doc-stubs --doc-dir=doc save my.xmi
```


TODO...

* Manual generation -> Pages
* Action generation

Upgrade to code generation, ...

