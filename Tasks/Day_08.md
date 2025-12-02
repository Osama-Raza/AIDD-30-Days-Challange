# Contitutons Project Constitution: Simple Python Calculator

## 1. Introduction

This constitution outlines the fundamental principles and guidelines governing the development of the "Simple Python Calculator" project. It serves as a foundational document to ensure consistency, quality, and maintainability throughout its lifecycle.

## 2. Principles

### 2.1 Technology Stack
The project MUST use Python 3 as its primary programming language.

### 2.2 Core Functionality
The calculator MUST perform basic arithmetic operations: addition, subtraction, multiplication, and division.

### 2.3 Code Style
All Python code MUST adhere to PEP 8 standards for formatting and style.

### 2.4 User Interface
The calculator MUST provide a simple and intuitive command-line interface (CLI) for user interaction.

### 2.5 Error Handling
The application MUST gracefully handle errors such as division by zero and invalid user input (e.g., non-numeric input).

### 2.6 Testing
Every function MUST have corresponding unit tests using either the `unittest` or `pytest` framework to ensure correctness and reliability.

### 2.7 Modularity
The project MUST be structured logically, separating business logic (calculations) from the user interface (input/output) components.

### 2.8 Extensibility
The design SHOULD allow for easy addition of new operations (e.g., exponentiation, square root) in the future without significant refactoring.

### 2.9 Documentation
All functions and critical code sections MUST have clear docstrings explaining their purpose, arguments, and return values.

## 3. Governance

### 3.1 Amendment Procedure
Amendments to this constitution MUST be proposed via a pull request, reviewed by at least two core contributors, and approved by a simple majority vote.

### 3.2 Versioning Policy
This constitution adheres to Semantic Versioning (MAJOR.MINOR.PATCH). MAJOR increments for backward-incompatible changes, MINOR for significant additions, and PATCH for minor clarifications or corrections.

### 3.3 Compliance Review
Compliance with this constitution MUST be reviewed annually by the project leads.

## 4. Document History
- **RATIFICATION_DATE**: 2025-12-02
- **LAST_AMENDED_DATE**: 2025-12-02
- **CONSTITUTION_VERSION**: 0.1.0

# Specification 

# Feature Specification: Simple Python Calculator

**Feature Branch**: `1-simple-calculator`
**Created**: 2025-12-02
**Status**: Draft
**Input**: User wants a simple calculator using Python.

## User Scenarios & Testing

### User Story 1 - Basic Arithmetic Calculation (Priority: P1)

As a user, I want to input two numbers and choose an arithmetic operation (addition, subtraction, multiplication, or division) to get the correct result.

**Why this priority**: This is the core functionality and delivers immediate value, fulfilling the primary purpose of a calculator.

**Independent Test**: This story can be fully tested by providing valid numeric inputs and a supported operator, then verifying the correctness of the output displayed to the user.

**Acceptance Scenarios**:

1.  **Given** the calculator is running, **When** I input `5`, then `+`, then `3`, **Then** the output should be `8`.
2.  **Given** the calculator is running, **When** I input `10`, then `-`, then `4`, **Then** the output should be `6`.
3.  **Given** the calculator is running, **When** I input `6`, then `*`, then `7`, **Then** the output should be `42`.
4.  **Given** the calculator is running, **When** I input `20`, then `/`, then `5`, **Then** the output should be `4.0`.

### User Story 2 - Handling Invalid Input (Priority: P2)

As a user, I want the calculator to provide a clear error message if I enter non-numeric input or attempt to divide by zero, without crashing.

**Why this priority**: This ensures the robustness and user-friendliness of the application, preventing unexpected program termination and guiding the user to correct input.

**Independent Test**: This story can be tested by providing non-numeric inputs or attempting division by zero, and then verifying that an appropriate, user-friendly error message is displayed and the program continues to function or prompts for new input.

**Acceptance Scenarios**:

1.  **Given** the calculator is running, **When** I input `abc` for a number, **Then** an error message "Invalid input. Please enter a number." should be displayed.
2.  **Given** the calculator is running, **When** I input `10`, then `/`, then `0`, **Then** an error message "Error: Division by zero is not allowed." should be displayed.

### Edge Cases

-   **Non-numeric input**: Handled gracefully with an error message (as per User Story 2).
-   **Division by zero**: Prevented with an error message (as per User Story 2).
-   **Large numbers**: The calculator should correctly handle numbers within Python's standard integer and float limits.
-   **Negative numbers**: All arithmetic operations should function correctly with negative numbers.

## Requirements

### Functional Requirements

-   **FR-001**: The system MUST accept two numerical inputs from the user.
-   **FR-002**: The system MUST accept an arithmetic operator (`+`, `-`, `*`, `/`) from the user.
-   **FR-003**: The system MUST perform addition on the two numbers if the `+` operator is selected.
-   **FR-004**: The system MUST perform subtraction on the two numbers if the `-` operator is selected.
-   **FR-005**: The system MUST perform multiplication on the two numbers if the `*` operator is selected.
-   **FR-006**: The system MUST perform division on the two numbers if the `/` operator is selected.
-   **FR-007**: The system MUST display the result of the operation to the user.
-   **FR-008**: The system MUST validate user input to ensure that operands are numerical.
-   **FR-009**: The system MUST detect and prevent division by zero, providing an appropriate error message.
-   **FR-010**: The system MUST be implemented in Python 3.

### Non-Functional Requirements

-   **NFR-001 (Code Style)**: All Python code MUST adhere to PEP 8 standards.
-   **NFR-002 (User Interface)**: The application MUST utilize a command-line interface (CLI).
-   **NFR-003 (Error Handling)**: The application MUST gracefully handle invalid inputs and runtime errors without crashing.
-   **NFR-004 (Testing)**: All core calculation functions MUST have unit tests covering typical and edge cases to ensure correctness.
-   **NFR-005 (Modularity)**: Business logic (calculation functions) MUST be distinctly separated from the user interface logic.
-   **NFR-006 (Documentation)**: All functions and critical code sections MUST include clear docstrings explaining their purpose, arguments, and return values.

### Key Entities

-   **Number**: A numerical value (integer or float) provided by the user as an operand.
-   **Operator**: A mathematical symbol (`+`, `-`, `*`, `/`) indicating the desired arithmetic operation.
-   **Result**: The computed outcome of the arithmetic operation.

## Success Criteria

### Measurable Outcomes

-   **SC-001**: The calculator correctly performs all four basic arithmetic operations (addition, subtraction, multiplication, division) for valid inputs in 100% of test cases.
-   **SC-002**: The calculator successfully catches and reports invalid non-numeric input without program termination in 100% of test cases.
-   **SC-003**: The calculator successfully catches and reports division by zero errors without program termination in 100% of test cases.
-   **SC-004**: The calculator's main functions are covered by unit tests with at least 90% code coverage.

- **RATIFICATION_DATE**: 2025-12-02
- **LAST_AMENDED_DATE**: 2025-12-02
- **CONSTITUTION_VERSION**: 0.1.0

# Plan  
# Implementation Plan: Simple Python Calculator

**Branch**: `1-simple-calculator` | **Date**: 2025-12-02 | **Spec**: [specs/1-simple-calculator/spec.md](specs/1-simple-calculator/spec.md)
**Input**: Feature specification from `/specs/1-simple-calculator/spec.md`

## Summary

The "Simple Python Calculator" will provide a command-line interface for users to perform basic arithmetic operations (addition, subtraction, multiplication, and division) on two numbers. The technical approach will emphasize modular design, robust error handling for invalid inputs and division by zero, and comprehensive unit testing to ensure calculation accuracy and application stability. The project will adhere to Python's PEP 8 style guidelines.

## Technical Context

**Language/Version**: Python 3.x (adhering to constitution Principle 2.1: Technology Stack)
**Primary Dependencies**: Standard Python library only. No external libraries required for core functionality.
**Storage**: N/A (stateless CLI application)
**Testing**: `pytest` (adhering to constitution Principle 2.6: Testing)
**Target Platform**: Any system with Python 3 installed (CLI application).
**Project Type**: Single project (CLI)
**Performance Goals**: Instantaneous response for basic operations. Operations should complete within milliseconds.
**Constraints**:
-   Must function as a command-line application.
-   Strict adherence to Python 3.
-   Outputs should be clear and user-friendly.
**Scale/Scope**: Single-user, single-operation at a time; limited to the four basic arithmetic operations specified.

## Constitution Check

All principles from the `constitution.md` are aligned with this plan. Specifically:

-   **Technology Stack (2.1)**: The plan confirms the use of Python 3.x.
-   **Core Functionality (2.2)**: The plan focuses on the specified basic arithmetic operations.
-   **Code Style (2.3)**: Adherence to PEP 8 is a stated goal of the plan.
-   **User Interface (2.4)**: The plan confirms a Command-Line Interface (CLI).
-   **Error Handling (2.5)**: Robust error handling for invalid inputs and division by zero is a core part of the plan.
-   **Testing (2.6)**: The plan includes comprehensive unit testing using `pytest`.
-   **Modularity (2.7)**: The planned project structure separates UI, operations, and validation logic.
-   **Extensibility (2.8)**: The modular design inherently supports future additions of new operations.
-   **Documentation (2.9)**: Docstrings for all functions will be included during implementation.

## Project Structure

### Documentation (this feature)

```text
specs/1-simple-calculator/
├── plan.md              # This file
├── spec.md              # Feature specification
└── checklists/
    └── requirements.md  # Specification quality checklist
```

### Source Code (repository root)

```text
calculator/
├── __init__.py          # Marks 'calculator' as a Python package
├── main.py              # Handles user interaction, input parsing, and result display
├── operations.py        # Contains functions for basic arithmetic operations (+, -, *, /)
└── validation.py        # Contains functions for validating user input (e.g., is_numeric, is_valid_operator)

tests/
├── conftest.py          # Pytest configuration/fixtures
├── test_operations.py   # Unit tests for functions in operations.py
└── test_validation.py   # Unit tests for functions in validation.py
```

**Structure Decision**: The "Single project" option is chosen to house the calculator application. The proposed directory structure `calculator/` and `tests/` separates the application logic from its test suite. Within `calculator/`, concerns are further separated into `main.py` for user interface and control flow, `operations.py` for pure arithmetic logic, and `validation.py` for input sanitization. This modular approach enhances readability, maintainability, and testability, directly aligning with the Modularity (2.7) and Testing (2.6) principles outlined in the project's constitution.

## Complexity Tracking

N/A. This is a straightforward new feature with no identified prior violations, unusual complexities, or conflicting requirements that would necessitate specific complexity tracking.  

# Tasks  

# Tasks: Simple Python Calculator

**Input**: Design documents from `specs/1-simple-calculator/`
**Prerequisites**: plan.md (required), spec.md (required for user stories), research.md, data-model.md

## Format: `[ID] [P?] [Story] Description`

- **[P]**: Can run in parallel (different files, no dependencies)
- **[Story]**: Which user story this task belongs to (e.g., US1, US2, US3)
- Include exact file paths in descriptions

## Path Conventions

- **Single project**: `calculator/`, `tests/` at repository root

---

## Phase 1: Setup (Shared Infrastructure)

**Purpose**: Project initialization and basic structure

- [ ] T001 Create project directories: `calculator/` and `tests/` at the repository root.
- [ ] T002 Create `calculator/__init__.py` to mark it as a Python package.
- [ ] T003 [P] Configure linting (`flake8`) and formatting (`black`) tools (e.g., in `pyproject.toml` or `setup.cfg`).
- [ ] T004 [P] Configure `pytest` for testing (e.g., create `tests/conftest.py` if needed for common fixtures).

---

## Phase 2: Foundational (No specific tasks beyond Setup for this simple app)

**Purpose**: Core infrastructure that MUST be complete before ANY user story can be implemented

**⚠️ CRITICAL**: No user story work can begin until this phase is complete

This phase is considered complete after Phase 1 for this project, as there are no complex foundational elements like database setup or external API integrations required.

---

## Phase 3: User Story 1 - Basic Arithmetic Calculation (Priority: P1) 🎯 MVP

**Goal**: Implement the core arithmetic operations (+, -, \*, /) and the basic user interface to get and display results.

**Independent Test**: This story can be tested by running `calculator/main.py` with valid numeric inputs and operators, and verifying that the correct result is displayed.

### Tests for User Story 1

> **NOTE: Write these tests FIRST, ensure they FAIL before implementation**

- [ ] T005 [P] [US1] Write unit tests for the `add` function in `tests/test_operations.py`.
- [ ] T006 [P] [US1] Write unit tests for the `subtract` function in `tests/test_operations.py`.
- [ ] T007 [P] [US1] Write unit tests for the `multiply` function in `tests/test_operations.py`.
- [ ] T008 [P] [US1] Write unit tests for the `divide` function (excluding zero division) in `tests/test_operations.py`.

### Implementation for User Story 1

- [ ] T009 [US1] Implement `add(num1, num2)` function in `calculator/operations.py`.
- [ ] T010 [US1] Implement `subtract(num1, num2)` function in `calculator/operations.py`.
- [ ] T011 [US1] Implement `multiply(num1, num2)` function in `calculator/operations.py`.
- [ ] T012 [US1] Implement `divide(num1, num2)` function (basic implementation, without zero division handling yet) in `calculator/operations.py`.
- [ ] T013 [US1] Implement the main application loop to prompt for two numbers and an operator, call the respective operation from `operations.py`, and display the result in `calculator/main.py`.

**Checkpoint**: At this point, User Story 1 should be fully functional with valid inputs and testable independently.

---

## Phase 4: User Story 2 - Handling Invalid Input (Priority: P2)

**Goal**: Implement robust input validation and error handling for non-numeric inputs and division by zero.

**Independent Test**: This story can be tested by running `calculator/main.py` and providing invalid inputs (e.g., text, division by zero) and verifying that the correct error messages are displayed without crashing the application.

### Tests for User Story 2

- [ ] T014 [P] [US2] Write unit tests for `is_numeric(input_str)` validation function in `tests/test_validation.py`.
- [ ] T015 [P] [US2] Write unit tests for `is_valid_operator(op_str)` validation function in `tests/test_validation.py`.
- [ ] T016 [P] [US2] Write unit tests for `divide` function specifically for division by zero scenarios in `tests/test_operations.py` (e.g., ensuring it raises a specific error).

### Implementation for User Story 2

- [ ] T017 [US2] Implement `is_numeric(input_str)` function in `calculator/validation.py` to check if a string can be converted to a number.
- [ ] T018 [US2] Implement `is_valid_operator(op_str)` function in `calculator/validation.py` to check if an operator is one of `+`, `-`, `*`, `/`.
- [ ] T019 [US2] Integrate input validation from `calculator/validation.py` into `calculator/main.py` when prompting for numbers and operators, displaying user-friendly error messages for invalid inputs.
- [ ] T020 [US2] Modify `divide` function in `calculator/operations.py` to raise a specific error (e.g., `ValueError`) for division by zero, and handle this error gracefully in `calculator/main.py`.

**Checkpoint**: At this point, User Stories 1 AND 2 should both work, with error handling for invalid inputs and division by zero.

---

## Phase 5: Polish & Cross-Cutting Concerns

**Purpose**: Enhance code quality, documentation, and ensure adherence to standards.

- [ ] T021 [P] Add comprehensive docstrings to all functions and modules in `calculator/operations.py`, `calculator/validation.py`, and `calculator/main.py`.
- [ ] T022 [P] Run `black` formatter on all Python source files (`calculator/` and `tests/`) to ensure consistent code formatting.
- [ ] T023 [P] Run `flake8` linter on all Python source files (`calculator/` and `tests/`) to ensure PEP 8 compliance and catch style issues.
- [ ] T024 [P] Review and ensure comprehensive unit test coverage (e.g., using `pytest-cov` to generate a coverage report).

---

## Dependencies & Execution Order

### Phase Dependencies

-   **Setup (Phase 1)**: No dependencies - can start immediately.
-   **Foundational (Phase 2)**: Considered complete after Phase 1.
-   **User Story 1 (Phase 3)**: Depends on Setup completion.
-   **User Story 2 (Phase 4)**: Depends on Setup completion, and ideally after User Story 1's basic functionality is in place to integrate validation.
-   **Polish (Phase 5)**: Depends on all user stories' core implementations being complete.

### Within Each User Story

-   Tests MUST be written and FAIL before corresponding implementation tasks begin.
-   Implementation tasks within a story can proceed once tests are written.

### Parallel Opportunities

-   Setup tasks T003 and T004 can run in parallel.
-   Test writing tasks (T005-T008 for US1, T014-T016 for US2) can run in parallel within their respective stories.
-   Polish tasks (T021-T024) can largely run in parallel.
-   Different team members could work on US1 and US2 implementation if the setup is complete, though US2 integrates with US1's structure.

---

## Implementation Strategy

### MVP First (User Story 1 Only)

1.  Complete Phase 1: Setup
2.  Complete Phase 2: Foundational (CRITICAL - blocks all stories)
3.  Complete Phase 3: User Story 1
4.  **STOP and VALIDATE**: Test User Story 1 independently
5.  Deploy/demo if ready

### Incremental Delivery

1.  Complete Setup + Foundational → Foundation ready
2.  Add User Story 1 → Test independently → Deploy/Demo (MVP!)
3.  Add User Story 2 → Test independently → Deploy/Demo
4.  Each story adds value without breaking previous stories

### Parallel Team Strategy

With multiple developers:

1.  Team completes Setup + Foundational together
2.  Once Foundational is done:
    -   Developer A: User Story 1
    -   Developer B: User Story 2
3.  Stories complete and integrate independently

---

## Notes

-   [P] tasks = different files, no dependencies
-   [Story] label maps task to specific user story for traceability
-   Each user story should be independently completable and testable
-   Verify tests fail before implementing
-   Commit after each task or logical group
-   Stop at any checkpoint to validate story independently
-   Avoid: vague tasks, same file conflicts, cross-story dependencies that break independence


# Implementation  

## Screenshot-1  
<img width="522" height="180" alt="Screenshot 1" src="https://github.com/user-attachments/assets/91e276e5-191c-4788-88a6-d59041bbeaea" />  

## Screenshot-2  
<img width="469" height="111" alt="Screenshot 2" src="https://github.com/user-attachments/assets/c324a9e6-3acb-4cca-b656-201bb7cd8252" />  

## Screenshot-3  
<img width="463" height="115" alt="Screenshot 3" src="https://github.com/user-attachments/assets/8cd50485-80e9-4da0-bf75-873d5020dee6" />




