🛡️ SentinelAI — LLM Safety Gateway
SentinelAI is an AI safety middleware layer designed to make LLM-powered applications safer and more reliable.

It acts as a gateway between the user and the Large Language Model (LLM), validating both incoming prompts and generated responses using configurable safety guardrails. The system helps detect sensitive information, unsafe content, jailbreak attempts, prompt injection patterns, and policy violations before they reach the model or the user.

🚀 Overview
Modern LLM applications can be vulnerable to malicious prompts, sensitive data exposure, unsafe outputs, and attempts to bypass system instructions.

SentinelAI addresses these risks by introducing a safety layer around the LLM:

## System Architecture

```mermaid
flowchart TD
    A[👤 User] --> B[🛡️ Input Guardrails]

    B --> B1[PII Detection]
    B --> B2[Content Moderation]
    B --> B3[Jailbreak Detection]
    B --> B4[Prompt Injection Detection]
    B --> B5[Custom Safety Checks]

    B1 --> C{Input Safe?}
    B2 --> C
    B3 --> C
    B4 --> C
    B5 --> C

    C -->|Yes| D[🤖 LLM]
    C -->|No| E[❌ Block / Reject Request]

    D --> F[🛡️ Output Guardrails]

    F --> F1[Content Validation]
    F --> F2[PII Detection]
    F --> F3[Policy Validation]
    F --> F4[Safety Checks]

    F1 --> G{Output Safe?}
    F2 --> G
    F3 --> G
    F4 --> G

    G -->|Yes| H[✅ Safe Response]
    G -->|No| I[❌ Block / Sanitize Response]

    H --> A
