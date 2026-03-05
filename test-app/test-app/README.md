# quiz-cli

An interactive command-line quiz game for learning JavaScript — small, dependency-free CLI quiz that runs on Node.js.

[![Node.js >=18](https://img.shields.io/badge/node-%3E%3D18-brightgreen.svg)](#requirements) [![version](https://img.shields.io/badge/version-1.0.0-blue.svg)](#)

Table of Contents
- Features
- Requirements
- Installation
- Usage
  - Run with npm
  - Run with node
  - Example interactive session
- Project structure
- Development notes
- Contributing
- License

Features
- Interactive command-line quiz with selectable categories.
- Multiple-choice questions with immediate feedback.
- Colored terminal output (ANSI) and visual progress bar.
- Results summary with score, performance message, and review of incorrect answers.
- No external dependencies — uses Node.js built-ins only.
- Easy to extend: add or edit questions in data/questions.json.

Requirements
- Node.js >= 18 (project uses ES modules and node: built-ins; package.json lists engines: "node": ">=18.0.0").
- No external npm dependencies required.

Installation
1. Clone the repository:
   git clone https://github.com/dgoncalo/test-app.git
2. Change into the project directory that contains the CLI app:
   cd test-app/test-app
3. (Optional) Install dependencies:
   This project uses only Node built-ins, so there are no production dependencies to install. Running npm install is optional; it will set up dev tools if any are later added:
   npm install

Usage

Run with npm
- Start the quiz using the package.json script:
  npm start
  (runs `node index.js`)

Run with node
- Run directly:
  node index.js

Example interactive session
Below is a representative transcript showing typical prompts and responses. Prompts like "Your choice (enter number):" expect a number corresponding to an option.

> Welcome to the Quiz CLI!
> Select a category:
>   1. JavaScript Basics
>   2. Node.js Fundamentals
>   3. General Programming
Your choice (enter number): 1

How many questions would you like? (Enter a number or press Enter for all): 3

[░░░░░░░░░░░░░░░░░░░░░] 0%
Question 1 of 3
What is the output of console.log(typeof null)?
  1. "null"
  2. "object"
  3. "undefined"
  4. "number"
Your choice (enter number): 2

✓ Correct!
💡 In JavaScript, typeof null returns "object" (a long-standing quirk).

[██████████░░░░░░░░░░░] 33%
Question 2 of 3
Which method is used to add an element to the end of an array?
  1. push()
  2. pop()
  3. shift()
  4. unshift()
Your choice (enter number): 1

✗ Incorrect!
The correct answer was: push()
💡 push() appends elements to the array's end.

[████████████████░░░░░] 66%
Question 3 of 3
Which keyword declares a block-scoped variable?
  1. var
  2. let
  3. function
  4. const
Your choice (enter number): 2

✓ Correct!

══════════════════════════════════════════════════
  📊 QUIZ RESULTS
══════════════════════════════════════════════════

  Category: JavaScript Basics
  Score: 2/3 (67%)

  👍 Good effort! Keep learning!

📝 Review these questions:

1. Which method is used to add an element to the end of an array?
   Your answer: pop()
   Correct: push()

How to add new questions
- Open data/questions.json (relative to the project root where index.js is located).
- The file contains categories and arrays of question objects. Each question object typically has:
  - question (string)
  - options (array of strings)
  - answer (number — index of correct option, zero-based)
  - explanation (optional string)
- Add or edit question objects, commit, and run the quiz to test.

Project structure
- index.js
  - CLI entry point. Loads data/questions.json, prompts user, runs the Quiz class and prints results.
- package.json
  - Project metadata (name: quiz-cli, version: 1.0.0), scripts (start/test), and engines (node >=18).
- data/
  - questions.json — categories and question sets (JavaScript Basics, Node.js Fundamentals, General Programming).
- src/
  - colors.js — small ANSI color helpers and convenience functions.
  - input.js — readline-based input helpers (prompt, select, confirm, pressEnter).
  - quiz.js — Quiz class implementing game logic, progress, scoring, and results display.

Development notes
- ES modules (package.json includes "type": "module"); import/export syntax is used throughout.
- Requires Node.js >= 18 for the node: builtin import style and runtime features.
- No external dependencies — the app uses only Node built-in modules (readline, console, etc.).
- package.json includes:
  - "start": "node index.js"
  - "test": "node --test" (if you add tests, `npm test` will run Node's test runner)

Contributing
- Contributions are welcome! Common ways to help:
  - Add new questions or categories in data/questions.json.
  - Improve prompts, UX, or add configuration options.
  - Add automated tests and CI.
  - Fix bugs or improve code clarity in src/.
- Suggested workflow:
  1. Fork the repository.
  2. Create a feature branch.
  3. Make changes and test locally (run node index.js).
  4. Open a pull request with a clear description of changes.
- Please keep changes small and include examples or sample question data when adding categories.

License
- MIT — see package.json "license": "MIT".
- By contributing you agree to license your contributions under the same MIT license.
