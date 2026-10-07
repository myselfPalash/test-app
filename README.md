# Quiz CLI

An interactive command-line quiz game for learning JavaScript. The application runs in a terminal, presents multiple-choice questions by category, provides immediate feedback and explanations, and displays a final score with a review of incorrect answers.

## Project Overview

This repository contains a Node.js command-line quiz application. The executable application is located in the nested `test-app/` directory, which contains `package.json`, `index.js`, the quiz implementation, and the question data.

The quiz currently includes these categories:

- JavaScript Basics
- Node.js Fundamentals
- General Programming

Each category currently contains five questions with explanations.

## Key Features

- Interactive terminal-based quiz experience
- Category selection
- Question-count selection:
  - All available questions
  - Three questions
  - Five questions, where available
- Multiple-choice questions
- Immediate answer feedback
- Explanations for questions
- Progress bar during a quiz
- Score and percentage calculation
- Performance feedback
- Review of incorrect answers
- Option to replay the quiz
- ANSI-colored terminal output
- No external runtime dependencies

## Technology Stack

- JavaScript
- Node.js
- Native ES modules
- Node.js built-in modules:
  - `node:fs/promises`
  - `node:url`
  - `node:path`
  - `node:readline`

The project uses the native Node.js module system through `"type": "module"` in [`test-app/package.json`](test-app/package.json).

## Prerequisites

- Node.js `>=18.0.0`

The repository does not include an `.nvmrc` or `.node-version` file, so no more specific Node.js version is declared.

## Installation and Setup

The application is located in the `test-app/` subdirectory. Run project commands from that directory:

```text
cd test-app
```

The project declares no external runtime dependencies, and no lockfile is included. Therefore, no dependency installation step is required by the repository configuration.

## Configuration

No environment variables, ports, credentials, or secret configuration are used by the application.

Questions are stored in:

```text
test-app/data/questions.json
```

The application loads this file relative to its module location.

## Running the Project

From the `test-app/` directory, use the configured start script:

```text
npm start
```

This runs:

```text
node index.js
```

The application starts an interactive terminal session. It displays a welcome banner, prompts for a category and question count, runs the quiz, shows feedback and explanations, displays the results, and asks whether to replay.

The command configuration was inspected but not executed as part of this documentation process.

## Usage Examples

Start the quiz from the application directory:

```text
cd test-app
npm start
```

During the interactive session, select one of the available categories:

```text
JavaScript Basics
Node.js Fundamentals
General Programming
```

Then select the desired number of questions:

```text
All available questions
3 questions
5 questions, where available
```

The quiz presents multiple-choice questions and provides feedback after each answer. At the end, it displays the score, percentage, performance message, and incorrect-answer review.

The exact terminal prompts and output were not executed or captured during repository inspection.

## Project Structure

```text
test-app/
├── __MACOSX/                  # macOS metadata artifacts; not part of the application
└── test-app/
    ├── .DS_Store              # macOS metadata file
    ├── data/
    │   └── questions.json     # Quiz categories, questions, answers, and explanations
    ├── index.js               # CLI entry point and application flow
    ├── package.json           # Project metadata, scripts, engine requirement, and license declaration
    └── src/
        ├── colors.js          # ANSI color helpers
        ├── input.js           # Interactive prompts, validation, and confirmations
        └── quiz.js            # Quiz logic, shuffling, scoring, progress, and answer review
```

The `__MACOSX/` directory and `.DS_Store` file are metadata artifacts and are not relevant to running the application.

## Architecture and Important Components

### `index.js`

The main command-line entry point. It:

- Loads `data/questions.json`
- Displays the welcome banner
- Handles category and question-count selection
- Creates and runs the quiz
- Handles replay behavior
- Reports application errors

### `src/quiz.js`

Defines the `Quiz` class and implements:

- Fisher–Yates question shuffling
- Multiple-choice question flow
- Progress-bar display
- Immediate feedback
- Explanations
- Score and percentage calculation
- Performance messages
- Review of incorrect answers

### `src/input.js`

Provides terminal interaction helpers, including:

- Readline prompts
- Numbered selections with validation
- Yes/no confirmation
- “Press Enter” pauses

### `src/colors.js`

Provides ANSI color helpers for terminal output. It does not use an external package.

### `data/questions.json`

Contains the quiz content, organized into the available categories. Each category currently contains five questions and explanations.

## Testing

The repository defines this test script in [`test-app/package.json`](test-app/package.json):

```text
npm test
```

The script runs:

```text
node --test
```

No test files were discovered in the inspected repository. The command was not executed, so this README does not claim that tests exist or pass.

## Available Commands

Run these commands from the `test-app/` directory:

| Command | Configured action |
|---|---|
| `npm start` | Runs `node index.js` and launches the interactive quiz |
| `npm test` | Runs `node --test` |

The commands were read from the project configuration but were not executed during inspection.

## Deployment

No deployment configuration, hosting instructions, container configuration, or CI/CD workflows were found in the repository.

The application is documented as a local Node.js command-line program.

## Contributing

No contribution guide or repository-specific contribution workflow was found.

When modifying the project, preserve the existing application structure and run the configured commands where appropriate:

```text
npm start
npm test
```

The commands above are configured in the repository but were not verified during preparation of this README.

## License

[`test-app/package.json`](test-app/package.json) declares the project license as **MIT**.

No standalone `LICENSE` file was found, and the repository metadata did not expose a repository-level license object. This README therefore reports the package declaration without treating the repository as having a separately verified license file.

## Documentation Scope and Limitations

- **Repository:** `https://github.com/myselfPalash/test-app`
- **Inspected branch:** `main`
- **Inspected commit:** `eb685a06d02bd48344d130b84d704a79fc9c9592`
- **Commit message:** `first commit`
- Documentation-relevant text files were retrieved successfully.
- Binary and metadata artifacts were handled as metadata only; they were not interpreted as application source.
- `__MACOSX/` and `.DS_Store` were excluded from application documentation because they are macOS metadata artifacts.
- No existing root `README.md` was available for cross-checking.
- No test files were found.
- No lockfile, CI/CD configuration, deployment configuration, screenshots, contribution guide, or standalone `LICENSE` file was found.
- The configured commands were not executed, so runtime behavior, test results, and terminal output were not independently verified.
- No unresolved environment-variable, port, credential, or secret-configuration requirements were identified.
