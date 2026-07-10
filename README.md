<div align="center">

# 🧠 Multi‑Agent Blog Writer

**Hierarchical multi‑agent blog writing demo using LangGraph, LangChain, OpenRouter and Tavily.**

<p align="center">
    <img src="assets/hero.png" alt="Multi-Agent Blog Writer hero" style="max-width:100%;height:auto;border-radius:8px;" />
</p>

[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?style=for-the-badge&logo=jupyter)](multi_agent_blog_writer.ipynb)
[![Python](https://img.shields.io/badge/Python-3.13-blue?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![LangGraph](https://img.shields.io/badge/LangGraph-%3E%3D0.5.4-lightgrey?style=for-the-badge)](https://github.com/langgraph/langgraph)
[![LangChain](https://img.shields.io/badge/LangChain-core-blue?style=for-the-badge)](https://langchain.com)
[![OpenRouter](https://img.shields.io/badge/OpenRouter-supported-00BFFF?style=for-the-badge)](https://openrouter.ai)
[![Tavily](https://img.shields.io/badge/Tavily-search-FF6B6B?style=for-the-badge)](https://tavily.ai)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](LICENSE)

</div>

---

## Project summary

This repository contains a notebook‑first implementation of a hierarchical multi‑agent system that coordinates a research team and a writing team to produce researched articles. The implementation is modular: each team is implemented as a LangGraph subgraph and a top‑level supervisor routes tasks between them.

Key capabilities
- Supervisor‑based routing between teams
- Web search (Tavily) + webpage scraping for research
- Outline generation, document drafting and editing
- Executable Python REPL tool for chart generation
- Persisted output files in `temp/`

The primary deliverable is `multi_agent_blog_writer.ipynb` — run it to reproduce the system end‑to‑end.

---

## Quick start (developer)

Prerequisites: Python 3.13+ and `pip`.

1. Install runtime dependencies:

```bash
# broken-down pip installs

pip install -U jupyterlab
pip install -U langgraph
pip install -U langchain-core
pip install -U langchain-openai
pip install -U langchain-tavily
pip install -U langchain_community
pip install -U langchain_experimental
pip install -U python-dotenv
pip install -U pydantic
pip install -U rich
```

2. Launch Jupyter Lab and open the notebook:

```bash
jupyter lab
# open `multi_agent_blog_writer.ipynb` and run cells in order
```

Notes:
- The notebook is organized into clearly named sections; run cells in order.
- Outputs (generated articles and outlines) are saved to the `temp/` folder.

---

## Configuration — environment variables

Create a file named `.env` (or set these variables in your environment) with the following keys:

```env
# OpenRouter (preferred model endpoint)
OPENROUTER_API_KEY=your_openrouter_api_key_here
OPENROUTER_BASE_URL=https://openrouter.ai/api/v1

# Tavily (web search / extraction)
TAVILY_API_KEY=your_tavily_api_key_here
```

The notebook includes a small helper that prompts interactively for missing keys if they are not present in the environment.

---

## Notebook sections

- **Preliminary Setup** — API keys and environment helpers
- **All Imports** — required imports from LangGraph / LangChain / Tavily
- **Define the Tools** — tool wrappers: scraping, read/write/edit, python repl
- **Define the Supervisor** — router node with structured output
- **Define the Agent Teams** — research subgraph and writing subgraph
- **End‑to‑end Graph** — compose subgraphs and run the full pipeline

---

## Demo & screenshots

Include high‑quality screenshots (recommended) in `assets/`:

- `assets/hero.png` — hero banner showing the high‑level architecture (preferred size: 1400×420)
- `assets/notebook_step.png` — screenshot of the notebook showing running cells (preferred size: 1200×800)

Place images in `assets/` and reference them from the notebook or README with relative paths.

---

## Results and artifacts

Generated sample outputs are stored in `temp/` (example files included):

- `dog_poem.txt`, `dog_poem_outline.txt`
- `gold_price_factors_2025.txt`, `gold_price_factors_2025_outline.txt`

Use these as examples for expected output format and file locations.

---

## Contributing

Contributions are welcome. Suggested workflow:

1. Fork the repository and create a feature branch
2. Add changes and tests (where applicable)
3. Open a pull request describing the change

Please keep the notebook reproducible and document any added dependencies in the README.

---

## License

MIT — see the `LICENSE` file for details.

---

<sub>Created for learning and experimentation. </sub>
---
