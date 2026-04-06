# 🌉 BridgeRock AI Migration Factory

**BridgeRock AI Migration Factory** is a provider-agnostic LLM migration and evaluation platform. It enables organizations to seamlessly transition between AI models (e.g., OpenAI → NVIDIA Llama) with real-time comparison, cost analysis, and performance evaluation.

The platform automates the entire migration pipeline through a structured lifecycle:
**Analyze** → **Translate** → **Execute** → **Compare** → **Evaluate** → **Report**

---

## 🎯 The Problem
Organizations face significant friction when attempting to switch or diversify their AI model usage:
* **Vendor Lock-in:** Hard-coded dependencies on specific APIs.
* **Migration Effort:** High manual overhead to rewrite prompts and logic.
* **Blind Transitions:** Unclear performance differences between models.
* **Shadow Costs:** Lack of granular cost visibility and comparison tools.

## 💡 The Solution
BridgeRock provides an end-to-end **migration intelligence system** that:
* **Analyzes** prompts for complexity and intent.
* **Dynamically selects** optimal target models.
* **Executes** across multiple providers in parallel.
* **Compares** outputs using semantic and quality metrics.
* **Generates** actionable migration insights and risk assessments.

---

## ⚙️ Key Features

### 🧠 Intelligent Model Selection
* Analyzes prompt type, complexity, and token counts.
* Dynamically maps requests to the most suitable target model.

### 🔄 Multi-Provider Execution
* Supports **OpenAI** and **NVIDIA (Llama models)**.
* Uses parallel execution to provide side-by-side comparisons in real-time.

### 📊 Evaluation Engine
* **Semantic Scoring:** Measures how closely the target output matches the source.
* **LLM-based Quality Eval:** Uses "LLM-as-a-judge" for nuanced quality checks.
* **Performance Tracking:** Monitors latency and token consumption.

### 🧾 Migration Decision System
Provides a clear traffic-light verdict for every migration test:
* ✅ **SAFE TO MIGRATE**
* ⚠️ **PROCEED WITH CAUTION**
* ❌ **DO NOT MIGRATE**

### 💰 Cost & Risk Analytics
* Detailed cost-per-model breakdown.
* Estimated monthly savings and cost-performance tradeoffs.
* Risk engine flags latency spikes and model-specific weaknesses.

---

## 🏗️ Architecture & Tech Stack

### High-Level Flow
1.  **Frontend (React):** User interface for prompt input and result visualization.
2.  **FastAPI Backend:** Orchestration layer managing the data flow.
3.  **Core Pipeline:**
    * **Analyze Layer:** Understanding the request.
    * **Translation Layer:** Prompt adaptation.
    * **Execution Layer:** Multi-provider API handling.
    * **Evaluation Engine:** Scoring and decision logic.
    * **Storage Layer:** Handling results via Mock or Cloud storage.

### Project Structure
```text
backend/
├── app/
│   ├── api/                # API routes
│   ├── core/               # Configuration
│   ├── integrations/       # OpenAI, NVIDIA clients
│   ├── services/
│   │   ├── translation/    # Prompt analysis
│   │   ├── execution/      # Orchestrator
│   │   ├── evaluation/     # Scoring engine
│   │   └── storage/        # DB / mock storage
frontend/
├── components/             # Reusable UI elements
├── pages/                  # Main views
└── API layer               # Frontend service calls
```

---

## 🚀 Getting Started

1.  **Clone the Repo**
    ```bash
    git clone <repo-url>
    cd project
    ```
2.  **Install Backend Dependencies**
    ```bash
    pip install -r requirements.txt
    ```
3.  **Setup Environment Variables (`.env`)**
    ```env
    OPENAI_API_KEY=your_key
    NVIDIA_API_KEY=your_key
    AWS_STORAGE_ENABLED=false
    ```
4.  **Run Backend**
    ```bash
    uvicorn app.main:app --reload
    ```
5.  **Run Frontend**
    ```bash
    npm install
    npm start
    ```

---

## 📊 Data Examples

### Example Input
```json
{
  "messages": [
    {
      "role": "user",
      "content": "Explain artificial intelligence"
    }
  ]
}
```

### Example Output
| Metric | Value |
| :--- | :--- |
| **Verdict** | ✅ SAFE TO MIGRATE |
| **Confidence** | 87% |
| **Latency** | 1.2s (Source) vs 0.9s (Target) |
| **Cost Savings** | ~35% Reduction |

---

## 🔮 Future Roadmap
* **Semantic Caching:** Reuse previous results to slash costs and latency.
* **Advanced Metrics:** Deeper evaluation for specific use cases (code, creative, logic).
* **Auto-Recommendation Engine:** Suggesting the best model based on historical performance.
* **Full DB Integration:** Native support for MongoDB and DynamoDB.

---

> **Final Statement:** BridgeRock transforms AI usage from simple execution into a **decision intelligence system**, helping organizations optimize cost, performance, and reliability across the evolving LLM landscape.
