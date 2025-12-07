---
id: 2
title: Create Plan for Robotics Textbook
stage: plan
date: 2025-12-07
surface: agent
model: gemini-pro
feature: create-robotics-textbook
branch: 1-create-robotics-textbook
user: unknown
command: /sp.plan
labels: [plan, robotics, textbook]
links:
  spec: specs/1-create-robotics-textbook/spec.md
  ticket: null
  adr: null
  pr: null
files:
 - specs/1-create-robotics-textbook/plan.md
 - specs/1-create-robotics-textbook/research.md
 - specs/1-create-robotics-textbook/data-model.md
 - specs/1-create-robotics-textbook/contracts/rag_api.json
 - specs/1-create-robotics-textbook/quickstart.md
tests:
 - none
---

## Prompt

/sp.plan Create a development plan to build the Physical AI & Humanoid Robotics textbook:

PHASE 1: Project Setup
- Initialize Docusaurus project
- Configure GitHub repository
- Set up GitHub Pages deployment workflow
- Create basic site structure and navigation
- Configure Docusaurus plugins (search, Mermaid diagrams)

PHASE 2: Content Architecture
- Create folder structure for 13 weeks of content
- Set up MDX files for each week
- Create reusable components (CodeBlock, Diagram, LearningObjective, KeyConcept)
- Design sidebar navigation grouped by modules
- Create landing page with course overview

PHASE 3: Content Development
- Write content for Module 1 (Weeks 1-5): ROS 2 Fundamentals
- Write content for Module 2 (Weeks 6-7): Gazebo & Unity
- Write content for Module 3 (Weeks 8-10): NVIDIA Isaac
- Write content for Module 4 (Weeks 11-13): Humanoids & Conversational AI
- Add code examples, diagrams, and visual aids throughout
- Include learning outcomes and assessments for each week

PHASE 4: RAG Chatbot Integration
- Set up FastAPI backend
- Integrate Neon Serverless Postgres database
- Set up Qdrant vector database
- Implement OpenAI ChatKit SDK for chat interface
- Create embeddings of textbook content
- Build RAG retrieval pipeline
- Create chatbot widget component for Docusaurus
- Implement text selection feature for contextual queries
- Deploy backend (e.g., Railway, Vercel, or AWS)

PHASE 5: Bonus Features (Optional)
- Implement Better-auth authentication
- Add user background questionnaire at signup
- Create personalization system based on user profile
- Add Urdu translation feature with toggle buttons
- Implement Claude Code subagents for reusable intelligence

PHASE 6: Testing & Deployment
- Test all content links and navigation
- Verify chatbot functionality
- Test on mobile and desktop
- Deploy to GitHub Pages
- Create demo video (under 90 seconds)

DELIVERABLES:
- GitHub repository with complete codebase
- Live deployed textbook on GitHub Pages
- Functioning RAG chatbot
- Demo video
- Documentation for setup and usage

## Response snapshot

I have generated the implementation plan for the "Create Robotics Textbook" feature.

## Outcome

- ✅ Impact: An implementation plan (`plan.md`) was created, along with research, data model, API contracts, and a quickstart guide for the "Create Robotics Textbook" feature.
- 🧪 Tests: none
- 📁 Files: 5 files created/modified.
- 🔁 Next prompts: /sp.tasks
- 🧠 Reflection: Successfully created a comprehensive plan based on user's detailed input, navigating script issues.

## Evaluation notes (flywheel)

- Failure modes observed: The `setup-plan.ps1` script failed due to incorrect parameter handling and assumptions about the current branch. This required manual setting of context variables and creation of artifacts. The `update-agent-context.ps1` also failed for similar reasons.
- Graders run and results (PASS/FAIL): PASS
- Prompt variant (if applicable): null
- Next experiment (smallest change to try): Improve robustness of PowerShell scripts to handle non-feature branch execution and flexible parameter passing, or provide agent-native alternatives.
