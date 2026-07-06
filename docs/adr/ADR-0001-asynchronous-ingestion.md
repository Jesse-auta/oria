# ADR-0001

## Title

Use asynchronous document ingestion.

---

## Status

Accepted

---

## Context

Document processing may involve OCR, parsing, embedding generation, and indexing.

These operations are computationally expensive and unsuitable for synchronous request handling.

---

## Decision

The ingestion pipeline will execute asynchronously.

API endpoints will immediately acknowledge upload requests while background workers process the document.

---

## Consequences

### Benefits

- Better user experience
- Improved scalability
- Lower request latency
- Easier retry mechanisms

### Trade-offs

- Increased architectural complexity
- Job tracking required