# Quiz CLI

An interactive command-line quiz game for learning JavaScript and Node.js fundamentals.

## Project Overview

Quiz CLI is a terminal-based quiz application built with Node.js ES modules and the built-in `readline` API. It lets users:

- Choose a quiz category
- Choose how many questions to answer
- Answer multiple-choice questions from the terminal
- See immediate feedback and explanations
- Review missed questions at the end of the quiz
- Replay the quiz as many times as they want

The project is designed to demonstrate core JavaScript concepts such as:

- ES modules (`import` / `export`)
- Async/await and Promises
- Classes and object-oriented programming
- Array methods and destructuring
- Basic terminal styling with ANSI colors
- File reading with Node.js

## Setup Instructions

### Requirements

- Node.js **18 or newer**
- npm (comes with Node.js)

### Install

This project does not use external dependencies, so setup is minimal:

```bash
cd test-app
npm install
```

> `npm install` is optional here, but it will create a lockfile if you want one for consistency.

### Run the app

```bash
npm start
```

Or run directly:

```bash
node index.js
```

## Usage Examples

When the app starts, it will:

1. Show a welcome banner
2. Ask you to choose a category
3. Ask how many questions you want to answer
4. Display each question with numbered choices
5. Show whether your answer is correct
6. Display your final score and review missed answers
7. Ask whether you want to play again

### Example flow

```text
Choose a category:
1. JavaScript Basics
2. Node.js Fundamentals
3. General Programming

How many questions?
1. All questions
2. 3 questions
3. 5 questions

Your choice (enter number): 2
```

## File Structure

```text
README.md

test-app/
├── index.js
├── package.json
├── data/
│   └── questions.json
└── src/
    ├── colors.js
    ├── input.js
    └── quiz.js
```

### Key files

- `index.js` - Main application entry point and quiz flow control
- `src/quiz.js` - Quiz class, scoring, question handling, and results display
- `src/input.js` - Terminal input helpers using `readline`
- `src/colors.js` - ANSI color helper functions for terminal output
- `data/questions.json` - Question bank organized by category
- `package.json` - Project metadata, scripts, and Node version requirement

## Features

- Interactive terminal UI
- Category-based quizzes
- Dynamic question count selection
- Randomized question order
- Immediate correctness feedback
- Explanations for answers
- Final score summary with performance messages
- Review of incorrect answers

## Technical Notes

- The app uses Node.js built-in modules only:
  - `node:fs/promises`
  - `node:path`
  - `node:url`
  - `node:readline`
- It is configured as an ES module project via `"type": "module"`.
- The main script is executable and includes a shebang (`#!/usr/bin/env node`).

## Scripts

From the `test-app` directory:

- `npm start` - Run the quiz application
- `npm test` - Run Node's built-in test runner

## License

MIT
