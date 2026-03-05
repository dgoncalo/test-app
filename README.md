# quiz-cli

Add README for quiz-cli (interactive CLI quiz app)

## Table of contents

- Summary
- Installation
- Running the app
- Requirements
- Repository files
- License

## Summary

This README adds a brief description and instructions for the quiz-cli interactive CLI quiz app. It documents how to install and run the app and notes the Node.js requirement.

## Installation

1. Clone the repository:

   git clone https://github.com/dgoncalo/test-app.git
   cd test-app

2. Install dependencies:

   npm install

## Running the app

Start the quiz from the project root:

   node index.js

or, if using npm scripts (if defined in package.json):

   npm start

## Requirements

- Node.js >= 18

## Repository files

This README was created based on the repository contents: index.js, package.json, data/questions.json, src/.

## License

See repository for license information.

## How to run the project

Entrypoint: index.js

Run using npm:

```
npm start
```

Or run directly with Node:

```
node index.js
```

Quick usage notes:
- The CLI prompts you to select a question category and the number of questions to attempt (e.g., All, 3, 5).
- Answer each question by entering the number corresponding to the chosen option.
- The app provides immediate per-question feedback, shows a final score, and offers a review of incorrect answers.
