<div align="center">

<img src="assets/orrery-banner.svg" width="100%" alt="Alfie Coxon — governed multi-agent AI systems" />

<br/>

### I don’t just *use* AI — I run fleets of it like an engineering org.

Written briefs · hostile critique loops · hard human gates · autonomy made safe by construction.

<br/>

![Focus](https://img.shields.io/badge/focus-agentic_systems_%26_AI_safety-38e1c4?style=for-the-badge&labelColor=0e1430)
![Approach](https://img.shields.io/badge/approach-governed_autonomy-6aa6ff?style=for-the-badge&labelColor=0e1430)

![Open to](https://img.shields.io/badge/open_to-AI_software%2C_engineering_%26_research-f6b64a?style=for-the-badge&labelColor=0e1430)

</div>

---

## ✦ Featured — ORRERY

> **A governed, local-first, multi-agent / multi-model AI workflow manager.**
> It turns plain-English requests into *verified* work by orchestrating agents under strict
> governance — hard budgets, an un-overridable human approval gate, and a deterministic,
> append-only, event-sourced spine you can always replay and trust.

<div align="center">

![Rust](https://img.shields.io/badge/Rust-000000?style=flat-square&logo=rust&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![Tauri](https://img.shields.io/badge/Tauri-24C8DB?style=flat-square&logo=tauri&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB)
![Tests](https://img.shields.io/badge/tests-1%2C000%2B-2ea043?style=flat-square)
![Determinism](https://img.shields.io/badge/replay-byte--identical-6aa6ff?style=flat-square)
![Status](https://img.shields.io/badge/private_repo-source_gated-8a8f9c?style=flat-square)

</div>

**The top-level run** — a request flows left-to-right, orchestrated across model tiers, fenced by governance, recorded on one event spine, and watched live in the workbench:

```mermaid
flowchart LR
    U(["Plain-English<br/>request"]) --> PIPE
    subgraph SIDE["Sidecar — TypeScript orchestration engine"]
      direction TB
      PIPE["Ultracode pipeline<br/>triage · clarify · spec · route<br/>plan · execute · verify · handoff"]
      GATE["Model gateway<br/>Fable-5 plan · Opus exec · fleets"]
      PIPE <--> GATE
    end
    subgraph GOV["Governance — safe by construction"]
      direction TB
      SG["Sacred gate<br/>un-overridable human approval"]
      BD["Hard budget ceilings"]
      VA["Encrypted vault<br/>Argon2id + SQLCipher · JIT decrypt"]
    end
    PIPE --> GOV
    SIDE -- "every effect is an event" --> SPINE[("Append-only event spine<br/>deterministic · replayable byte-for-byte")]
    SPINE --> UI["Mission-control workbench<br/>pure projection · live + replay"]
    HOST["Tauri / Rust host shell"] -.-> SIDE
```

<details>
<summary><b>🛡 Governance — where autonomy ends, on purpose</b></summary>

<br/>

- **Sacred gate** — destructive actions park for a human; no model can talk its way past it.
- **Hard budgets** — token/step ceilings **block on breach** instead of silently truncating.
- **Capability is never inferred** — tool authority comes only from an explicit granted allowlist, carried by least-privilege spawn envelopes through a five-plane permission gate.
- **Encrypted vault** — provider keys live under Argon2id + SQLCipher, decrypt just-in-time, and never touch disk in plaintext.

</details>

<details>
<summary><b>🎞 Determinism — the audit trail and the program are the same object</b></summary>

<br/>

- **Append-only spine, single per-run writer** — every effect is an event.
- **Pure projections** — every view is a fold over the event bus; **no wall-clock or RNG** in anything a reducer sees.
- **Replay is byte-identical** — re-run any log and get the exact same state, every time.
- **Rust ↔ TypeScript hash parity** — the `Event` schema is byte-for-byte identical across the host and the engine.

</details>

<details>
<summary><b>🧩 Architecture — four surfaces, one contract</b></summary>

<br/>

| Surface | Role |
|---|---|
| `src-tauri/` + `crates/` | Tauri / Rust host shell + the encrypted credential vault |
| `sidecar/` | TypeScript orchestration engine: event spine, Ultracode pipeline, model gateway, governance, budgets, tool suite, shared memory |
| `frontend/` | React / WebGL *mission-control* workbench — a pure projection consumer; mutates state only via `POST /command` |
| `packages/` | the shared `Event` schema — the spine contract, byte-parity across Rust and TS |

Verified by one gate: `pnpm verify` → typecheck · tests · lint · secrets-grep · Rust↔TS parity · replay-determinism.

</details>

> [!NOTE]
> ORRERY’s source is private. Shown here at the top level — architecture, guarantees, and capabilities — with no implementation exposed. Walkthrough or gated access available on request.

---

## What else I build

Autonomy made safe by construction, across a portfolio of live and study systems:

| Project | What it is |
|---|---|
| **Autonomous content engines** | 4 self-running publishing engines (~50 crons) behind a hard publish gate |
| **Bookings-recovery system** | turns missed enquiries into recovered revenue, end-to-end |
| **Assistant SaaS** | a hosted AI assistant product |
| **Pattern studies** | two focused deep-dives into agentic patterns |

<sub>Most are private or gated. Details and demos available on request.</sub>

---

## How I work

- **Briefs before code** — every build starts from a written mission + invariants.
- **Hostile critique loops** — findings are adversarially verified before they’re trusted.
- **Human gates everywhere** — zero unattended commits; destructive actions always stop for a person.
- **Proof, not vibes** — 1,000+ tests, deterministic replay, and a single CI gate that must pass.

---

## Toolbox

<div align="center">

![Rust](https://img.shields.io/badge/Rust-000000?style=for-the-badge&logo=rust&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![Tauri](https://img.shields.io/badge/Tauri-24C8DB?style=for-the-badge&logo=tauri&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-5FA04E?style=for-the-badge&logo=nodedotjs&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=for-the-badge&logo=sqlite&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)

</div>

---

<div align="center">

### Reach me

[![Email](https://img.shields.io/badge/email-a@alfie.cx-38e1c4?style=for-the-badge&logo=maildotru&logoColor=white&labelColor=0e1430)](mailto:a@alfie.cx)
[![GitHub](https://img.shields.io/badge/github-Alfiecxn-6aa6ff?style=for-the-badge&logo=github&logoColor=white&labelColor=0e1430)](https://github.com/Alfiecxn)

<sub>Portfolio is PIN-gated — happy to share on request.</sub>

</div>
