# AI Tools Comparison: ChatGPT vs Claude vs Gemini

A data analysis project comparing three leading AI assistants — **ChatGPT (GPT-5.1)**, **Claude (Opus 4.8)**, and **Gemini (2.5 Pro)** — across benchmark performance, pricing, and real-world user satisfaction.

## 📁 Project Structure

```
ai-tools-comparison/
├── data/
│   ├── ai_tools_benchmarks.csv      # Benchmark scores, pricing, context window, speed
│   └── user_survey.csv              # Simulated user survey (satisfaction, use case, etc.)
├── src/
│   └── analyze.py                   # Main analysis script — generates all charts + summary CSVs
├── notebooks/
│   └── exploration.ipynb            # Interactive Jupyter notebook for ad-hoc analysis
├── visuals/                          # Generated PNG charts (created after running analyze.py)
├── reports/                           # Generated summary CSVs (created after running analyze.py)
├── requirements.txt
└── README.md
```

## 📊 Dataset Description

### `ai_tools_benchmarks.csv`
Columns: `tool`, `model_version`, `category`, `benchmark`, `score`, `unit`, `date_recorded`, `source`

Covers:
- **Reasoning**: MMLU
- **Coding**: HumanEval, SWE-bench
- **Math**: GSM8K, MATH
- **Multimodal**: MMMU
- **Context window**: max tokens supported
- **Speed**: tokens/sec generation
- **Pricing**: input/output cost per million tokens

> ⚠️ Note: benchmark figures are illustrative placeholder values reflecting plausible ranges as of early 2026 — swap in live numbers from vendor docs or [LMSYS Chatbot Arena](https://lmarena.ai) / [Artificial Analysis](https://artificialanalysis.ai) for a production-grade version.

### `user_survey.csv`
Columns: `respondent_id`, `tool_primary`, `use_case`, `satisfaction_score`, `ease_of_use`, `accuracy_rating`, `would_recommend`, `monthly_usage_hours`

A 30-respondent simulated survey across three use cases (writing, coding, research).

## 🚀 Getting Started

```bash
git clone <your-repo-url>
cd ai-tools-comparison
pip install -r requirements.txt
python src/analyze.py
```

This generates:
- `visuals/benchmark_radar.png` — radar chart of benchmark performance
- `visuals/pricing_comparison.png` — input/output cost comparison
- `visuals/context_and_speed.png` — context window + generation speed
- `visuals/satisfaction_boxplot.png` — user satisfaction distribution
- `visuals/use_case_breakdown.png` — tool preference by use case
- `reports/benchmark_pivot.csv` — tool × benchmark score table
- `reports/survey_summary.csv` — aggregated survey stats

For interactive exploration, open `notebooks/exploration.ipynb`.

## 🔑 Key Findings

| Dimension | Winner | Notes |
|---|---|---|
| Coding (SWE-bench, HumanEval) | **Claude** | Consistently leads on agentic coding benchmarks |
| Multimodal (MMMU) | **Gemini** | Strongest vision/multimodal reasoning |
| Context window | **Gemini** | 1M tokens vs 200K (Claude) vs 128K (ChatGPT) |
| Generation speed | **Gemini** | Fastest tokens/sec |
| Cheapest input cost | **Gemini** | $3.50/M tokens |
| Cheapest output cost | **ChatGPT** | $15/M tokens |
| User satisfaction (survey) | **Claude** | Highest avg. satisfaction (8.8/10), especially for coding |
| Best value use case | **ChatGPT** | Most versatile for writing + general use at low cost |

## 🛠️ Extending This Project

- Replace placeholder benchmark data with live figures scraped from vendor benchmark pages or [Artificial Analysis](https://artificialanalysis.ai)
- Connect to each provider's API to run your own head-to-head prompt evaluations
- Add statistical significance testing (t-tests) between survey groups
- Deploy `analyze.py` outputs to a dashboard (Streamlit / Plotly Dash)

## 📄 License

MIT — free to use and adapt.
