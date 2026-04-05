# AI Agents - 6 Must Know Terms
*Source: AI Matt (@aimattant)*

---

## 1. Model Context Protocol (MCP)

A universal standard introduced by Anthropic for **connecting AI applications to external data sources and tools**. Think of it as "USB-C for AI" - one protocol that any MCP-compatible application can use to connect to any MCP server, eliminating the need for custom integrations.

**Architecture:** Agent -> MCP Client(s) -> MCP Server(s) -> External Tools/Data

---

## 2. Single-Agent Architecture

A system where **one agent handles the entire pipeline**, making all decisions about when to search, summarize, or generate responses. The agent acts as both the user and architect of context.

---

## 3. Skills

The specific **capabilities or tools an agent can leverage to complete tasks** - such as accessing databases, calling APIs, or performing searches. These are the building blocks of what an agent can actually do.

**Architecture:** Agent -> Skill Loader -> Skills/Capabilities

---

## 4. Multi-Agent Architecture

A system where multiple specialized **agents work together**, each taking on specific roles that contribute to a larger goal. This allows for more complex task decomposition and parallel processing.

---

## 5. Agentic RAG

An AI agent-based implementation of Retrieval-Augmented Generation that uses agents to orchestrate the RAG pipeline. Unlike traditional RAG, agentic RAG can **dynamically route queries, validate retrieved information**, and make **decisions** about re-retrieval.

**Flow:** Query -> Agent -> Context Retrieval -> Validation -> Response

---

## 6. Memory

The component that **stores context**, prior interactions, and data collected during task execution.

Includes both **short-term memory** (in the context window) and **long-term memory** (retrieved on demand).

**Memory Layer Components:**
- Write Control
- Deduplication
- Reconciliation
- Amendment
- Purposeful Forgetting

---

## Key Takeaways

- **MCP** = Universal connector for AI tools (like USB-C)
- **Single-Agent** = One agent does everything
- **Skills** = The tools an agent can use
- **Multi-Agent** = Specialized agents collaborating
- **Agentic RAG** = Smart retrieval with agent decision-making
- **Memory** = Short-term + long-term context storage
