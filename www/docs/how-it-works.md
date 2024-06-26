# How it works

GoReleaser's goal is to automate most of the boring work you'll have while
releasing software, ideally using sensible defaults and making the most common
use cases easy.

GoReleaser expects a couple of things:

- a `.goreleaser.yaml` file with the configuration (see the
  [customization section](./customization/index.md) for more info)
- a clean working tree
- a SemVer-compatible version (e.g. `10.21.34-prerelease+buildmeta`)

And that's it.

## What happens when you release

A GoReleaser run is split into 4 major steps:

- **defaulting**: configures sensible defaults for each step
- **building**: builds the binaries, archives, packages, Docker images, etc
- **publishing**: publishes the release to the configured SCM, Docker
  registries, blob storages...
- **announcing**: announces your release to the configured channels

Some steps might be skipped with `--skip` flags (check the
[command line docs](./cmd/goreleaser.md) for details).

If any of the previous steps fails, the next steps will not run.
