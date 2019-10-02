# Gloo docs

## Deploying to a test site

```
make serve-site
```

## Notes about the build process

- we want documentation to be avaailable in the form of docs.solo.io/gloo/latest/... and also as docs.solo.io/gloo/<some_version/...
  - during the release process, we will replace the prior "latest" build with the new build
  - if we want to make a particular version of the docs available for a longer timespan, we can host the version-scoped image
- we currently emit two images for each Gloo release
  - a version of the docs that is served under domain.com/gloo/latest/
  - a version of the docs that is served under domain.com/gloo/[version]/
- the two images are built in the following temporary directories
  - site-latest/
  - site-versioned/
- in the Dockerfile, we copy the appropriate directories to a nested directory corresponding to the prefix path
- all urls are scoped relative to the prefix path
- if you want to run locally, do: `make serve-site` which will build and serve the site from the site/ directory, with no prefix


