# Data Model: Create Robotics Textbook

**Date**: 2025-12-07

## Entities

### Module
- **Description**: Represents one of the 4 main sections of the course.
- **Attributes**:
    - `id`: Unique identifier (UUID or integer, auto-generated)
    - `title`: Name of the module (string)
    - `description`: Brief overview of the module (string, optional)
    - `weeks`: List of `Week` IDs belonging to this module (array of UUIDs/integers)

### Week
- **Description**: Represents a weekly unit of content within a module.
- **Attributes**:
    - `id`: Unique identifier (UUID or integer, auto-generated)
    - `title`: Name of the week (string)
    - `content`: Markdown content of the week (long string)
    - `moduleId`: Foreign key to `Module` (UUID or integer)
    - `order`: Order of the week within its module (integer)

### UserProgress
- **Description**: Represents a user's completion status for a module.
- **Attributes**:
    - `id`: Unique identifier (UUID or integer, auto-generated)
    - `userId`: Identifier for the user (string, optional for initial local storage implementation, but mandatory for future authentication)
    - `moduleId`: Foreign key to `Module` (UUID or integer)
    - `isCompleted`: Boolean indicating if the module is completed
    - `lastAccessed`: Timestamp of last access (datetime)

## Relationships

- `Module` has many `Week`s (one-to-many)
- `UserProgress` tracks `Module` completion for a `User` (many-to-many, via `moduleId` and `userId` if authenticated)

## Backend Considerations (RAG Chatbot)

### Document (for Qdrant)
- **Description**: Represents a chunk of textbook content stored in the vector database.
- **Attributes**:
    - `id`: Unique identifier (UUID, from original Week/Module content)
    - `text_content`: Text chunk for embedding (string)
    - `metadata`: Source information (e.g., `source_module`, `source_week`, `url`)

## Schema Evolution

- Anticipate minor changes for future features like personalization (e.g., adding user preferences to `UserProgress` or a new `UserProfile` entity).
- Versioning strategy for content and APIs will be considered as the project matures.
