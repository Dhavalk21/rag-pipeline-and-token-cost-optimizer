🤖 RAG Pipeline Performance & Token Cost Simulator

An interactive, strategic product management dashboard designed to model and balance retrieval accuracy (recall), end-to-end user latency, and token consumption costs across modern enterprise Large Language Models (LLMs).

🔗 Live Link: Launch the Interactive Simulator Here

🎨 How it Works (System Architecture)

    graph TD

    %% Define Nodes
    RawData[Raw Knowledge Base <br> PDF, Wikis, Docs] -->|1. Slicing & Chunking| Chunking[Text Chunks <br> Sized with Overlap]
    Chunking -->|Vectorization| VectorDB[(Vector Database <br> Pinecone, Milvus, Postgres)]
    
    UserQuery[User Input Query <br> Question Asked] -->|2. Semantic Search Query| VectorDB
    VectorDB -->|3. Context Retrieval| RetrievedChunks[Top-K Matching Chunks <br> High-Relevance Context]
    
    UserQuery -->|Assemble Context| LLMInput[Prompt Template <br> User Question + Snippets]
    RetrievedChunks -->|Assemble Context| LLMInput
    
    LLMInput -->|4. Inference Call| LLM[Frontier LLM <br> Claude, Gemini, GPT-5]
    LLM -->|5. Output Generation| FinalResponse[Accurate, Grounded Answer]

    %% Color Styling
    style RawData fill:#f8fafc,stroke:#94a3b8,stroke-width:2px,color:#0f172a
    style Chunking fill:#f1f5f9,stroke:#64748b,stroke-width:2px,color:#0f172a
    style VectorDB fill:#e0e7ff,stroke:#4f46e5,stroke-width:2px,color:#312e81
    style RetrievedChunks fill:#e0f2fe,stroke:#0284c7,stroke-width:2px,color:#0369a1
    style LLMInput fill:#fae8ff,stroke:#c084fc,stroke-width:2px,color:#6b21a8
    style LLM fill:#dcfce7,stroke:#10b981,stroke-width:2px,color:#14532d
    style FinalResponse fill:#fef9c3,stroke:#eab308,stroke-width:2px,color:#713f12


📋 Three Steps of RAG Sizing:

Slicing & Chunking: Long text resources are diced into structured, overlapping text segments (Chunks). This preserves key sentence context so that ideas aren't cut in half.

Search & Retrieve: When a query arrives, the system searches the Vector DB for the best matches (Top-K). These snippets are bundled alongside the original query.

The Balance Trade-Off: The LLM uses these snippets to answer the question without hallucinating. Larger models and bigger contexts yield excellent answers but increase cost and take longer to respond.

🌟 Core PM Competencies Demonstrated

AI System Design & Trade-Offs: Understands and simulates the relationship between data chunking sizes, overlap, retrieval metrics (Top-$K$), database indexing, and downstream context window impact.

Token Unit Economics & Modeling: Projects precise API costs by tracking token consumption patterns for advanced model APIs (like Gemini 3, GPT-5, and Claude 4.5/4.6 series).

Technical Infrastructure Strategy: Models the financial and latency differences of running vector databases on local edge embeddings (Chroma) vs. managed cloud serverless or dedicated enterprise clusters.

Executive Decision Briefs: Translates complex system variables into direct, clear, and actionable planning recommendations for engineering, finance, and product stakeholders.

⚙️ Mathematical & Economic Foundations

This optimizer runs continuous modeling using verified real-world pricing and architectural trends:

Retrieval Recall Accuracy Approximation: Modeled using an exponential convergence curve relative to the total tokens retrieved (Chunk Size $\times$ Top-$K$), penalized by lower chunk overlaps:


$$\mathrm{Accuracy} \approx 1 - e^{-0.0007 \times (\mathrm{Chunk\ Size} \times K)} \times (1 - \mathrm{Overlap} \times 0.15)$$

End-to-End Latency Sizing: Compounds vector database search latency with the LLM's Time to First Token (TTFT) and token generation speed:


$$\mathrm{Latency} = \mathrm{TTFT}_{\mathrm{Model}} + \mathrm{Search}_{\mathrm{DB}} + \frac{\mathrm{Output\ Tokens}}{\mathrm{Tokens\ Per\ Second}_{\mathrm{Model}}}$$

Context-Aware Tiered Pricing: Dynamic billing checks context lengths on input payloads (especially Claude 4.5/4.6 Sonnet and Opus models) to scale prices under/over the $200\mathrm{K}$ token threshold.

API Token Cost Formula:


$$\mathrm{Cost}_{\mathrm{Query}} = (\mathrm{Input\ Tokens} \times \mathrm{Price}_{\mathrm{Input}}) + (\mathrm{Output\ Tokens} \times \mathrm{Price}_{\mathrm{Output}})$$

🚀 Technical Architecture

Responsive SVG Chart: Dynamic rendering of the Pareto Efficiency Frontier, plotting where current pipeline configurations sit on the cost-to-accuracy spectrum.

Tailwind CSS UI: Clean layout, built with professional color systems, responsive grids, and visual depth.

Interactive Tooltips: Accessible, built-in definitions next to all parameters to guide non-technical users.

Markdown Memo Export: Fully automated strategic executive memo compiler, allowing one-click copying of planning decisions directly to PRDs or Notion sheets.


GitHub: Check out my GitHub Portfolio

© 2026 Dhaval Kareliya. All rights reserved.
