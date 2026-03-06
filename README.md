# Quiz CLI

An interactive command-line quiz game written in modern JavaScript (ES Modules). It provides a small, dependency-free example of building a terminal-based quiz app demonstrating Node.js APIs, async/await, classes, and basic CLI input handling.

## Project Overview

- Purpose: A simple educational CLI app for testing programming knowledge across multiple categories (JavaScript, Node.js, General Programming).
- Key features:
  - Category selection with configurable question counts
  - Shuffled questions and a visual progress bar
  - Immediate feedback with explanations
  - Final score summary and review of incorrect answers
  - No external dependencies; uses Node.js built-in modules

## Requirements

- Node.js >= 18.0.0 (as specified in package.json `engines`)

## Setup Instructions

1. Clone the repository and change into the `test-app` directory (project files are under `test-app/`).

   git clone <repo-url>
   cd <repo-root>/test-app

2. (Optional) Install dependencies. This project has no declared runtime dependencies. If you use npm scripts, run:

   npm install

3. Run the app:

   npm start

   or directly:

   node index.js

4. Run tests (note: package.json defines a `test` script as `node --test`, but this repository contains no test files):

   npm test

## Usage Examples

- Start the app with `npm start` or `node index.js`.
- Follow the prompts to:
  1. Choose a category (e.g. "JavaScript Basics").
  2. Choose how many questions (All / 3 / 5 when available).
  3. Answer questions by entering the number shown for each option.
  4. Press Enter to advance between questions and screens.
  5. At the end, view your score and a review of any incorrect answers.

Example CLI flow (illustrative):

  $ npm start
  ╔═══════════════════════════════════════════╗
  ║                                           ║
  ║   📚 QUIZ CLI                             ║
  ║   Test your programming knowledge!       ║
  ║                                           ║
  ╚═══════════════════════════════════════════╝

  Choose a category:
    1. JavaScript Basics
    2. Node.js Fundamentals
    3. General Programming

  Your choice (enter number): 1

  How many questions?
    1. All questions
    2. 3 questions
    3. 5 questions

  Your choice (enter number): 2

  [Progress bar]
  Question 1 of 3
    1. var
    2. let
    3. const
    4. define
  Your choice (enter number): 3

  ✓ Correct!

  Press Enter to continue...

At the end you'll see a results summary with score percentage and optional review of incorrect answers.

## File Structure

test-app/
- package.json  - npm metadata (name: quiz-cli, version, scripts, license: MIT, engines: node >=18)
- index.js      - Main entry point and application loop (loads questions, handles menus)
- data/
  - questions.json - Quiz content: categories (javascript, nodejs, general) and question objects (question, options, answer index, explanation)
- src/
  - input.js     - Lightweight readline-based input utilities (createInterface, prompt, select, confirm, pressEnter)
  - quiz.js      - Quiz class with game logic (shuffle, askQuestion, progress rendering, showResults)
  - colors.js    - Small ANSI color helpers for terminal output

Note: There are some macOS metadata files under `__MACOSX/` that can be ignored.

## Additional Details

- License: MIT (as declared in package.json)
- Project type: ES Modules (package.json has "type": "module")
- Entry point: `index.js` (executable shebang present)
- No external dependencies: the app uses Node's built-in `readline`, `fs/promises`, and `path` modules
- Contribution & issues: This repository does not include a CONTRIBUTING.md file. To report bugs or request features, open an issue in the repository.

## Notes & Known Items

- Tests: `npm test` runs `node --test` per package.json, but there are no test files in the repo.
- Node version: Use Node 18+ to match the `engines` field and ESM usage.

--
Generated from repository contents. No additional files or behavior were assumed beyond the repository sources.
