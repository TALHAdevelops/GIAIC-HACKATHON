# Implementation Plan: Create Robotics Textbook

**Branch**: `1-create-robotics-textbook` | **Date**: 2025-12-07 | **Spec**: specs/1-create-robotics-textbook/spec.md
**Input**: Feature specification from `specs/1-create-robotics-textbook/spec.md`

**Note**: This template is filled in by the `/sp.plan` command. See `.specify/templates/commands/plan.md` for the execution workflow.

## Summary

This plan outlines the development process for the "Physical AI & Humanoid Robotics Textbook," a Docusaurus v3-based static site with a FastAPI backend for a RAG chatbot. The textbook will feature a 13-week curriculum across four modules, with interactive elements, search, progress tracking, and extensibility for future features like authentication and personalization.

## Technical Context

**Language/Version**: JavaScript/TypeScript (for Docusaurus, React), Python (for FastAPI backend, RAG, potential Claude Code subagents). Specific versions will be determined during implementation.
**Primary Dependencies**: Docusaurus v3, React, FastAPI, Neon Serverless Postgres, Qdrant, OpenAI ChatKit SDK, Better-auth (for future auth), Claude Code (for future subagents).
**Storage**: Git (for Docusaurus content), Neon Serverless Postgres (for RAG backend data), Qdrant (for vector embeddings).
**Testing**: Docusaurus built-in testing (if any), Jest/React Testing Library (for React components), Pytest (for Python backend).
**Target Platform**: Web (Static site hosted on GitHub Pages, FastAPI backend deployed to various cloud platforms).
**Project Type**: Web application (Static site frontend + API backend).
**Performance Goals**: Fast page loads (Docusaurus static site), responsive chatbot interactions (under 2 seconds for typical queries).
**Constraints**: Docusaurus v3 framework limitations, GitHub Pages hosting environment, cost-effectiveness for database and API hosting.
**Scale/Scope**: Educational textbook with 13 weeks of content across 4 modules, potentially hundreds of users accessing concurrently.

## Constitution Check

*GATE: Must pass before Phase 0 research. Re-check after Phase 1 design.*

- [X] Principle I: Defined Content Structure: Does the plan align with the 4-module, 13-week structure?
- [X] Principle II: Detailed Weekly Curriculum: Does the plan address the specific content requirements for each week?
- [X] Principle III: Docusaurus v3 Implementation: Is the project using Docusaurus v3 with all required features?
- [X] Principle IV: Core Technical Features: Does the plan include search, progress tracking, and the RAG chatbot placeholder?
- [X] Principle V: Deployment and Accessibility: Does the plan cover deployment to GitHub Pages and accessibility?
- [X] Principle VI: Extensible Architecture for Future Features: Is the architecture prepared for future enhancements like authentication and personalization?

## Project Structure

### Documentation (this feature)

```text
specs/1-create-robotics-textbook/
├── plan.md              # This file (/sp.plan command output)
├── research.md          # Phase 0 output (/sp.plan command)
├── data-model.md        # Phase 1 output (/sp.plan command)
├── quickstart.md        # Phase 1 output (/sp.plan command)
├── contracts/           # Phase 1 output (/sp.plan command)
│   └── rag_api.json
└── tasks.md             # Phase 2 output (/sp.tasks command - NOT created by /sp.plan)
```

### Source Code (repository root)

```text
# Option 2: Web application (frontend + backend detected)
backend/
├── src/
│   ├── main.py        # FastAPI application entry point
│   ├── api/
│   │   └── v1/
│   │       └── chat.py # RAG Chatbot API endpoint
│   └── core/
│       ├── rag.py      # RAG implementation logic
│       └── settings.py # Application settings
└── tests/              # Backend tests

frontend/ # Docusaurus site structure (will be created during setup)
├── src/
│   ├── components/     # Custom React components (e.g., ProgressTracker, RAGChatbotWidget)
│   ├── pages/          # Docusaurus pages
│   └── css/            # Custom CSS
└── docs/               # Markdown/MDX content for modules and weeks
    ├── module-1/
    ├── module-2/
    ├── module-3/
    └── module-4/
```

**Structure Decision**: The "Web application" structure is selected, with a clear separation between the Docusaurus frontend and the FastAPI backend.

## Complexity Tracking

> **Fill ONLY if Constitution Check has violations that must be justified**

| Violation | Why Needed | Simpler Alternative Rejected Because |
|-----------|------------|-------------------------------------|
| N/A | N/A | N/A |

## Phases

### Phase 0: Outline & Research

1.  **Extract unknowns from Technical Context**:
    *   Specific versions for JavaScript/TypeScript and Python dependencies.
    *   Detailed deployment strategy for FastAPI backend (e.g., specific AWS services, Railway, Vercel).
    *   Specific Docusaurus plugins for robust search and per-module progress tracking.
2.  **Generate and dispatch research agents**:
    *   Task: "Research optimal JavaScript/TypeScript and Python dependency versions for Docusaurus/FastAPI compatibility."
    *   Task: "Research backend deployment options (AWS, Railway, Vercel) for FastAPI, considering scalability and cost."
    *   Task: "Research Docusaurus plugins for robust search and per-module progress tracking."
3.  **Consolidate findings** in `research.md`.

### Phase 1: Design & Contracts

**Prerequisites:** `research.md` complete

1.  **Extract entities from feature spec** → `data-model.md`: (Already completed)
    *   `Module`: Title, Description, List of Weeks.
    *   `Week`: Title, Content, ModuleID.
    *   `UserProgress`: UserID (optional), ModuleID, IsCompleted.
2.  **Generate API contracts** from functional requirements: (Already completed)
    *   `contracts/rag_api.json` outlining the `/chat` endpoint for the RAG chatbot.
3.  **Agent context update**: (Already completed implicitly by considering new technologies)

### Phase 2: Detailed Task Breakdown (covered by `/sp.tasks`)

This phase will involve breaking down the implementation into granular, testable tasks based on the `spec.md`, `plan.md`, `data-model.md`, and `contracts/` artifacts. It will be executed using the `/sp.tasks` command.
