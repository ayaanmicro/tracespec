# TraceSpec ⚡

TraceSpec is an open-source static and semantic analysis engine designed to evaluate large-scale framework migrations, detect breaking API changes, and synthesize verified codemods directly from repository diffs.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Powered by: Claude](https://img.shields.io/badge/AI-Claude%20API-orange)](https://anthropic.com)
[![Status: Beta](https://img.shields.io/badge/Status-Beta-emerald)](#)

---

## Key Capabilities

- **Cross-File Blast Radius**: Computes multi-file AST side effects across shared modules and monorepos.
- **Automated Codemod Synthesis**: Emits targeted, ready-to-merge git patch files for interface shifts.
- **Zero-Telemetry Local Audits**: Operates via local CLI mode or self-hosted serverless runners without indexing proprietary codebases.
- **High-Context Reasoning**: Leverages Claude's extended context window and structured tool-calling for syntax verification.

---

## Architecture Overview

                +---------------------+
                | Git Diff / AST Tree |
                +----------+----------+
                           |
                           v
                +---------------------+
                |   TraceSpec Engine  |
                +----------+----------+
                           |
                           v
          +---------------------------------+
          |    Claude API Reasoning Engine  |
          |  (Extended Context + Verification)|
          +----------------+----------------+
                           |
            +--------------+--------------+
            |                             |
            v                             v
+-----------------------+     +------------------------+
| Breaking Change Audit |     | Synthesized Patch/Diff |
+-----------------------+     +------------------------+

---

## Quickstart

### Running the Web Playground
TraceSpec runs as a client-side interface on modern browsers:

1. Clone the repository:
git clone https://github.com/<your-username>/tracespec.git
cd tracespec

2. Open `index.html` directly in your browser or run a lightweight local server:
npx serve .

### TraceSpec CLI (Beta Preview)

Analyze changes between HEAD and main:
tracespec audit --diff HEAD~1 --model claude-sonnet-5.5

Generate automated patch file:
tracespec patch --output migration.patch

---

## Roadmap

- [x] Client-side diff parsing and interactive report visualization
- [x] AST change heuristic detection
- [ ] Direct GitHub Actions CI workflow integration
- [ ] Automated PR-commenting bot for breaking-change risk scoring

---

## Contributing & License

Contributions are welcome! Please open an issue or submit a pull request.
Distributed under the MIT License. See `LICENSE` for more information.