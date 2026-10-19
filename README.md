# Automated Documentation Engine

**Automated documentation · Browser automation · Web portal**

A documentation ecosystem designed to simplify the creation, maintenance, and delivery of functional documentation for enterprise applications.

[![JavaScript](https://img.shields.io/badge/JavaScript-18181B?style=flat-square&logo=javascript&logoColor=FF1493)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![Python](https://img.shields.io/badge/Python-18181B?style=flat-square&logo=python&logoColor=FF1493)](https://www.python.org/)
[![Playwright](https://img.shields.io/badge/Playwright-18181B?style=flat-square&logo=playwright&logoColor=FF1493)](https://playwright.dev/)
[![Vite](https://img.shields.io/badge/Vite-18181B?style=flat-square&logo=vite&logoColor=FF1493)](https://vite.dev/)
[![License](https://img.shields.io/badge/License-MIT-FF1493?style=flat-square)](LICENSE)

---

<img width="1916" height="865" alt="image" src="https://github.com/user-attachments/assets/03379e89-0278-4665-94c9-4c95fb00c1e1" />


## 01. Overview

Keeping enterprise documentation accurate and up to date can be challenging, particularly in applications with multiple modules, complex navigation structures, and frequently evolving interfaces.

**Automated Documentation Engine** addresses this challenge by combining browser automation, Markdown-based documentation, and a lightweight web portal into a unified workflow.

The goal is simple: **reduce repetitive documentation tasks while improving consistency, accessibility, and maintainability.**

### ✦ Interface Preview

A responsive documentation portal with a clean interface, intuitive navigation, and support for light and dark themes.

<table>
  <tr>
    <td width="50%" align="center">
      <strong>☀ Light Mode</strong>
    </td>
    <td width="50%" align="center">
      <strong>☾ Dark Mode</strong>
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top">
      <img
        src="https://github.com/user-attachments/assets/fdc5edf0-ded8-41e5-ae18-87a20f30fc16"
        alt="Documentation portal — Light Mode"
        width="100%"
      />
    </td>
    <td width="50%" valign="top">
      <img
        src="https://github.com/user-attachments/assets/ebe6646d-e7a4-4737-96c1-c4f68b807f2f"
        alt="Documentation portal — Dark Mode"
        width="100%"
      />
    </td>
  </tr>
</table>

<p align="center">
  <sub>One portal. Two themes. A consistent documentation experience. 🌸</sub>
</p>


### The challenge

Traditional documentation workflows often involve:

- Manually capturing and updating interface screenshots.
- Maintaining separate documents for multiple application modules.
- Repeating documentation tasks after interface changes.
- Navigating scattered files to locate functional information.

### The approach

The project introduces two complementary components:

**01 — Documentation Automation**

A Python automation engine powered by Playwright that navigates application modules, captures screenshots, and updates documentation metadata.

**02 — Documentation Portal**

A responsive, Markdown-driven Single Page Application that provides centralized access to functional manuals, searchable content, and intuitive navigation.

---

## 02. Tech Stack

| Layer | Technologies |
| :--- | :--- |
| Frontend | JavaScript (ES6+), HTML5, CSS3 |
| Build System | Vite, Node.js |
| Browser Automation | Python 3.10+, Playwright |
| Documentation | Markdown, Marked |
| Content Security | DOMPurify |
| Authentication | Node.js middleware, HTTP-only cookies |
| Deployment | Vercel |

The architecture prioritizes lightweight dependencies, modularity, maintainability, and efficient delivery.

---

## 03. Core Features

**🌸 Automated Documentation**

Browser automation powered by Playwright captures application interfaces and updates associated Markdown documentation.

**✦ Centralized Web Portal**

A lightweight SPA brings functional manuals together in a structured, accessible interface.

**⌕ Instant Search**

Search documentation by title, module identifier, or content, including internal references such as `ADM001` and `CON016`.

**◐ Adaptive Themes**

Responsive layouts with light and dark mode support, powered by CSS Custom Properties.

**↗ Streamlined Navigation**

Module-based navigation makes it easier to explore application features and locate relevant documentation.

**◇ Protected Access**

Authentication middleware provides controlled access through a Node.js proxy and HTTP-only session cookies.

**⟳ Build Automation**

A custom Vite build pipeline manages documentation assets and prepares the portal for deployment.

---

## 04. Architecture

The system is organized into two primary workflows.

### Documentation generation

```text
Enterprise Application
         │
         ▼
Python + Playwright
         │
         ├── Authenticate
         ├── Navigate modules
         ├── Capture screenshots
         └── Update documentation metadata
                       │
                       ▼
                Markdown Files
                       │
                       ▼
                docs/ + images/
```

### Documentation delivery

```text
Markdown Documentation
          │
          ▼
     Vite Build
          │
          ▼
    JavaScript SPA
          │
          ├── Markdown rendering
          ├── Search indexing
          ├── Module navigation
          └── Theme management
                       │
                       ▼
              Documentation Portal
```

The separation between documentation generation and presentation allows each component to evolve independently.

---

## 05. Project Structure

```text
.
├── assets/             # Branding and visual assets
├── docs/               # Functional documentation
│   ├── images/         # Automated screenshots
│   └── INICIO.md       # Portal welcome page
│
├── app.js              # Navigation, search and rendering
├── build.mjs           # Custom build pipeline
├── documentar.py       # Playwright automation engine
├── menu.js             # Module and navigation mapping
├── proxy.js            # Authentication and session proxy
├── styles.css          # Responsive UI and theme definitions
├── index.html          # Application entry point
└── vercel.json         # Deployment configuration
```

---

## 06. Engineering Principles

The project follows a set of practical engineering principles:

- **Automation first:** Minimize repetitive and error-prone manual tasks.
- **Maintainability:** Keep responsibilities clearly separated and code easy to extend.
- **Performance:** Favor lightweight implementations and efficient resource delivery.
- **Consistency:** Preserve a predictable documentation structure across modules.
- **Usability:** Make technical information accessible through intuitive navigation.
- **Security:** Apply access controls and sanitize rendered documentation content.

---

## 07. Security Considerations

The portal incorporates authentication and content-protection mechanisms, including:

- Node.js authentication and proxy middleware.
- Password verification using SHA-256 hashes.
- HTTP-only cookies for session management.
- Markdown HTML sanitization through DOMPurify.
- Protected routing and deployment configuration.

**Security note:** Direct SHA-256 password hashing is not recommended for production password storage. Password-specific algorithms such as Argon2id or scrypt, combined with appropriate session protections, should be used for production deployments.

---

## 08. Project Goals

This project explores the intersection of **browser automation, documentation engineering, and frontend development**, focusing on building tools that improve everyday development workflows.

Its primary objective is to transform documentation from a repetitive maintenance task into a more efficient, structured, and sustainable process.

## 09. Getting Started

### Prerequisites

Make sure the following tools are installed:

- **Node.js** and npm
- **Python 3.10+**
- **Playwright** and its Chromium browser

### Development Commands

Start the local development server:

```bash
npm run dev
```

Generate an optimized production build:

```bash
npm run build
```

Preview the production build locally:

```bash
npm run preview
```

### Running the Automation Engine

The automation engine is responsible for navigating application modules, capturing screenshots, and updating Markdown documentation.

**Full documentation synchronization**

Run the automation workflow without creating a Git commit:

```bash
python documentar.py --sem-commit
```

**Text-only synchronization**

Execute the text-copy workflow without launching the browser:

```bash
python documentar.py --copiar-apenas
```

> **Note:** The automation engine requires access to the target application and any necessary environment configuration.

---

## 10. License

Distributed under the **MIT License**. See the [`LICENSE`](LICENSE) file for more information.

---

## 11. Author

**Pricila Oliveira**  
*Software Engineering · Web Development · Automation*

[![GitHub](https://img.shields.io/badge/GitHub-18181B?style=flat-square&logo=github&logoColor=FFFFFF)](https://github.com/PricilaOliveiraRocha)
[![Portfolio](https://img.shields.io/badge/Portfolio-FF1493?style=flat-square&logo=googlechrome&logoColor=FFFFFF)](https://www.pricilaoliveirarocha.com.br)
[![DEV.to](https://img.shields.io/badge/DEV.to-18181B?style=flat-square&logo=devdotto&logoColor=FFFFFF)](https://dev.to/pricilaoliveirarocha)

---

<p align="center">
  <sub>Designed with attention to detail. Engineered for simplicity. 🌸</sub>
</p>

---

## License

Distributed under the MIT License. See the `LICENSE` file for details.

---

*Designed with attention to detail, built for maintainability.* 🌸
