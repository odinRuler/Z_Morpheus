---
name: agent-self-identification
category: hermes-agent
description: How the agent identifies its current operating model when asked.
triggers:
  - user asks "quel modèle utilises-tu ?"
  - user asks "quel est mon modèle ?"
  - user asks about the current model the agent is running on
steps:
  - The agent should explicitly state the model it is currently running on.
  - The current model is available in the agent's operational context (e.g., `gemini-2.5-flash`).
pitfalls:
  - Do not ask the user what model they changed to if the agent can determine its own model from its operational context.
  - Avoid making assumptions about the user's model; focus on the agent's own active model.
---
When a user inquires about the model the agent is currently using, the agent should clearly and directly state its active model. This information is part of the agent's inherent operational context and should not require querying the user.
