---
id: 2
title: Amend Constitution with Detailed Requirements
stage: constitution
date: 2025-12-07
surface: agent
model: gemini-pro
feature: none
branch: main
user: unknown
command: /sp.constitution
labels: [constitution, amendment, requirements]
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

/sp.constitution Specify the requirements for a Physical AI & Humanoid Robotics textbook with the following structure:

CONTENT STRUCTURE:
- Landing page introducing Physical AI and the course
- 13 weeks of content organized into 4 main modules:
  * Module 1: ROS 2 Fundamentals (Weeks 1-5)
  * Module 2: Robot Simulation with Gazebo & Unity (Weeks 6-7)
  * Module 3: NVIDIA Isaac Platform (Weeks 8-10)
  * Module 4: Humanoid Robots & Conversational AI (Weeks 11-13)

WEEKLY CONTENT REQUIREMENTS:
Week 1-2: Introduction to Physical AI
- Foundations of Physical AI and embodied intelligence
- From digital AI to robots understanding physical laws
- Humanoid robotics landscape overview
- Sensor systems: LIDAR, cameras, IMUs, force/torque sensors

Week 3-5: ROS 2 Fundamentals
- ROS 2 architecture and core concepts
- Nodes, topics, services, and actions
- Building ROS 2 packages with Python
- Launch files and parameter management

Week 6-7: Robot Simulation with Gazebo
- Gazebo simulation environment setup
- URDF and SDF robot description formats
- Physics simulation and sensor simulation
- Introduction to Unity for robot visualization

Week 8-10: NVIDIA Isaac Platform
- NVIDIA Isaac SDK and Isaac Sim
- AI-powered perception and manipulation
- Reinforcement learning for robot control
- Sim-to-real transfer techniques

Week 11-12: Humanoid Robot Development
- Humanoid robot kinematics and dynamics
- Bipedal locomotion and balance control
- Manipulation and grasping with humanoid hands
- Natural human-robot interaction design

Week 13: Conversational Robotics
- Integrating GPT models for conversational AI in robots
- Speech recognition and natural language understanding
- Multi-modal interaction: speech, gesture, vision

TECHNICAL REQUIREMENTS:
- Built with Docusaurus v3
- Responsive design for mobile and desktop
- Code syntax highlighting for Python, XML (URDF), YAML
- Support for embedding diagrams (Mermaid or images)
- Search functionality
- Progress tracking per module
- Placeholder for RAG chatbot widget (bottom-right corner)
- GitHub Pages deployment ready

FUTURE FEATURES TO PREPARE FOR:
- User authentication integration points
- Content personalization based on user background
- Urdu translation toggle
- Selected text highlighting for chatbot queries

## Response snapshot

I have amended the project constitution to version 1.1.0, incorporating the more detailed requirements you provided.

## Outcome

- ✅ Impact: The constitution was updated to v1.1.0 with more specific principles. The `plan-template.md` was also updated.
- 🧪 Tests: none
- 📁 Files: 2 files modified: `.specify/memory/constitution.md` and `.specify/templates/plan-template.md`.
- 🔁 Next prompts: none
- 🧠 Reflection: Amending the constitution with more detail provides greater clarity for the project's direction.

## Evaluation notes (flywheel)

- Failure modes observed: none
- Graders run and results (PASS/FAIL): PASS
- Prompt variant (if applicable): null
- Next experiment (smallest change to try): n/a
