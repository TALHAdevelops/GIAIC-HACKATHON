---
id: 1
title: Create Constitution for AI Textbook
stage: constitution
date: 2025-12-07
surface: agent
model: gemini-pro
feature: none
branch: main
user: unknown
command: /sp.constitution
labels: [constitution, docusaurus, textbook]
links:
  spec: null
  ticket: null
  adr: null
  pr: null
files:
 - .specify/memory/constitution.md
 - .specify/templates/plan-template.md
tests:
 - none
---

## Prompt

/sp.constitution Create a constitution for building a comprehensive textbook on Physical AI & Humanoid Robotics using Docusaurus. The textbook should:

- Cover a 13-week course curriculum on Physical AI, ROS 2, Gazebo, Unity, NVIDIA Isaac, humanoid robots, and conversational robotics
- Be structured with clear weekly modules and learning outcomes
- Include interactive elements and be optimized for embedding a RAG chatbot
- Follow best practices for technical educational content
- Be deployable to GitHub Pages
- Support future features like personalization, translation to Urdu, and user authentication
- Use modern web technologies (React, Tailwind CSS via Docusaurus)
- Be accessible and follow web standards

The architecture should include:
- Docusaurus-based static site
- Content organized by weeks/modules with navigation
- Support for code examples, diagrams, and multimedia
- Placeholder sections for RAG chatbot integration
- Clean, professional design suitable for technical education

## Response snapshot

I have created a new constitution for the "Physical AI & Humanoid Robotics Textbook" project and updated the relevant project templates.

## Outcome

- ✅ Impact: A new constitution (v1.0.0) was created, defining the guiding principles for the project. The `plan-template.md` was updated to align with the new constitution.
- 🧪 Tests: none
- 📁 Files: 2 files modified: `.specify/memory/constitution.md` and `.specify/templates/plan-template.md`.
- 🔁 Next prompts: none
- 🧠 Reflection: Creating a constitution is a good first step to align on the project's goals and standards.

## Evaluation notes (flywheel)

- Failure modes observed: The `create-phr.sh` script was not found, requiring a fallback to the agent-native PHR creation flow.
- Graders run and results (PASS/FAIL): PASS
- Prompt variant (if applicable): null
- Next experiment (smallest change to try): Ensure the project setup includes all required scripts in the correct locations.
