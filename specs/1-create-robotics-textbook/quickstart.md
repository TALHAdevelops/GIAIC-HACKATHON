# Quickstart Guide: Physical AI & Humanoid Robotics Textbook

**Date**: 2025-12-07

## Overview

This guide provides instructions to quickly set up and run the "Physical AI & Humanoid Robotics Textbook" project locally, and to deploy it to GitHub Pages.

## Prerequisites

- Node.js (v18 or higher)
- npm or yarn
- Git
- Python (v3.9 or higher)
- pip
- Docker (for local Qdrant/Postgres setup, optional)

## 1. Clone the Repository

```bash
git clone https://github.com/your-username/physical-ai-robotics-textbook.git
cd physical-ai-robotics-textbook
```

## 2. Setup Docusaurus Frontend

```bash
# Install dependencies
npm install # or yarn install

# Start local development server
npm start # or yarn start
```
The textbook frontend should now be accessible in your browser at `http://localhost:3000`.

<h2>3. Setup RAG Chatbot Backend (Optional)</h2>

This project includes a FastAPI backend for the RAG chatbot.

<h3>Backend Prerequisites</h3>
- A Neon Serverless Postgres database instance (connection string required).
- A Qdrant instance (local Docker or cloud service).
- OpenAI API Key.

<h3>Environment Configuration</h3>
Create a `.env` file in the `physical-ai-robotics-textbook/physical-ai-robotics-textbook/backend` directory:

```
OPENAI_API_KEY="YOUR_OPENAI_API_KEY"
DATABASE_URL="YOUR_NEON_POSTGRES_CONNECTION_STRING"
QDRANT_HOST="localhost" # or your Qdrant host
QDRANT_PORT="6333" # or your Qdrant port
```

<h3>Run Backend</h3>
```bash
cd physical-ai-robotics-textbook/backend

# Install dependencies
pip install -r requirements.txt

# Run the FastAPI application
uvicorn app.main:app --reload
```
The backend API should now be running at `http://localhost:8000`.

<h2>4. Deploy to GitHub Pages</h2>

To deploy the Docusaurus site to GitHub Pages:

1.  Ensure your `docusaurus.config.ts` is correctly configured for GitHub Pages deployment (e.g., `baseUrl`, `projectName`).
2.  Run the deployment command:
    ```bash
    npm run deploy # or yarn deploy
    ```
    This will build the static assets and push them to the `gh-pages` branch of your repository.

<h2>Next Steps</h2>

- Start writing content for your modules and weeks in the `docs/` directory.
- Refer to the Docusaurus documentation for advanced customization.
- Explore the FastAPI documentation for backend development.
