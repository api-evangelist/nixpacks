# Nixpacks (nixpacks)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
