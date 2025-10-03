# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a warmup repository for the 10xDevs.pl training program. It contains TypeScript exercises focused on TDD practices, AI-assisted development workflows, and specification-driven implementation. The primary exercise is a banking system implementation in `banking/` with full test coverage.

## Commands

### Installation
```bash
npm install
```

### Testing
```bash
# Run all tests
npm test

# Run tests in watch mode
npx vitest --watch

# Run a specific test file
npx vitest banking/banking.test.ts
```

## Project Structure

The repository is organized into domain-specific modules with accompanying specifications and tests:

- **`banking/`** - Core banking system exercise
  - `banking.ts` - Domain logic implementation
  - `types.ts` - TypeScript interfaces and types
  - `banking.test.ts` - Vitest test suite
  - `banking-spec.md` - Functional requirements specification (in Polish)
  - `prompts/` - AI prompts for analysis and implementation guidance

- **`prompts/`** - Reusable AI prompts for different scenarios
  - `decomposer.md` / `decomposer_pl.md` - Task decomposition prompts
  - `unblocker.md` / `unblocker_pl.md` - Problem-solving prompts

- **`charts/`** - Mermaid diagram exercises
  - `request.md` - Diagram creation tasks

## Architecture & Patterns

### Testing Architecture
- **Framework**: Vitest 3.0.9
- **Pattern**: Specification-driven TDD - tests are derived from `banking-spec.md`
- **Structure**: Nested `describe`/`it` blocks mirroring business rules
- **Coverage**: Both happy paths and error cases with explicit error codes and messages

### Type System
- Strict TypeScript 5.8+ with `strict: true` in tsconfig
- Domain types defined in `types.ts` using interfaces
- Error handling via discriminated unions (`WithdrawalResult | WithdrawalError`)
- Error codes: `INSUFFICIENT_FUNDS`, `INVALID_AMOUNT`, `ACCOUNT_NOT_FOUND`

### Code Organization
- Domain logic isolated in feature modules (`banking/`)
- Supporting materials (specs, prompts) co-located with implementation
- Pure functions preferred with `const` declarations
- Transaction IDs generated using timestamp + random string pattern

## Coding Standards

From `CONVENTIONS.md` and `.github/copilot-instructions.md`:
- TypeScript 5.7+ with strict mode enabled
- Prefer `const` over `let` and `var`
- Avoid `any` type
- Two-space indentation with trailing commas
- Double-quoted imports
- PascalCase for types (`WithdrawalRequest`)
- camelCase for functions (`processWithdrawal`)

## Key Development Workflows

### Implementing New Features
1. Check `banking-spec.md` for functional requirements
2. Review or add corresponding test cases in `banking.test.ts`
3. Implement logic in `banking.ts` to satisfy tests
4. Ensure error handling returns proper error codes and messages

### Working with Tests
- Tests define the contract - implementation must match test expectations
- Error cases must return objects with `code` and `message` properties
- Success cases must return `success: true` with transaction details
- Use `npx vitest --watch` during development

### AI Collaboration Patterns
The `prompts/` directory contains structured prompts for:
- Breaking down complex problems into LLM-friendly steps
- Analyzing specifications and generating implementation plans
- Both English and Polish variants available

## Important Notes

- The repository includes Cursor commands in `.cursor/commands/` for various tasks
- Cursor rules in `.cursor/rules/hooks.mdc` define React Hooks compliance rules (for reference, not directly applicable to current banking exercise)
- Follow Conventional Commits pattern: `feat:`, `chore:`, `fix:`, etc.
- New test files should be named `<feature>.test.ts` beside the code they verify
