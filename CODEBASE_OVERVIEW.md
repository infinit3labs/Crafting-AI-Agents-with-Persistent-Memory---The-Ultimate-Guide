# Codebase Directory Overview

High-level map of the repository with notes on what each area contains and the skills you can build by exploring it.

## Root
- `README.md` and `requirements.txt` document the course context and core Python dependencies (LangChain, LangGraph, langmem, mem0, Supabase tooling, etc.).
- `.env.example` shows expected environment variables for cloud integrations.

## adk-test/multi_tool_agent
- `agent.py` defines a small Google ADK-based multi-tool agent that can report weather/time and exposes them via `Agent`.
- Learn how to register simple Python functions as tools in the ADK, set model metadata, and shape structured responses for testing.

## agents_with_mem
- `customer_supp.py` builds a LangGraph customer-support agent with triage and response stages, tool use (ticketing, messaging, memory helpers), and an in-memory store.
- `test_customer_sup_agent.py` contains a basic test scaffold for this flow.
- Learn to compose multi-node LangGraph workflows, use structured output for routing, and plug simple memory/search abstractions into a support workflow.

## bedrock
- Standalone scripts for Amazon Bedrock: simple invoke/converse examples, CLI helpers, and Streamlit tools (`scraper_final.py`) that call Bedrock agents with SigV4 signing.
- Includes Lambda-friendly scrapers and OpenAI tool schemas for web scraping/time functions.
- Learn Bedrock client patterns (invoke vs. converse), request signing, and building lightweight agent UIs and Lambda utilities around Bedrock.

## langmem-agents
- Examples using LangGraph’s `InMemoryStore` with the `langmem` toolkit: `simple_mem_agent.py`, `coach.py`, and `recipe_assis.agent.py`.
- Learn to add memory management/search tools to ReAct agents and persist conversational context with embeddings.

## mem0
- Streamlit apps and scripts that pair `mem0` memory storage with OpenAI models and Supabase (`final_coach_mem0_supa.py`, `mem0_supabase.py`, `mem0_supabase_simple.py`), plus lightweight local/API demos.
- Learn to configure `mem0` backends, add/authenticate users via Supabase, and build memory-aware assistants (health coach, generic chat) that store and retrieve conversational memories.

## raw_agent_with_memory
- `agent_with_memory.py` implements a framework-agnostic memory system (facts, procedures, episodic and working memory) with JSON persistence; `memory_visualization.py` offers inspection helpers; `agent_memory/` stores persisted data.
- Learn core memory architecture concepts (semantic/episodic/procedural/working memory), simple ranking/search heuristics, and how to generate LLM context from custom memory stores.
