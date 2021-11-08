# scanner-demo

Runs AppMaps scanners on sample projects, and uploads the output data to [Google Cloud Storage](https://console.cloud.google.com/storage/browser/appland-ci-artifacts/scanner-demo/main).

# Artifacts

Each artifact is a tar-gzip (tarball), so that all the data can be downloaded as one unit.

* `[project].findings.tgz` Scanner findings in JSON, plus AppMap file for each finding.
* `[project].appmaps.tgz` All AppMaps generated for the project by the build. This may be a subset of all the project tests, depending on how the build is run.

# Adding a project

Clone the new project as a Git submodule.

Configure .travis.yml to build the project.

Note that artifacts are **only uploaded from builds of the main branch**. This is a Travis limitation for security purposes. So, you will need to get your branch working and then merge to `main` in order to get artifact uploads + downloads.
