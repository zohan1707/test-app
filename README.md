# test-app — CLI Quiz

A small interactive command-line quiz application located in the test-app/ folder. It runs under Node.js (engine requirement >= 18) and loads question sets from a JSON data file. Intended for quick CLI demos, learning, and small experiments.

## Features
- Interactive CLI quiz experience.
- Questions are driven by a JSON data file (multiple categories).
- Zero external dependencies (runs with Node.js built-in APIs).
- Simple start script: `npm start` → runs `node index.js`.

## Prerequisites
- Node.js v18 or newer (the package.json specifies Node engine >=18).
- Git (to clone the repo), if installing from source.

Check your Node version:
```
node -v
```

## Installation

1. Clone the repository:
```
git clone <repository-url>
cd <repo-root>
```

2. Navigate to the app directory:
```
cd test-app
```

3. (Optional) Install dependencies:
- There are no external dependencies required by this project, so `npm install` is optional. Running it is harmless if you plan to add dependencies later:
```
npm install
```

## Running

From the test-app directory you can start the quiz:

- With npm script:
```
npm start
```

- Or directly with Node:
```
node index.js
```

`npm start` runs `node index.js` (start script in package.json).

## Usage summary (CLI flow)
- The app is a CLI quiz that reads questions from `data/questions.json`.
- On launch it presents an interactive flow (choose category / answer questions / see results).
- Question sets are grouped into categories; the shipped data includes at least:
  - javascript
  - nodejs
  - general

(Exact prompts and flow are implemented in `index.js` — run the app to see the interactive behavior.)

## Project structure

Top-level (important files)
- test-app/
  - index.js           — CLI entry point (run with node index.js)
  - package.json       — project metadata, scripts (start = node index.js), engine >=18
  - data/
    - questions.json   — quiz data (question categories and items)
  - README.md?         — (this file should be placed at repo root)
  - other files (package-lock.json, etc.) may be present

Note: The CLI quiz and all runnable logic live in `test-app/`. Treat that as the application root when developing or running.

## Data / questions
- Questions are stored in `test-app/data/questions.json`.
- The JSON contains multiple categories (javascript, nodejs, general) and question objects for each category.
- To add or modify questions, edit that JSON file. Keep the structure consistent with the existing entries.

Suggestions:
- Validate JSON structure after edits (e.g., with `jq` or a quick Node script) to avoid runtime errors.
- Consider adding metadata per question (difficulty, id) if you plan to extend features.

## Development notes
- The project targets Node.js >=18. Use a matching runtime for ESM and modern APIs.
- The codebase uses modern Node features; if package.json includes `"type": "module"`, it runs as ESM. If you switch to CommonJS, adjust imports/exports accordingly.
- There are no external dependencies by default — ideal for fast iteration.

## Contributing / clean-up suggestions
- Add a LICENSE file (none detected). Consider MIT, Apache-2.0, or another license that fits your project goals.
- Add a CONTRIBUTING.md if you expect external contributors (guidelines, code style, tests).
- Add simple tests (e.g., data validation tests for questions.json).
- Clean up repository metadata:
  - Remove macOS/hidden files (e.g., .DS_Store) and platform-specific temporary files.
  - Add a .gitignore to exclude OS metadata, node_modules (if dependencies are added), and other local artifacts.
- Consider improving question editing UX (a small admin CLI) or persisting scores/history.

## License
No license file detected in the repository. If you plan to publish or accept contributions, add an explicit LICENSE file to make reuse and contribution terms clear.

## Contact / Support
- For issues, feature requests, or questions: open an issue in the repository.
- When opening issues, include Node version and steps to reproduce if you encounter runtime errors.

---

If you want, I can:
- Generate a LICENSE.md (e.g., MIT) and add it to the repo.
- Add a CONTRIBUTING.md template and a simple .gitignore.
- Produce a short development checklist (local run, tests, PR template).
