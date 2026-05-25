# Nixpacks (nixpacks)
Nixpacks is an open-source build tool from Railway that converts application source code into OCI-compliant Docker images by combining language-specific providers, Nix packages, and Buildkit. It inspects a project, selects one or more providers (Node, Python, Ruby, Go, Java, Rust, PHP, Elixir, Deno, Crystal, .NET, Swift, Scala, Dart, Haskell, Gleam, Zig, Clojure, and more), and produces a reproducible build plan of setup, install, build, and start phases. Plans can be customized via `nixpacks.toml`, CLI flags, or environment variables. The project is MIT licensed and currently in maintenance mode; Railway recommends Railpack as the actively developed successor.

**URL:** [Visit APIs.json URL](https://nixpacks.com)

## Scope

- **Type:** Index
- **Position:** Consuming
- **Access:** 3rd-Party

## Tags:

 - Build Tool, Buildpacks, Docker, OCI, Nix, Nixpkgs, Container Image, Application Packaging, Railway, Open Source, Rust, DevOps, Platform Engineering, PaaS

## Timestamps

- **Created:** 2026-05-24
- **Modified:** 2026-05-24

## APIs

### Nixpacks CLI
The Nixpacks command-line interface is the primary interface for generating build plans and producing Docker images from application source. Core commands include `nixpacks plan`, `nixpacks build`, and `nixpacks detect`. The CLI accepts inline overrides for install, build, and start commands, Nix and apt packages, environment variables, the base build image, and a separate runtime image, and is distributed as a single Rust binary via Homebrew, install script, Docker image, and GitHub releases.

**Human URL:** [https://nixpacks.com/docs/cli](https://nixpacks.com/docs/cli)

#### Tags:

 - CLI, Build, Plan, Detect

#### Properties

- [Documentation](https://nixpacks.com/docs/cli)
- [Getting Started](https://nixpacks.com/docs/getting-started)
- [SourceCode](https://github.com/railwayapp/nixpacks)
- [Install](https://nixpacks.com/docs/install)

### Nixpacks Build Plan
The Nixpacks build plan is the JSON representation of how a source directory will be turned into a container image. A plan declares the list of providers, top-level `variables`, `staticAssets`, `buildImage`, and an ordered set of phases (`setup`, `install`, `build`, plus any user-defined phases) along with a `start` phase. Each phase carries `cmds`, `nixPkgs`, `nixLibs`, `aptPkgs`, `dependsOn`, `cacheDirectories`, `onlyIncludeFiles`, and `paths`. Plans can be saved and replayed via `nixpacks build --plan plan.json`.

**Human URL:** [https://nixpacks.com/docs/how-it-works](https://nixpacks.com/docs/how-it-works)

#### Tags:

 - Build Plan, JSON, Phases, Reproducible Builds

#### Properties

- [Documentation](https://nixpacks.com/docs/how-it-works)
- [Reference](https://nixpacks.com/docs/configuration/file)

### Nixpacks Configuration File (nixpacks.toml)
Projects override or extend the auto-detected build plan by committing a `nixpacks.toml` file at the root of the repository. The file mirrors the build-plan structure with `providers`, `buildImage`, `variables`, `staticAssets`, `[phases.<name>]` tables, and a `[start]` table. The `"..."` token can be used inside array fields to extend rather than replace provider-supplied values.

**Human URL:** [https://nixpacks.com/docs/configuration/file](https://nixpacks.com/docs/configuration/file)

#### Tags:

 - Configuration, TOML, Phases, Customization

#### Properties

- [Documentation](https://nixpacks.com/docs/configuration/file)
- [Reference](https://nixpacks.com/docs/configuration/environment)

### Nixpacks Language Providers
Providers are the pluggable modules that detect a language or framework in the source directory and contribute their portion of the build plan. Nixpacks ships with providers for Node, Python, Ruby, Go, Java, Rust, PHP, Elixir, Deno, Crystal, C#/.NET, Swift, Scala, Dart, Haskell, Gleam, Zig, Clojure, Lunatic, Cobol, Scheme, F#, and a Staticfile provider. Multiple providers can compose in a single image.

**Human URL:** [https://nixpacks.com/docs/providers](https://nixpacks.com/docs/providers)

#### Tags:

 - Providers, Detection, Languages, Frameworks

#### Properties

- [Documentation](https://nixpacks.com/docs/providers)
- [SourceCode](https://github.com/railwayapp/nixpacks/tree/main/src/providers)

### Nixpacks GitHub Action
The official GitHub Action wraps the Nixpacks CLI so CI pipelines can build and optionally push OCI images directly from a workflow without installing Nixpacks manually. The action accepts the same overrides as the CLI and is commonly paired with Docker login actions to publish images to GHCR, Docker Hub, or any OCI-compliant registry.

**Human URL:** [https://github.com/iloveitaly/github-action-nixpacks](https://github.com/iloveitaly/github-action-nixpacks)

#### Tags:

 - GitHub Actions, CI/CD, Build, Container Image

#### Properties

- [SourceCode](https://github.com/iloveitaly/github-action-nixpacks)
- [Documentation](https://nixpacks.com/docs/guides/github-actions)

## Common Properties

- [Website](https://nixpacks.com)
- [Documentation](https://nixpacks.com/docs)
- [Getting Started](https://nixpacks.com/docs/getting-started)
- [Install](https://nixpacks.com/docs/install)
- [GitHub Organization](https://github.com/railwayapp)
- [GitHub Repository](https://github.com/railwayapp/nixpacks)
- [SourceCode](https://github.com/railwayapp/nixpacks)
- [License](https://github.com/railwayapp/nixpacks/blob/main/LICENSE)
- [Issues](https://github.com/railwayapp/nixpacks/issues)
- [Change Log](https://github.com/railwayapp/nixpacks/releases)
- [Container Image](https://github.com/railwayapp/nixpacks/pkgs/container/nixpacks)
- [Provider — Railway](https://railway.app)
- [Successor — Railpack](https://github.com/railwayapp/railpack)
- [Twitter](https://twitter.com/Railway)

## Maintainers

**FN:** Kin Lane

**Email:** kin@apievangelist.com
