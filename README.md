# AL VSC Prompts

A collection of VS Code prompt templates for AL (Application Language) development in Microsoft Dynamics 365 Business Central. These prompts are designed to be used with GitHub Copilot agents in VS Code to streamline common AL development tasks.

> **Note:** These are demonstration prompts — published to share the concept and approach, not as production-ready templates. They reflect how I structure Copilot agent prompts in my own AL development workflow. Use them as a starting point and adapt to your team's standards and needs.

## Available Prompts

| Prompt | Description | Recommended Model |
|--------|-------------|-------------------|
| [al-docs-code.prompt.md](al-docs-code.prompt.md) | Create comprehensive business-focused documentation for AL code | Claude Haiku 4.5 |
| [al-refactor-code.prompt.md](al-refactor-code.prompt.md) | Review and refactor AL code for quality, security, performance, and maintainability | Claude Sonnet 4.6 |
| [al-review-code.prompt.md](al-review-code.prompt.md) | Review AL code for quality, security, performance, and maintainability | Claude Sonnet 4.6 |
| [al-unit-tests.prompt.md](al-unit-tests.prompt.md) | Generate unit tests for AL procedures with Given-When-Then structure | Claude Sonnet 4.6 |

## Quick Start

1. **Save the prompts** in one of these locations:
   - **Repository workspace**: Copy `.prompt.md` files to `App\.github\prompts` in your project root
   - **Global VS Code**: Save to `C:\Users\<user>\AppData\Roaming\Code\User\prompts` for use across all projects
2. Open your AL project in VS Code with GitHub Copilot enabled
3. Use the prompts with Copilot by referencing them in your chat

## Prompt Details

### 📄 AL Documentation Generator

**File:** `al-docs-code.prompt.md`

Generates business-focused documentation for AL code. This prompt helps translate technical AL code into documentation that consultants and end users can understand.

**Features:**
- Translates AL code into business-friendly language
- Documents fields, table extensions, page extensions with business purpose
- Provides documentation in both English and Swedish
- Uses markdown format with consistent structure

**Output includes:**
- Business Context
- Functional Overview
- Prerequisites and dependencies
- Implementation Details
- User Impact
- Results/Outputs with examples

---

### 🔧 AL Code Refactor

**File:** `al-refactor-code.prompt.md`

Reviews and refactors AL code focusing on quality, security, performance, and maintainability with automated code improvements.

**Review Areas:**
- Reuse of existing Business Central objects instead of duplicating
- Security: permissions, input handling, and secure patterns
- Code cleanup: redundant logic, unused variables, and placeholders
- Magic numbers: replace with constants, enums, or setup tables
- Performance optimization: set-based operations, queries, avoid unnecessary loops
- Best practices: naming conventions, events, and extensibility
- Error handling where failures may occur
- Modular, testable, and maintainable design

**Output includes:**
- Refactored code block with improvements
- Summary of key improvements grouped by category
- Assumptions made due to missing context
- Suggested next steps if further information is needed

**Input handling:**
- Direct AL code snippets
- File paths (e.g., "src/Codeunit/MyCodeunit.al" or "c:\path\to\file.al")
- Folder paths containing .al files (e.g., "src/" or "c:\path\to\folder")

---

### 🔍 AL Code Review

**File:** `al-review-code.prompt.md`

Reviews AL code focusing on quality, security, performance, and maintainability.

**Review Areas:**
- Reuse of existing Business Central objects
- Security: permissions, input handling, secure patterns
- Code cleanup: redundant logic, unused variables
- Best practices: naming conventions, events, extensibility
- Performance optimization
- Error handling
- Modular, testable design

**Output includes:**
- Reviewed code block with identified issues
- Summary of improvements by category
- Assumptions made
- Suggested next steps

---

### 🧪 AL Unit Test Generator

**File:** `al-unit-tests.prompt.md`

Generates comprehensive unit tests for AL procedures using the Given-When-Then format.

**Features:**
- Analyzes procedures to extract parameters, variables, and record fields
- Covers positive, negative, and boundary scenarios
- Uses `Library - Random` codeunit for test data
- Preserves table relationships during setup
- Adds detailed comments explaining each test's intent

**Output Structure:**
```
procedure_analysis:
  - parameters
  - variables
  - record_fields
  - test_scenarios
  - random_data_cases

tests:
  - SCENARIO: <Number>: <Brief summary>
  - GIVEN: <Setup>
  - WHEN: <Action performed>
  - THEN: <Expected outcome>
```

## Usage Example

When using these prompts, provide input in one of the following formats:

- **Code text**: Direct AL code snippet
- **File path**: Path to .al file (e.g., "src/Codeunit/MyCodeunit.al")
- **Folder path**: Path to folder containing .al files (e.g., "src/")

```
Focus on: [Provided code text, file path, or folder path here]
```

## License

MIT License

Copyright (c) 2026 Milos Baic

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
