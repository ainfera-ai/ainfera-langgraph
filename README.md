# ainfera-langgraph — LangGraph + Ainfera Routing

**LangGraph integration + Ainfera Routing.** Build stateful graphs and agents — inference routed through Ainfera with signed audit per turn.

Fleet dogfood: [Yavanna](https://ainfera.ai/agents) (LangGraph runtime).

## Quickstart (curl only)

No LangGraph install required — proves the OpenAI-compatible layer graphs call:

```bash
git clone https://github.com/ainfera-ai/ainfera-langgraph
cd ainfera-langgraph
./curl-example.sh   # signup → inference → audit verify
```

## Quickstart (LangGraph + ChatOpenAI)

```bash
pip install -r requirements.txt
export AINFERA_API_KEY=ai_infera_...  # https://app.ainfera.ai/signup
python main.py
```

`main.py` compiles a minimal `StateGraph` with one node using `ChatOpenAI` pointed at `https://api.ainfera.ai/v1`.

## LangGraph apps + Ainfera

Use any LangChain `ChatOpenAI` (or model binding) with:

- `base_url="https://api.ainfera.ai/v1"`
- `api_key=os.environ["AINFERA_API_KEY"]`

Budget caps, routing, and per-turn receipts are enforced at the Ainfera API — the graph code stays vanilla LangGraph.

## What this shows

- One Agent Card across providers (L1)
- Routed inference with per-call budget caps (L3)
- Hash-chained receipts per LLM turn (L4)

## Other frameworks

- [ainfera-letta](https://github.com/ainfera-ai/ainfera-letta) — Letta + memory blocks
- [ainfera-mcp](https://github.com/ainfera-ai/ainfera-mcp) — Claude Desktop + Cursor
- [ainfera-langchain](https://github.com/ainfera-ai/ainfera-langchain) — LangChain chains
- [ainfera-openai-compatible](https://github.com/ainfera-ai/ainfera-openai-compatible) — universal wedge

Apache 2.0. © Ainfera Inc. 2026.
