# Naftiko Fleet — Community Edition

[![License](https://img.shields.io/badge/License-Freeware_EULA-blue.svg)](https://github.com/naftiko/fleet/blob/main/LICENSE.md)

Welcome to the **Naftiko Fleet**, the product platform for [Spec-Driven Integration](https://shipyard.naftiko.io/docs/1.0.0-alpha3/concepts/spec-driven-integration/) — reinventing API integration for the AI era with governed, versatile **capabilities** that streamline the API sprawl created by massive SaaS and microservices growth.

> A *fleet* is what you call a group of ships sailing together — here, a group of capabilities running and governed as one.

<img src="https://naftiko.github.io/docs/images/technology/fleet-overview.png" width="700">

## What the Fleet is

The Naftiko Fleet delivers Spec-Driven Integration **end to end**, from authoring a capability to running, governing, and orchestrating it at scale. It is composed of **six focused components** that each own one step of the workflow, and is available in **three editions** — Community, Standard, and Enterprise.

```text
 Discover ──► Author ──► Lint ──► Run ──► Govern ──► Orchestrate
    │           │         │        │         │             │
 Shipyard    Crafter   Polychro  Ikanos    Warden      Skipper
    │           │         │        │         │             │
  (docs &     (UI &     (CI &    (engine   (policy      (fleet-wide
   search)    spec      local    runtime)  enforcement) routing &
              editor)   valid.)                         placement)
```

Crafter generates specs that Ikanos runs and Polychro validates. Warden sits between Crafter and Ikanos in regulated environments, enforcing policy before specs are deployed. Skipper coordinates many Ikanos processes across many clusters. Shipyard is where you learn about all of them — and soon, where you try them in a hosted Playground.

> **Fleet vs fleet** — Capitalised **Fleet** always refers to the Naftiko Fleet, the product platform. Lowercase **fleet** refers to a group of capabilities running together at runtime (a *ship cluster*). Skipper orchestrates the latter on behalf of the former.

## What the Fleet is *not*

- **Not a single monolithic product.** The Fleet is six independently usable components, not one binary. You can adopt Ikanos and Polychro on their own under Apache 2.0, and add Crafter, Warden, or Skipper when you need them.
- **Not a paywall on the essentials.** Every edition ships *every* component. **Ikanos** and **Polychro** are fully open-source — the same Apache 2.0 binary in every edition, with no premium features, forever. Editions only add team- and enterprise-grade features on top of Shipyard, Crafter, Warden, and Skipper.
- **Not an all-or-nothing platform.** Components compose, but none requires the others. Use Polychro in CI without Ikanos, run Ikanos without Skipper, or document with Shipyard alone — each is valuable standalone.

## Components

With the Alpha 3 release, all six components are shipping software.

| Component | Role | Edition / Version |
|---|---|---|
| [Shipyard](https://shipyard.naftiko.io/docs/1.0.0-alpha3/) | Documentation hub for the Fleet — soon a hosted Playground and AI-assisted search | Live |
| [Ikanos](https://shipyard.naftiko.io/docs/1.0.0-alpha3/ikanos/) | The capability engine — runs a Naftiko spec as a multi-protocol server (100% OSS) | v1.0.0-alpha3 |
| [Polychro](https://shipyard.naftiko.io/docs/1.0.0-alpha3/polychro/) | The deterministic AI-era linter for YAML, JSON, and Markdown (100% OSS) | v1.0.0-alpha3 |
| [Crafter](https://shipyard.naftiko.io/docs/1.0.0-alpha3/fleet/crafter/) | Capability builder — local-first today, hosted web UI in Standard | v1.0.0-alpha3 |
| [Warden](https://shipyard.naftiko.io/docs/1.0.0-alpha3/fleet/warden/) | Capability governance and policy enforcement | v1.0.0-alpha3 |
| [Skipper](https://shipyard.naftiko.io/docs/1.0.0-alpha3/fleet/skipper/) | Fleet-wide orchestration across teams, regions, and compliance domains | v1.0.0-alpha3 |

## Editions

The three editions do not differ by *which* components they include — every edition ships every component. What changes is the set of premium features layered on top of Shipyard, Crafter, Warden, and Skipper as you move up.

| Edition | For | Deployment | What you get |
|---|---|---|---|
| **Community** | Open-source developers, individuals, OSS projects | Self-hosted | Every component, no premium add-ons — free for personal and internal business use |
| **Standard** | Teams and small organizations | Self-hosted or cloud | Team-grade features for Shipyard, Crafter, Warden, Skipper |
| **Enterprise** | Regulated enterprises | Self-hosted, air-gapped, or managed | Governance + scale for Shipyard, Crafter, Warden, Skipper |

> Ikanos and Polychro are committed to staying **100% Apache 2.0 OSS** — identical in every edition, with no premium features and no commercial add-ons.

For the full per-component premium-feature matrix and detailed edition pages, see [Fleet → Editions](https://shipyard.naftiko.io/docs/1.0.0-alpha3/fleet/editions/) on the Shipyard.

## Licensing at a glance

- The **Naftiko Fleet — Community Edition** is distributed under a **Freeware (Closed Source) EULA** — free of charge for personal or internal business use. See [the EULA](https://github.com/naftiko/fleet/blob/main/LICENSE.md).
- **Ikanos** and **Polychro** are released as fully **Apache 2.0** open-source projects in their own repositories. You can use them standalone — outside of the Fleet — under Apache 2.0 terms.
- **Standard** and **Enterprise** premium features are dual-licensed under the **Naftiko Commercial License**.

> The full three-license picture is on the [License page](https://shipyard.naftiko.io/docs/1.0.0-alpha3/fleet/license/).

***

## :anchor: Dive deeper on the Shipyard

The complete, always-up-to-date Fleet documentation lives on the **Naftiko Shipyard**. Start here and keep exploring:

- :compass: [Concepts — Spec-Driven Integration](https://shipyard.naftiko.io/docs/1.0.0-alpha3/concepts/spec-driven-integration/)
- :ship: [Fleet Overview](https://shipyard.naftiko.io/docs/1.0.0-alpha3/fleet/)
- :anchor: [Ikanos — the capability engine](https://shipyard.naftiko.io/docs/1.0.0-alpha3/ikanos/)
- :mag: [Polychro — the spec linter](https://shipyard.naftiko.io/docs/1.0.0-alpha3/polychro/)
- :hammer_and_wrench: [Crafter — the capability builder](https://shipyard.naftiko.io/docs/1.0.0-alpha3/fleet/crafter/)
- :shield: [Warden — governance & policy](https://shipyard.naftiko.io/docs/1.0.0-alpha3/fleet/warden/)
- :sailboat: [Skipper — fleet-wide orchestration](https://shipyard.naftiko.io/docs/1.0.0-alpha3/fleet/skipper/)
- :moneybag: [Editions](https://shipyard.naftiko.io/docs/1.0.0-alpha3/fleet/editions/)
- :ocean: [FAQ](https://shipyard.naftiko.io/docs/1.0.0-alpha3/fleet/faq/)
- :mega: [Releases](https://shipyard.naftiko.io/docs/1.0.0-alpha3/fleet/releases/)
- :telescope: [Roadmap](https://shipyard.naftiko.io/docs/1.0.0-alpha3/fleet/roadmap/)
- :scroll: [License](https://shipyard.naftiko.io/docs/1.0.0-alpha3/fleet/license/)

## :video_game: Try it in the Playground

Want to see the Fleet in action without installing anything? The upcoming **Shipyard Playground** lets you author a capability with **Crafter**, lint it live with **Polychro**, and serve it with **Ikanos** — all from your browser. Keep an eye on the [Shipyard](https://shipyard.naftiko.io/docs/1.0.0-alpha3/) for its release.

***

Please join the community of users and contributors in [this GitHub Discussion forum!](https://github.com/orgs/naftiko/discussions)

<img src="https://naftiko.github.io/docs/images/navi/navi_hello.svg" width="50">
