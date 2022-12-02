# About

This dbt project does not run!  It just acts as a demonstration of GitHub pages. Assume the docs were created
prior earlier in the pipeline, and now we want to see them hosted on GitHub.

GitHub Pages is limited to serving static content from either the root `/` or `/docs`.
DBT Core is limited to outputting its static documentation to `/target`. ([Issue](https://github.com/dbt-labs/dbt-core/issues/4096))
URL Limitations?? Does a user have ghpages, or a repo? Repo. We're good.

To get these to play nice together, a GitHub Action moves the documentation after its creation, making it available to GitHub Pages.

1. DBT command creates documentation, outputs them to `/target`
2. GHAction moves docs to `/docs` and commits them. This action is run on commit (or when /target changes?)
3. GHPages serve the fresh content from TODO URL.

Three files make up DBT Docs:
 - `/target/index.html`
 - `/target/manifest.json`
 - `/target/catalog.json`

The GitHub Action that moves them: todo