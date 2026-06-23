# Quiz CLI

An interactive command-line quiz game for learning JavaScript and Node.js fundamentals.

## Project Overview

Quiz CLI is a small but complete terminal application built with Node.js and ES modules. It presents multiple-choice questions in the console, accepts user input through the built-in `readline` interface, and keeps track of score, progress, and answer review.

The application is organized around a simple gameplay loop:

1. Show a welcome banner
2. Let the user choose a quiz category
3. Let the user choose how many questions to answer
4. Ask each question one by one
5. Show instant feedback after every answer
6. Display a summary screen with the final score
7. Offer the option to replay

This repo is also educational: the code demonstrates several core JavaScript and Node.js concepts in a practical way, including:

- ES module syntax with `import` / `export`
- Asynchronous control flow with `async` / `await`
- Reading files from disk with `fs/promises`
- Handling terminal input with `readline`
- Object-oriented design through a `Quiz` class
- Array operations such as `map`, `filter`, `slice`, and `find`
- Destructuring assignments and template literals
- ANSI color output for a more polished terminal UI

The quiz content lives in a JSON file, which makes it easy to expand the question bank without changing the application logic.

## Setup Instructions

### Requirements

Make sure the following are installed on your machine:

- Node.js **18 or newer**
- npm, which is included with Node.js installations

The project uses modern JavaScript features and relies on built-in Node APIs, so older Node versions may not work correctly.

### Install

The application has no third-party runtime dependencies. The install step is still useful because it verifies the project metadata and can generate a lockfile if you want one for reproducible installs.

```bash
cd test-app
npm install
```

If you only want to run the app and do not need a lockfile, you can skip this step and go straight to starting the program.

### Run the app

From inside the `test-app` directory, start the quiz with:

```bash
npm start
```

You can also run the entry file directly:

```bash
node index.js
```

The `start` script is defined in `package.json` and points to the same entry point, so both approaches launch the same experience.

### Optional test command

A test script is included for Node's built-in test runner:

```bash
npm test
```

If no test files are present yet, the command may not do much, but the script is ready for future coverage.

## Usage Examples

When you launch the app, you will see a banner and a guided, menu-driven workflow. The questions are answered entirely from the terminal by entering the number that matches your choice.

Typical flow:

1. The app clears the screen and prints a welcome banner.
2. You choose a category such as JavaScript Basics, Node.js Fundamentals, or General Programming.
3. You choose whether to answer all questions or a smaller set.
4. Each question is displayed with numbered options.
5. You receive immediate feedback after answering.
6. The quiz ends with a score summary and a review of missed questions.
7. You can decide whether to play again without restarting the process.

### Example interaction

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

After each question, the app shows whether your answer was correct and may also display a short explanation for learning purposes.

### Example results behavior

If you answer most questions correctly, the app will display a positive performance message such as:

- Perfect score
- Great job
- Good effort

If you miss questions, the app lists the incorrect ones so you can review the correct answers before playing again.

## File Structure

```text
README.md

test-app/
├── data/
│   └── questions.json
├── index.js
├── package.json
└── src/
    ├── colors.js
    ├── input.js
    └── quiz.js
```

### What each file does

- `test-app/index.js` - Application entry point; loads questions, controls the quiz loop, and handles replay behavior
- `test-app/src/quiz.js` - Contains the `Quiz` class, question randomization, scoring, progress tracking, and final result rendering
- `test-app/src/input.js` - Wraps Node's `readline` module with reusable helpers for prompts, selections, confirmations, and pauses
- `test-app/src/colors.js` - Exposes ANSI color helpers used to style terminal output without external libraries
- `test-app/data/questions.json` - Stores quiz categories, question text, answer choices, correct answer indexes, and explanations
- `test-app/package.json` - Defines the project metadata, scripts, module type, and supported Node version

### Architecture notes

The application is intentionally split into small modules so each part has a clear responsibility:

- `index.js` coordinates the overall program flow
- `quiz.js` handles quiz state and results
- `input.js` abstracts terminal interaction
- `colors.js` keeps presentation helpers separate from game logic
- `questions.json` separates content from code

That structure makes it easier to maintain, extend, and reuse the quiz engine for additional categories or question sets.

## Features

- Interactive terminal experience with a clean welcome screen
- Category-based quizzes so users can focus on a topic
- Flexible question count selection for short or full sessions
- Randomized question order to keep repeat runs fresh
- Immediate correct/incorrect feedback after each answer
- Explanations for answers to reinforce learning
- Progress indicator that shows how far through the quiz you are
- Final score summary with performance-based encouragement
- Review section for questions answered incorrectly
- Replay loop so multiple sessions can happen in one run

## Technical Notes

- The app uses only built-in Node.js modules:
  - `node:fs/promises` for reading the question bank
  - `node:path` and `node:url` for resolving file locations in an ES module environment
  - `node:readline` for terminal prompts and selections
- The project is configured as an ES module package via `"type": "module"`
- The entry file includes a shebang, so it can be executed like a CLI script in environments that support it
- The quiz class computes progress, records answers, and renders a result screen at the end of the session
- Color output is handled through simple ANSI escape codes, which keeps the project dependency-free
- Questions are loaded at runtime from JSON, so new content can be added without changing the quiz engine

## Scripts

From the `test-app` directory:

- `npm start` - Launch the quiz application
- `npm test` - Run Node's built-in test runner

## Extending the Project

If you want to add more content, the easiest place to start is `test-app/data/questions.json`. You can add new categories, questions, answer choices, and explanations there.

If you want to change the experience itself, the main extension points are:

- `src/quiz.js` for scoring rules, progress display, or result formatting
- `src/input.js` for different interaction patterns
- `src/colors.js` for output styling

## License

MIT
