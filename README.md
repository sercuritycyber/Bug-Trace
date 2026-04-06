<div align="center">

```
██████╗ ██╗   ██╗ ██████╗ ████████╗██████╗  █████╗  ██████╗███████╗
██╔══██╗██║   ██║██╔════╝ ╚══██╔══╝██╔══██╗██╔══██╗██╔════╝██╔════╝
██████╔╝██║   ██║██║  ███╗   ██║   ██████╔╝███████║██║     █████╗  
██╔══██╗██║   ██║██║   ██║   ██║   ██╔══██╗██╔══██║██║     ██╔══╝  
██████╔╝╚██████╔╝╚██████╔╝   ██║   ██║  ██║██║  ██║╚██████╗███████╗
╚═════╝  ╚═════╝  ╚═════╝    ╚═╝   ╚═╝  ╚═╝╚═╝  ╚═╝ ╚═════╝╚══════╝
```

**Web Security Toolkit — Desktop Edition**

![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20Linux-blue?style=flat-square)
![Electron](https://img.shields.io/badge/Electron-34-47848F?style=flat-square&logo=electron)
![React](https://img.shields.io/badge/React-18-61DAFB?style=flat-square&logo=react)
![License](https://img.shields.io/badge/license-MIT-green?style=flat-square)

A fast, offline-first desktop app for web security research and bug bounty hunting.  
No accounts. No telemetry. Everything runs locally.

</div>

---

## Features

### Passive / Analysis
| Tool | Description |
|------|-------------|
| **Header Analyser** | Detect missing security headers & insecure cookie flags |
| **CORS Analyser** | Identify CORS misconfigurations + generate PoC JS |
| **Tech Fingerprinter** | Identify CMS, frameworks & servers from source/headers |
| **CSP Analyser** | Evaluate Content-Security-Policy directives for weaknesses |
| **JWT Decoder** | Decode, inspect & security-check JWT tokens |
| **Secret Scanner** | Regex scan for hardcoded API keys, tokens & credentials |
| **Code Analyser** | Static pattern analysis for JS, Python & PHP |

### Active / Payloads
| Tool | Description |
|------|-------------|
| **XSS Probe** | Generate contextual XSS test vectors for reflected parameters |
| **IDOR Walker** | Generate sequential URL lists for IDOR testing |
| **Open Redirect** | Bypass payloads for open redirect parameters |
| **SSRF Helper** | Internal/metadata SSRF payload reference |
| **GraphQL Probe** | Introspection queries & attack vectors |
| **Param Miner** | Extract parameter names & build custom wordlists |

### Reporting / Export
| Tool | Description |
|------|-------------|
| **Burp Exporter** | Format raw HTTP requests for Burp Suite Repeater |
| **PoC Generator** | Generate structured Markdown vulnerability reports |

---

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) v18 or later

### Run in development mode

```bash
git clone https://github.com/YOUR_USERNAME/bugtrace.git
cd bugtrace
npm install
npm run dev
```

The app window will open automatically with hot reload enabled.

---

## Building Installers

### Windows
```bash
npm run dist:win
```
Outputs to `dist-electron/`:
- `BugTrace Setup 2026.1.0.exe` — NSIS installer with Start Menu shortcut
- `BugTrace 2026.1.0.exe` — Standalone portable executable

### Linux
```bash
npm run dist:linux
```
Outputs to `dist-electron/`:
- `BugTrace-2026.1.0.AppImage` — Universal binary (run with `chmod +x` first)
- `bugtrace_2026.1.0_amd64.deb` — Debian/Ubuntu package

### Both platforms
```bash
npm run dist
```

---

## Project Structure

```
bugtrace/
├── electron/
│   └── main.js          # Electron main process (window, menu, security)
├── src/
│   ├── App.jsx          # All 15 security tools (React)
│   └── main.jsx         # React entry point
├── public/
│   ├── icon.png         # App icon (Linux)
│   └── icon.ico         # App icon (Windows)
├── index.html           # HTML shell
├── vite.config.js       # Vite bundler config
└── package.json         # Scripts + electron-builder config
```

---

## Tech Stack

- **[Electron](https://www.electronjs.org/)** — Desktop shell
- **[React 18](https://react.dev/)** — UI framework
- **[Vite](https://vitejs.dev/)** — Bundler & dev server
- **[electron-builder](https://www.electron.build/)** — Cross-platform packaging

---

## Disclaimer

> BugTrace is intended for **authorised security testing only**.  
> Only use this tool against systems you have explicit permission to test.  
> The author is not responsible for any misuse or damage caused by this software.

---

## License

MIT — see [LICENSE](LICENSE) for details.
