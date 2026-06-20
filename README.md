# 🤖 RAG Pipeline Performance & Token Cost Simulator

An interactive, strategic product management dashboard designed to model and balance retrieval accuracy (recall), end-to-end user latency, and token consumption costs across modern enterprise Large Language Models (LLMs).

### 🔗 Live Link: [Launch the Interactive Simulator Here](https://YOUR_GITHUB_USERNAME.github.io/rag-token-cost-optimizer/)

## 🌟 Core PM Competencies Demonstrated

* **AI System Design & Trade-Offs:** Understands and simulates the relationship between data chunking sizes, overlap, retrieval metrics (Top-$K$), database indexing, and downstream context window impact.
* **Token Unit Economics & Modeling:** Projects precise API costs by tracking token consumption patterns for advanced model APIs (like Gemini 3, GPT-5, and Claude 4.5/4.6 series).
* **Technical Infrastructure Strategy:** Models the financial and latency differences of running vector databases on local edge embeddings (Chroma) vs. managed cloud serverless or dedicated enterprise clusters.
* **Executive Decision Briefs:** Translates complex system variables into direct, clear, and actionable planning recommendations for engineering, finance, and product stakeholders.


## ⚙️ Mathematical & Economic Foundations

This optimizer runs continuous modeling using verified real-world pricing and architectural trends:

1. **Retrieval Recall Accuracy Approximation:** Modeled using an exponential convergence curve relative to the total tokens retrieved (Chunk Size $\times$ Top-$K$), penalized by lower chunk overlaps:
   $$\mathrm{Accuracy} \approx 1 - e^{-0.0007 \times (\mathrm{Chunk\ Size} \times K)} \times (1 - \mathrm{Overlap} \times 0.15)$$

2. **End-to-End Latency Sizing:** Compounds vector database search latency with the LLM's Time to First Token (TTFT) and token generation speed:
   $$\mathrm{Latency} = \mathrm{TTFT}_{\mathrm{Model}} + \mathrm{Search}_{\mathrm{DB}} + \frac{\mathrm{Output\ Tokens}}{\mathrm{Tokens\ Per\ Second}_{\mathrm{Model}}}$$

3. **Context-Aware Tiered Pricing:** Dynamic billing checks context lengths on input payloads (especially Claude 4.5/4.6 Sonnet and Opus models) to scale prices under/over the $200\mathrm{K}$ token threshold.

4. **API Token Cost Formula:**
   $$\mathrm{Cost}_{\mathrm{Query}} = (\mathrm{Input\ Tokens} \times \mathrm{Price}_{\mathrm{Input}}) + (\mathrm{Output\ Tokens} \times \mathrm{Price}_{\mathrm{Output}})$$


## 🚀 Technical Architecture

* **Responsive SVG Chart:** Dynamic rendering of the Pareto Efficiency Frontier, plotting where current pipeline configurations sit on the cost-to-accuracy spectrum.
* **Tailwind CSS UI:** Clean layout, built with professional color systems, responsive grids, and visual depth.
* **Interactive Tooltips:** Accessible, built-in definitions next to all parameters to guide non-technical users.
* **Markdown Memo Export:** Fully automated strategic executive memo compiler, allowing one-click copying of planning decisions directly to PRDs or Notion sheets.
