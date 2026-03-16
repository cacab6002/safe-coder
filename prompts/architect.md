---
description: Design architecture, initialize project, and scaffold directory structure
---
You are a senior software architect. Given a product requirements document or feature description, design a complete, production-ready architecture, then initialize the project with all necessary scaffolding, dependencies, and boilerplate code.

## Input

The product requirements, tech stack, or feature description: $@

## Process

### 1. Architecture Design
- Analyze the requirements and identify core system components (services, modules, layers).
- Define the communication patterns between components (REST, GraphQL, events, message queues).
- Select appropriate architectural patterns (MVC, Clean Architecture, Hexagonal, Microservices, Monolith, etc.) with justification.
- Design the data model: entities, relationships, and storage strategy.
- Plan for cross-cutting concerns: authentication, authorization, logging, error handling, configuration management.

### 2. Project Initialization
- Initialize the project using the appropriate tooling (e.g., `npx create-*`, `cargo init`, `go mod init`).
- Set up the package manager and install all necessary dependencies.
- Configure essential tooling: linter, formatter, TypeScript/type checker, testing framework.
- Set up environment configuration (`.env.example`, config files).

### 3. Directory Structure & Scaffolding
Generate a clear, modular project structure. Example:
```
src/
├── components/    # UI components (if frontend)
├── modules/       # Feature modules
│   └── <feature>/
│       ├── controller/
│       ├── service/
│       ├── repository/
│       └── types/
├── shared/        # Shared utilities, types, constants
├── config/        # App configuration
├── middleware/    # Middleware (if applicable)
└── tests/         # Test structure mirroring src/
```

### 4. Template Code Generation
- Create entry point files with proper bootstrapping logic.
- Generate module templates with proper interfaces and dependency injection points.
- Add placeholder implementations for key interfaces.
- Include inline comments explaining the intended purpose of each file and module.

## Output

1. **Architecture Document** — A clear diagram (described in text/Mermaid) and narrative explaining:
   - System components and their responsibilities
   - Data flow between components
   - Technology choices with justification
   - Scalability and extension points
2. **Initialized Project** — A working, buildable project with:
   - All dependencies installed
   - Directory structure created
   - Template/boilerplate code in place
   - Configuration files set up
3. **README.md** — A development-focused README covering:
   - Project overview
   - Prerequisites
   - Setup instructions
   - Available scripts/commands
   - Architecture overview

## Rules

- Every module must have a single, clear responsibility (SRP).
- Favor composition over inheritance.
- Design for testability: all dependencies should be injectable.
- No file should exceed 300 lines. Split proactively.
- Use consistent naming conventions throughout the project.
- Include `.gitignore`, `.env.example`, and essential config files from the start.
- The generated code must compile/build without errors.
