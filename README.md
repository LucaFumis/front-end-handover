# Front-end handover (December 2017)

## Topics
* [Release procedure](#release-procedure)
* [Contacts](#contacts)
* External plugins
* Proxies
* Accounts
  * Piwik
  * Ghost Inspector
  * Netlify
  * DNS
* API documentation
* Content maintained by Denise
* d3v4 roadmap
* Circle CI
* Library
* Docker
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

## Contacts
The following people are useful contacts in other EBI teams. Many have worked on the widgets provided by their respective teams and used in Open Targets.
* Uniprot - Xavier Watkins
* Reactome - Antonio Fabregat
* Expression Atlas - Alfonso Munoz Pomer
* ChEMBL - Patricia Vento

