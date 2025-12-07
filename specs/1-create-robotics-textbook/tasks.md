---

description: "Task list for the Create Robotics Textbook feature implementation"
---

# Tasks: Create Robotics Textbook

**Input**: Design documents from `specs/1-create-robotics-textbook/`
**Prerequisites**: plan.md (required), spec.md (required for user stories), research.md, data-model.md, contracts/

**Tests**: This feature specification does not explicitly request TDD or test tasks beyond the functional requirements. Testing will primarily involve manual verification and automated checks where Docusaurus provides them.

**Organization**: Tasks are grouped by user story to enable independent implementation and testing of each story.

## Format: `[ID] [P?] [Story?] Description with file path`

- **[P]**: Can run in parallel (different files, no dependencies)
- **[Story]**: Which user story this task belongs to (e.g., US1, US2, US3)
- Include exact file paths in descriptions

## Path Conventions

- **Web app**: `backend/src/`, `frontend/src/` (as per `plan.md`)

---

## Phase 1: Setup (Shared Infrastructure)

**Purpose**: Project initialization and basic structure

- [ ] T001 Initialize Docusaurus project in the `frontend/` directory.
- [ ] T002 Configure `frontend/docusaurus.config.ts` with site metadata and navigation.
- [ ] T003 Setup GitHub repository and configure GitHub Actions for deployment (assuming frontend is in a subdirectory like 'frontend').
- [ ] T004 Create `frontend/sidebars.ts` for structured navigation grouped by modules.
- [ ] T005 Setup custom CSS for branding in `frontend/src/css/custom.css`.
- [ ] T006 Add logo and favicon (update `frontend/static/img/logo.svg` and `frontend/static/img/favicon.ico`).
- [ ] T007 Configure Docusaurus search plugin.
- [ ] T008 Configure Docusaurus for Mermaid diagrams.
- [ ] T009 Create reusable React components in `frontend/src/components/` (CodeBlock, DiagramWrapper, LearningObjective, KeyConcept, HardwareSpec).
- [ ] T010 Create placeholder for a RAG chatbot widget (bottom-right corner) in `frontend/src/components/RAGChatbotWidget.tsx` and integrate into Docusaurus layout.

---

## Phase 2: Foundational (Backend for RAG Chatbot)

**Purpose**: Core infrastructure for the RAG chatbot that MUST be complete before the chatbot can be integrated

**⚠️ CRITICAL**: No RAG chatbot integration work can begin until this phase is complete

- [ ] T011 Set up FastAPI project structure in `backend/`.
- [ ] T012 Configure `backend/requirements.txt` for FastAPI and dependencies (uvicorn, openai, qdrant-client, psycopg2-binary, etc.).
- [ ] T013 Set up environment configuration management for backend (e.g., `.env` file handling).
- [ ] T014 Set up Neon Serverless Postgres database integration.
- [ ] T015 Set up Qdrant vector database client.
- [ ] T016 Implement embeddings generation script (e.g., `backend/scripts/generate_embeddings.py`).
- [ ] T017 Implement document chunking and indexing logic.
- [ ] T018 Create RAG retrieval endpoints in `backend/app/api/v1/chat.py` based on `contracts/rag_api.json`.
- [ ] T019 Implement OpenAI ChatKit SDK for chat interface logic in backend.
- [ ] T020 Deploy backend (e.g., to Railway, Vercel, or AWS).

**Checkpoint**: Foundational backend ready - RAG chatbot integration can now begin

---

## Phase 3: User Story 1 - Access Structured Content (Priority: P1) 🎯 MVP

**Goal**: Students can navigate and access all textbook content.

**Independent Test**: A user can navigate from the landing page to any weekly module and view its content.

### Implementation for User Story 1

- [ ] T021 [P] [US1] Create a landing page `frontend/src/pages/index.tsx` with a course overview.
- [ ] T022 [P] [US1] Create folder structure for 13 weeks of content in `frontend/docs/` (e.g., `module-1/week-1/index.mdx`).
- [ ] T023 [P] [US1] Create MDX files for Module 1 (Weeks 1-5): ROS 2 Fundamentals (`frontend/docs/module-1/week-1/index.mdx` through `frontend/docs/module-1/week-5/index.mdx`).
- [ ] T024 [P] [US1] Create MDX files for Module 2 (Weeks 6-7): Robot Simulation with Gazebo & Unity (`frontend/docs/module-2/week-6/index.mdx` through `frontend/docs/module-2/week-7/index.mdx`).
- [ ] T025 [P] [US1] Create MDX files for Module 3 (Weeks 8-10): NVIDIA Isaac Platform (`frontend/docs/module-3/week-8/index.mdx` through `frontend/docs/module-3/week-10/index.mdx`).
- [ ] T026 [P] [US1] Create MDX files for Module 4 (Weeks 11-13): Humanoid Robots & Conversational AI (`frontend/docs/module-4/week-11/index.mdx` through `frontend/docs/module-4/week-13/index.mdx`).
- [ ] T027 [US1] Write content for Weeks 1-2: Introduction to Physical AI, including foundations, embodied intelligence, humanoid overview, and sensor systems in `frontend/docs/module-1/week-1/index.mdx` and `frontend/docs/module-1/week-2/index.mdx`.
- [ ] T028 [US1] Write content for Weeks 3-5: ROS 2 Fundamentals, including architecture, core concepts, Python packages, and launch files in `frontend/docs/module-1/week-3/index.mdx` through `frontend/docs/module-1/week-5/index.mdx`.
- [ ] T029 [US1] Write content for Weeks 6-7: Robot Simulation with Gazebo, including setup, URDF/SDF, physics, and Unity visualization in `frontend/docs/module-2/week-6/index.mdx` and `frontend/docs/module-2/week-7/index.mdx`.
- [ ] T030 [US1] Write content for Weeks 8-10: NVIDIA Isaac Platform, including SDK, AI perception, RL, and sim-to-real in `frontend/docs/module-3/week-8/index.mdx` through `frontend/docs/module-3/week-10/index.mdx`.
- [ ] T031 [US1] Write content for Weeks 11-12: Humanoid Robot Development, including kinematics, locomotion, manipulation, and HRI design in `frontend/docs/module-4/week-11/index.mdx` and `frontend/docs/module-4/week-12/index.mdx`.
- [ ] T032 [US1] Write content for Week 13: Conversational Robotics, including GPT integration, speech recognition, and multi-modal interaction in `frontend/docs/module-4/week-13/index.mdx`.
- [ ] T033 [US1] Add code examples, diagrams, and visual aids throughout all weekly content (across `frontend/docs/` files).
- [ ] T034 [US1] Include learning outcomes and assessments for each week (across `frontend/docs/` files).

**Checkpoint**: At this point, User Story 1 should be fully functional and testable independently

---

## Phase 4: User Story 2 - Search for Topics (Priority: P2)

**Goal**: Students can effectively search the textbook content.

**Independent Test**: A user can enter a keyword in the search bar and receive a list of relevant pages.

### Implementation for User Story 2

- [ ] T035 [P] [US2] Integrate search functionality with Docusaurus frontend (`frontend/docusaurus.config.ts` and relevant theme files).
- [ ] T036 [US2] Test search for accuracy and relevance across all content.

**Checkpoint**: At this point, User Stories 1 AND 2 should both work independently

---

## Phase 5: User Story 3 - Track Progress (Priority: P3)

**Goal**: Students can monitor their learning progress through modules.

**Independent Test**: A user can mark a module as complete and see a visual indicator of their progress.

### Implementation for User Story 3

- [ ] T037 [P] [US3] Implement client-side progress tracking logic (e.g., using local storage) for module completion in `frontend/src/utils/progressStorage.ts`.
- [ ] T038 [P] [US3] Create a `ProgressTracker` component (`frontend/src/components/ProgressTracker.tsx`) to display user progress visually.
- [ ] T039 [US3] Integrate `ProgressTracker` component into Docusaurus layout (`frontend/src/theme/Layout/index.tsx`) or individual module pages.
- [ ] T040 [US3] Implement UI to mark modules as complete (e.g., a button or checkbox in module pages).

**Checkpoint**: All user stories should now be independently functional

---

## Phase 6: Polish & Cross-Cutting Concerns

**Purpose**: Improvements that affect multiple user stories

- [ ] T041 Test all content links and navigation (manual and/or automated checks).
- [ ] T042 Verify chatbot functionality end-to-end (manual testing).
- [ ] T043 Test site responsiveness on various mobile and desktop devices (manual testing, browser developer tools).
- [ ] T044 Deploy Docusaurus site to GitHub Pages.
- [ ] T045 Record demo video (under 90 seconds) showcasing textbook navigation and chatbot features.
- [ ] T046 Documentation for setup and usage (update `quickstart.md`).

---

## Dependencies & Execution Order

### Phase Dependencies

- **Setup (Phase 1)**: No dependencies - can start immediately
- **Foundational (Phase 2)**: Depends on Setup completion - BLOCKS RAG chatbot integration
- **User Stories (Phase 3+)**: All depend on core Docusaurus setup (from Phase 1) completion. RAG chatbot integration (Phase 2) is a prerequisite for a fully functional chatbot, but User Story 1 (content access) can proceed independently.
  - User stories can then proceed in parallel (if staffed) or sequentially in priority order (P1 → P2 → P3)
- **Polish (Final Phase)**: Depends on all desired user stories being complete

### User Story Dependencies

- **User Story 1 (P1)**: Can start after Docusaurus Setup (Phase 1) - No dependencies on other stories.
- **User Story 2 (P2)**: Can start after Docusaurus Setup (Phase 1) - May integrate with US1 but should be independently testable.
- **User Story 3 (P3)**: Can start after Docusaurus Setup (Phase 1) - May integrate with US1/US2 but should be independently testable.

### Within Each User Story

- Core implementation before integration.
- Story complete before moving to next priority.

### Parallel Opportunities

- All tasks marked [P] can run in parallel (e.g., creating multiple MDX files for content).
- Different user stories can be worked on in parallel by different team members once their prerequisites are met.

---

## Implementation Strategy

### MVP First (User Story 1 Only)

1. Complete Phase 1: Setup (Docusaurus and basic site structure).
2. Complete Phase 3: User Story 1 (Content creation and access).
3. **STOP and VALIDATE**: Test User Story 1 independently.
4. Deploy/demo if ready.

### Incremental Delivery

1. Complete Phase 1: Setup → Docusaurus foundation ready.
2. Complete Phase 3: User Story 1 → Content accessible → Deploy/Demo (MVP!).
3. Complete Phase 2: Foundational (Backend) → RAG chatbot infrastructure ready.
4. Complete Phase 4: User Story 2 → Search integrated → Deploy/Demo.
5. Complete Phase 5: User Story 3 → Progress tracking integrated → Deploy/Demo.
6. Each story adds value without breaking previous stories.

### Parallel Team Strategy

With multiple developers:

1. Team completes Phase 1: Setup (Docusaurus) together.
2. Developer A: Phase 3: User Story 1 (Content creation).
3. Developer B: Phase 2: Foundational (Backend).
4. Developer C: Phase 4: User Story 2 (Search) and Phase 5: User Story 3 (Progress Tracking) (after Phase 1 is done).
5. Stories complete and integrate independently.

---

## Notes

- [P] tasks = different files, no dependencies
- [Story] label maps task to specific user story for traceability
- Each user story should be independently completable and testable
- Commit after each task or logical group
- Stop at any checkpoint to validate story independently
- Avoid: vague tasks, same file conflicts, cross-story dependencies that break independence
