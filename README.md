# BigQuery for Agent Ops: Unified Platform Demo Collections

This repository demonstrates how to use **Google BigQuery** as a unified platform for AI Agent Observability ("Agent Ops"), Governance, Analytics, Evaluation, and Memory.

It features a comprehensive Jupyter notebook that simulates an e-commerce customer support agent, **"ShopBot"**, and showcases how to capture, analyze, and optimize its behavior using the Google Agent Development Kit (ADK) and BigQuery's built-in AI capabilities.

## 🎯 Goals

The primary goal of this demo is to show how developers can move beyond simple logging and build a production-grade observability stack for AI agents without leaving the data warehouse. Key capabilities demonstrated include:

  * **Real-time Observability:** Streaming agent traces, decisions, and tool inputs/outputs directly to BigQuery.
  * **Root Cause Analysis (RCA):** Using Gemini 2.5 Flash within BigQuery to automatically diagnose why an agent session failed.
  * **Cost Tracking:** Granular token and cost estimation per session and per user.
  * **Semantic Search:** Retrieving past similar sessions to solve current user problems using BigQuery Vector Search.
  * **Structured Memory:** Automatically extracting structured facts (user intent, outcomes) from unstructured conversation logs to build long-term agent memory.

## 📂 Repository Contents

  * `Demo_Plan_BigQuery_for_Agent_Ops_Unified_Platform_Public.ipynb`: The main demo notebook. It contains the complete end-to-end workflow, from raw telemetry ingestion to AI-powered analysis and visualization.

## 🚀 Quick Start

### Prerequisites

1.  A Google Cloud Project with billing enabled.
2.  The following APIs enabled:
      * BigQuery API
      * BigQuery Connection API
      * Vertex AI API
3.  A BigQuery Cloud Resource Connection (for calling Gemini models from SQL).

### Running the Demo

You can run this notebook in any Jupyter environment. We have provided "Open in..." links for convenience:

| Environment | Link |
| :--- | :--- |
| **Google Colab** | [Link](https://www.google.com/search?q=https://colab.research.google.com/github/haiyuan-eng-google/demo_BQ_agent_analytics_plugin_notebook/blob/main/Demo_Plan_BigQuery_for_Agent_Ops_Unified_Platform_Public.ipynb) |
| **Vertex AI Workbench** | [Link](https://www.google.com/search?q=https://console.cloud.google.com/vertex-ai/workbench/deploy-notebook%3Fdownload_url%3Dhttps://raw.githubusercontent.com/haiyuan-eng-google/demo_BQ_agent_analytics_plugin_notebook/main/Demo_Plan_BigQuery_for_Agent_Ops_Unified_Platform_Public.ipynb) |
| **BigQuery Studio** | [Link](https://www.google.com/search?q=https://console.cloud.google.com/bigquery/import%3Furl%3Dhttps://github.com/haiyuan-eng-google/demo_BQ_agent_analytics_plugin_notebook/blob/main/Demo_Plan_BigQuery_for_Agent_Ops_Unified_Platform_Public.ipynb) |

**Steps:**

1.  Open the notebook in your preferred environment.
2.  Update the `PROJECT_ID`, `DATASET_ID`, and `CONNECTION_ID` variables in the **Configuration** cell to match your Google Cloud environment.
3.  Run the cells sequentially.

## 📊 Key Features & Analysis

The notebook guides you through five distinct phases of Agent Ops:

1.  **Real-time Feed:** View raw traces of agent `LLM_RESPONSE`, `TOOL_USE`, and `USER_MESSAGE` events.
2.  **Behavior Analysis:** SQL-based analytics to visualize Tool Usage distribution and Error Rates.
3.  **Deep Dive & RCA:** Using `AI.GENERATE` to read conversation logs and explain *why* a specific session failed (e.g., distinguishing between a tool error and an LLM hallucination).
4.  **Enhancing Agent Intelligence:**
      * **Vector Search:** Finding relevant past sessions to provide context for new queries.
      * **Structured Memory:** Creating a JSON object of "facts" from a conversation to store in a user profile.
5.  **Visualization:** Native Python visualizations (using Altair) right inside BigQuery Studio to track cost and performance KPIs.

## 🛠️ Technology Stack

  * **Google BigQuery:** Data warehouse and engine for SQL analysis.
  * **BigQuery ML (BQML):** For calling remote models (Gemini, Text Embedding) directly from SQL.
  * **Google Agent Development Kit (ADK):** (Conceptual) Used for the agent instrumentation plugin.
  * **Python (Pandas, Altair):** For data manipulation and visualization.

## ⚠️ Disclaimer

This is a demonstration project and is not an officially supported Google product. The "ShopBot" agent data is simulated for demonstration purposes.
