# Hospital-ChatBot-Front-end-project-
🧱 Architecture

The application follows a chatbot-first, intent-driven front-end architecture.
There is no page navigation or backend—the chatbot itself acts as the complete user interface.

High-level flow:

User Input → Gemini AI → Intent Resolver → UI Renderer → Local State Update


Key architectural principles:

Single-page conversational UI

Intent-based UI rendering

Local in-memory state management

Modular and reusable components

Conversation context preserved throughout the session

All hospital data (reports, appointments, pregnancy records, vitals) is stored and managed in local React state using the provided mock dataset.

🔁 Intent Flow

The user types a natural language message in the chat.

The message is sent to Gemini AI for intent classification.

Gemini AI returns a structured JSON containing:

Detected intent

Extracted entities (e.g., report ID, date)

The intent resolver maps the intent to a specific UI component.

The chatbot renders the corresponding UI (cards, tables, forms) inline.

Any CRUD action updates the local state and reflects instantly in the chat.

This approach ensures a smooth, uninterrupted conversational experience.

🤖 How AI Is Integrated

Gemini AI is used only for intelligence, not for data storage or UI rendering.

AI responsibilities:

Classify user intent

Extract relevant entities from natural language input

Model used:

gemini-1.5-flash

The front-end sends a prompt to Gemini AI and expects a JSON-only response.
If AI fails or returns an unknown intent, the system falls back gracefully with a help response, ensuring the UI never breaks.
