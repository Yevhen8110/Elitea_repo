# quiz-cli

## Overview

**quiz-cli** is an interactive command-line quiz game built with Node.js. It quizzes users on programming topics, with a focus on **JavaScript Basics**, **Node.js Fundamentals**, and **General Programming**.

The project is designed as a lightweight CLI experience using only Node.js built-in modules. It demonstrates ES Modules, async/await, simple object-oriented design through a `Quiz` class, and a polished terminal user experience with colored output and progress tracking.

## Features

- Interactive terminal quiz experience
- Category-based question selection
- Choice of quiz length: all questions, 3 questions, or 5 questions
- Shuffled questions for each run
- Score summary at the end of the quiz
- Review of incorrect answers with correct choices shown
- Colored terminal output and progress bar
- Replay prompt to run another quiz session
- No external npm dependencies

## Requirements

- **Node.js 18.0.0 or later**
- A terminal that supports standard ANSI color output

## Installation

1. Clone the repository.
2. Open the `test-app/` directory:

   ```bash
   cd test-app
   ```

3. No npm install is required because the app uses only built-in Node.js APIs.

## Usage

Run the application from the `test-app/` directory:

```bash
npm start
```

You can also start it directly with Node:

```bash
node index.js
```

### Example flow

1. Choose a quiz category.
2. Select how many questions to answer.
3. Answer each question from the provided options.
4. View your final score and review any incorrect answers.
5. Choose whether to play again.

## Project Structure

```text
test-app/
├── index.js
├── package.json
├── data/questions.json
└── src/
    ├── colors.js
    ├── input.js
    └── quiz.js
```

### File responsibilities

- **`index.js`**: Application entry point. Loads questions, handles category selection, runs the quiz flow, manages replay, shows the banner, and handles errors.
- **`src/quiz.js`**: Contains the `Quiz` class, question shuffling, scoring, progress display, answer tracking, and final results output.
- **`src/input.js`**: Readline helper utilities for prompts, selections, confirmations, and pause actions.
- **`src/colors.js`**: ANSI terminal color helpers for styling CLI output.
- **`data/questions.json`**: Quiz content organized by category, including questions, options, answer indices, and explanations.

## Scripts

Run these scripts from inside `test-app/`:

```bash
npm start
```

Starts the quiz application.

```bash
npm test
```

Runs Node's built-in test runner with `node --test`.

## Quiz Content / Data Format

Quiz questions are stored in `data/questions.json` and grouped by category.

Each question entry includes:

- `question`: The question text
- `options`: An array of possible answers
- `answer`: The index of the correct option
- `explanation`: A short explanation shown after answering

Example structure:

```json
{
  "categories": {
    "javascript": {
      "name": "JavaScript Basics",
      "questions": [
        {
          "question": "What keyword is used to declare a constant in JavaScript?",
          "options": ["var", "let", "const", "define"],
          "answer": 2,
          "explanation": "The 'const' keyword declares a block-scoped constant that cannot be reassigned."
        }
      ]
    }
  }
}
```

## Notes

- The app uses a Unix-style shebang in `index.js`, making it executable in compatible environments.
- Questions are shuffled each time a quiz starts.
- Incorrect answers are reviewed at the end of the quiz with the correct answer shown.
- No CI/CD, build pipeline, or deployment configuration was found in the repository.
- No dedicated test files were found, although a test script is defined in `package.json`.
