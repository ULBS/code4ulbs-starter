# Project Copilot Instructions

## Project Overview

General information about the project and its architecture.

## Coding Conventions

- Use TypeScript strict mode
- Follow functional programming patterns
- Use async/await for asynchronous operations
- Minimum 80% code coverage required for new code

## Testing

- Unit tests: Jest
- E2E tests: Playwright

## Design System

- Follow [ULBS Visual Guidelines](https://www.figma.com/design/6l4FWSiHc1u4oCUwRS3Q2s/ULBS-Visual-guidelines)

## Workflows & Runners

- **Avoid default GitHub runners** (e.g., `ubuntu-latest`, `windows-latest`).
- **Use ULBS organization runners** for all workflows.
- Use the runner label: `build-01` (or others as specified by the organization).

## Common Patterns

- Repository pattern for data access
- DTOs for data transfer
- Middleware for authentication/authorization
