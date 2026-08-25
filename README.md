# Electrical Troubleshooter

**Electrical Troubleshooter** is a portable, safety-conscious local framework for educational electrical/electronic diagnostic decision trees. It provides a versioned JSON/YAML-compatible schema, yes/no and multiple-choice traversal, explanations, warnings, back/reset, import/export, validator, and visual editor.

> **Critical boundary:** Do **not** work on exposed energized equipment. Isolate, lock out, and verify equipment is de-energized; use qualified personnel where required. This framework is educational, uses generic observational guidance only, and never instructs live probing, bypassing protection, or work inside unsafe compartments.

The included guides cover motor non-start, basic control-panel fault, sensor non-response, and power-supply diagnostic contexts. Every guide begins with a safety confirmation and routes uncertainty to a safe stop/qualified-service state.

| Layer | Local behavior |
|---|---|
| Schema | Versioned `1` decision tree with question/terminal nodes and validated links. |
| Safety validator | Requires the isolation/lockout/qualified-personnel boundary, rejects cycles, missing links, and potentially unsafe exposed/live/energized work language. |
| Renderer | Presents branch choices, warning, explanation, back, and reset controls. |
| Visual editor | Lets users edit selected local nodes and safely validates before saving. |
| Import/export | Reads JSON or JSON-form YAML 1.2; exports JSON and JSON-form YAML without external dependencies. |

## Local Linux and Windows use

Install **Node.js 22+** and pnpm. This is a portable local application, not a hosted service or native installer, and has no public website URL.

| Task | Linux / macOS shell | Windows PowerShell or Command Prompt |
|---|---|---|
| List bundled guides | `./run-local.sh list` | `run-local.cmd list` |
| Generate a safe demo | `./run-local.sh demo --tree motor --out reports/demo` | `run-local.cmd demo --tree motor --out reports\demo` |
| Validate an exported guide | `./run-local.sh validate guide.json` | `run-local.cmd validate guide.json` |
| Serve a local workspace | `./run-local.sh serve reports/demo --port=4069` | `run-local.cmd serve reports\demo --port=4069` |

The report server binds only to `127.0.0.1`. Exported guides remain local unless you intentionally share them.

## Validation

```bash
pnpm install
pnpm test
pnpm check
pnpm demo
```

Tests cover safe traversal, back/reset, cycle detection, schema validation, JSON-form YAML import/export, malformed safety content, and the UI contract.

## License

MIT.

<!-- clear-use-guide -->
## Clear use guide

### Install

Use Node.js 22 or newer, clone this repository, and install its dependencies:

```bash
git clone https://github.com/nandurpm/electrical-troubleshooter.git
cd electrical-troubleshooter
pnpm install
```

### Open it locally

Start the local web/report server:

```bash
pnpm start
```

Then open the URL printed by the terminal. The production report hosts use http://localhost:4080 unless a different PORT value is set. To choose another port, use PORT=5050 pnpm start on Linux/macOS or set PORT=5050 && pnpm start in Windows Command Prompt.


### Use the hosted version

**Live URL:** [https://electrical-troubleshooter.onrender.com](https://electrical-troubleshooter.onrender.com)

The hosted version is a browser-friendly report or application view. It runs on Render’s free tier, so the first request after inactivity can take longer while the instance starts.

### Windows and Linux

The same Node.js commands work in Windows PowerShell, Windows Command Prompt, and a Linux terminal. Use the platform-specific port command above only when you need a non-default local port.

### Important scope

This project follows its existing local-first and read-only boundaries. Demo/report content is generated or supplied through the documented local workflow; a hosted page does not provide hidden access to your device, private files, hardware, accounts, or network.

