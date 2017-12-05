# Front-end handover (December 2017)

## Topics
* [Release procedure](#release-procedure)
* [API documentation](#api-documentation)
* [Plugins](#plugins)
* [Accounts](#accounts)
* [Contacts](#contacts)
* [D3 v4 roadmap](#d3-v4-roadmap)
* [Static content](#static-content)
* [Docker](#docker)
* [Remaining questions](#remaining-questions)

* Proxies
* Library
* Blogs
* Genome browser

## Release procedure
### Major/minor release
Suppose production branch is `v3.4` and the latest tag is `3.4.5`. Perform the following steps:
* On a new branch `v3.5` from `master`:
  * Bump version to 3.5.0 in `footer.html`
  * Invalidate cache in `index.html`
  * Tag `3.5.0`
  * Switch production branch to `v3.5` on Netlify and publish (remember to push tags and disable auto-publication)

### Patch/bugfix release
Suppose production branch is `v3.4` and the latest tag is `3.4.5`. Perform the following steps:
* On a new branch `bugfix` from current production:
  * Fix issues
  * Bump version to 3.4.6 in `footer.html`
  * Invalidate cache in `index.html`
  * Tag `3.4.6`
* Merge `bugfix` into `v3.4`
* Merge `v3.4` into `master`
* Publish on Netlify (remember to push tags and disable auto-publication)

## API documentation
The API documentation is managed by the back-end. Front-end loads the `swagger.yaml` file from `{api}/v3/platform/swagger`, which is displayed using the `angular-swagger-ui` module.

## Plugins
The webapp uses plugins written by the Open Targets team and by other parties, which are here divided into *internal* and *external*.

### Internal
* `cttv.api`
* `cttv.diseaseGraph`
* `cttv.flowerView`
* `cttv.genome`
* `cttv.spinner`
* `cttv.targetAssociationsBubbles`
* `cttv.targetAssociationsTree`
* `cttv.targetGeneTree`
* `ot.interactionsViewer`
* `viz_diseases`
* `tnt.ensembl`
* `tnt.genome`
* `tnt.rest`
* `tnt.tooltip`
* `tnt.utils`
* `tntvis`

### External
* `bio-pv`
* `reactome`
* `expression-atlas-heatmap`

## Accounts
Open Targets uses the following accounts.
  * Piwik - Usage statistics
  * Circle CI - Unit testing/linting
  * Ghost Inspector - End-to-end testing
  * Netlify - Webapp hosting and DNS mapping

## Contacts
The following people are useful contacts in other EBI teams. Many have worked on the plugins provided by their respective teams and used in Open Targets.
* Uniprot - Xavier Watkins
* Reactome - Antonio Fabregat
* Expression Atlas - Alfonso Munoz Pomer
* ChEMBL - Patricia Vento

## D3 v4 roadmap
Most plugins have a branch which supports version 4.0 of `d3`. The `bubblesView` is the main outstanding plugin requiring support.

## Static content
Other members of the Open Targets team occasionally need to update static content. This seems to be mainly done by Denise, affecting pages such as:
* `variants`
* `scoring`
* `faq`
* `data-sources`
* `about`

## Docker
There is a `Dockerfile` and `docker-entrypoint.sh` in the webapp repository, but these are not used in the public site, which is hosted on Netlify. They should nonetheless be kept for other instances and for users wishing to run their own version locally.

## Remaining questions

