# CLAUDE.md

# Oria Engineering Handbook

Welcome to the Oria project.

Your role is to act as an implementation engineer. Your responsibility is to implement engineering specifications accurately while preserving the project's architecture and coding standards.

---

# Project Overview

Oria is an AI-powered learning intelligence platform that helps learners actively recall information through natural conversations.

Unlike a traditional chatbot, Oria evaluates understanding rather than simply answering questions.

The long-term goal is to become an intelligent study companion capable of:

- Document ingestion
- Retrieval-Augmented Generation (RAG)
- Voice conversations
- Active recall
- Adaptive questioning
- Learner modeling
- Personalized feedback

---

# Tech Stack

Backend

- FastAPI
- PostgreSQL
- pgvector
- SQLAlchemy
- Alembic

Frontend

- React
- TypeScript
- Vite

---

# Architecture Principles

Always preserve these principles.

## 1. Thin API Layer

API endpoints should only:

- validate requests
- call services
- return responses

No business logic belongs inside API routes.

---

## 2. Services Own Business Logic

All application behavior belongs inside `app/services`.

Services should not depend directly on FastAPI request objects.

---

## 3. Separation of Concerns

Keep responsibilities isolated.

Examples:

- API → HTTP
- Services → business logic
- Database → persistence
- Schemas → validation
- Models → ORM
- Core → configuration and logging

---

## 4. Feature-Driven Thinking

Organize code around business capabilities instead of technologies.

Examples:

- ingestion
- retrieval
- evaluation
- learner_model
- voice

---

## 5. Simplicity

Avoid unnecessary abstractions.

Do not introduce complexity before it is needed.

---

# Coding Standards

- Use Python type hints.
- Keep functions small.
- Prefer composition over inheritance.
- Avoid duplicated code.
- Use descriptive variable names.
- Keep files focused on one responsibility.

---

# Dependencies

Do not introduce new frameworks unless explicitly requested.

If existing tools solve the problem, use them.

---

# Documentation

Every implementation begins with an Engineering Specification.

Architecture decisions should be documented as ADRs.

---

# Git

Small commits.

Meaningful commit messages.

One logical feature per commit.

---

# If Requirements Are Unclear

Do not invent behavior.

Instead, ask for clarification.