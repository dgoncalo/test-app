# test-app

Table of Contents

1. Project description
2. Setup instructions
3. How to run the project
4. Key features

## Project description

Interactive command-line quiz game to practice JavaScript, Node.js, and general programming fundamentals.

## Setup instructions

Prerequisites:
- Node.js >= 18.0.0
- git

Clone the repository and change into the project directory:

```
git clone https://github.com/dgoncalo/test-app.git
cd test-app/test-app
```

Note: This project has no external dependencies; there is no need to run npm install. The project uses ES modules (package.json "type": "module") and requires Node 18 or newer.

## Key features

- Interactive category selection
- Configurable question count (select All or specific counts like 3 or 5)
- Immediate per-question feedback
- Final score summary and review of incorrect answers
- Pure Node.js implementation using ES modules (no external dependencies)
- Questions stored in data/questions.json for easy editing or extension
