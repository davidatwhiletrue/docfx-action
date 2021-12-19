# docfx-action
A GitHub action to run [DocFX](https://dotnet.github.io/docfx/) and generate a documentation site in GitHub Pages.

This is a combination of two existing action that already work super, but executed in one single step:

* https://github.com/nikeee/docfx-action
* https://github.com/maxheld83/ghpages

## Usage
```yaml
jobs:
  generate_and_publish_docs:
    runs-on: ubuntu-latest
    name: Generate and publish the docs
    steps:
    - uses: actions/checkout@v1
      name: Checkout code
    - uses: davidatwhiletrue/docfx-action@v1.0.0
      name: Build and Publish Documentation
      with:
        args: path/to/your/docfx.json
      env:
        BUILD_DIR: _site # docfx's default output directory is _site
        GH_PAT: ${{ secrets.GH_PAT }} # See https://github.com/maxheld83/ghpages
```

In general, to run `docfx <something>`, you can use:
```yaml
    - uses: nunit/docfx-action@v1.0.0
      with:
        args: <something>
```
