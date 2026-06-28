<div align="center">

<img width="100%" alt="banner" src="https://capsule-render.vercel.app/api?type=waving&color=0:6366F1,50:8B5CF6,100:EC4899&height=220&section=header&text=Cash%20Flow%20Predictor&fontSize=48&fontColor=ffffff&animation=fadeIn&fontAlignY=38&desc=Know%20your%20money%20before%20it%20moves&descAlignY=58&descSize=20" />

<br>

**AI-powered forecasting · Spending intelligence · Savings recommendations**

<p>
  <img src="https://img.shields.io/badge/status-active-2DD4BF?style=for-the-badge&labelColor=0F172A" />
  <img src="https://img.shields.io/badge/made%20with-Python%20%2B%20React-6366F1?style=for-the-badge&labelColor=0F172A" />
  <img src="https://img.shields.io/badge/forecasting-Prophet-F472B6?style=for-the-badge&labelColor=0F172A" />
  <img src="https://img.shields.io/badge/license-Team%20Project-FBBF24?style=for-the-badge&labelColor=0F172A" />
</p>

<br>

</div>

> Banking apps show what already happened. This project shows what's **about to happen** — and why.

<div align="left">

## 🔗 Quick Navigation

<div align="left">

**🎯 The Why**
- [Project Overview](#-project-overview)
- [Problem Statement](#-problem-statement)
- [Why It Matters](#-why-it-matters)

**🚀 The What**
- [Features](#-features)
- [Demo Walkthrough](#-demo-walkthrough)
- [Architecture](#️-architecture)

**🧠 The How**
- [Technology Stack](#️-technology-stack)
- [AI Components](#-ai-components)
- [Model Performance](#-model-performance--metrics)

</div>
  
<div align="left">

- [Challenges Faced](#-challenges-faced)
- [What We Learned](#-what-we-learned)
- [Future Enhancements](#-future-enhancements)

</div>

<br>

---

<br>

## 🎯 Project Overview

Most people can't answer one simple question:

<div align="center">

### 💭 *"Will I have enough money next month?"*

</div>

<br>

Banking apps show what already happened. Spreadsheets are manual and quickly go stale. Nothing connects past transactions to a forward-looking view of cash flow — **until now.**

> **Personal Cash Flow Predictor** closes that gap. Upload a bank statement, and the system automatically classifies every transaction, builds a 90-day balance forecast, and surfaces plain-language insights and savings opportunities — turning financial anxiety into financial confidence.

<br>

## 🧩 Problem Statement

```mermaid
flowchart LR
    A["💸 <b>No Warning</b><br/>Low-balance surprises<br/>before next paycheck"] --> D{{"😟 Financial<br/>Anxiety &<br/>Uncertainty"}}
    B["🌀 <b>No Visibility</b><br/>Recurring expenses &<br/>habits go unnoticed"] --> D
    C["⏪ <b>Reactive, Not Proactive</b><br/>Decisions made after<br/>the money is gone"] --> D

    classDef problem fill:#312E81,stroke:#818CF8,stroke-width:2px,color:#EEF2FF,rx:10,ry:10
    classDef result fill:#9D174D,stroke:#F472B6,stroke-width:2px,color:#FCE7F3,rx:10,ry:10
    class A,B,C problem
    class D result
```

<div align="center">

| | Pain Point | Description |
|:---:|:---|:---|
| 💸 | **Low-balance surprises** | Unexpected shortfalls arrive before the next paycheck, with no warning. |
| 🌀 | **No visibility into patterns** | Recurring expenses and spending habits go unnoticed month after month. |
| ⏪ | **Reactive, not proactive** | Decisions get made after the money is already gone, not before. |

</div>

<br>

## ✨ Why It Matters

> Financial stress is rarely about income alone — it's about **uncertainty**. A forward-looking view turns financial anxiety into financial confidence.

<table>
<tr>
<td width="33%" align="center" valign="top">

### ⏱️
**Act before it's too late**

Forecasting low balances days in advance gives people time to adjust spending, not just react after an overdraft.

</td>
<td width="33%" align="center" valign="top">

### 🧮
**Save without the spreadsheet**

Automated pattern detection finds savings opportunities people would never spot manually.

</td>
<td width="33%" align="center" valign="top">

### 🌍
**Built for real life**

Supports multiple currencies and real bank statement formats, not just toy demo data.

</td>
</tr>
</table>

<br>

## 🚀 Features

```mermaid
mindmap
  root(("💰 Cash Flow<br/>Predictor"))
    ("📂 Multi-format Upload")
      CSV / Excel / PDF
      Instant validation
    ("🏷️ Auto-Classification")
      Incoming / Outgoing
      11 expense categories
    ("📊 Real-time Dashboard")
      KPI cards
      Inflow vs outflow charts
    ("📄 Pagination")
      Large datasets
      Fast navigation
    ("🔮 90-Day Forecasting")
      Confidence bands
      90 day horizons
    ("🎛️ What-If Simulation")
      Live sliders
      Income / expense modeling
    ("🔔 Alerts & Recommendations")
      Low-balance warnings
      AI savings tips
    ("🌍 Multi-currency")
      INR / USD / EUR
      Live conversion
```

<table>
<tr>
<td width="50%" valign="top">

#### 📂 Multi-format upload
Drag-and-drop CSV, Excel, or PDF bank statements, with instant column validation.

#### 🏷️ Automatic transaction classification
Every transaction tagged Incoming/Outgoing and sorted into 11 expense categories.

#### 📊 Real-time dashboard
KPI cards, inflow vs. outflow charts, and category breakdowns.

#### 📄 Pagination support
Large transaction datasets split into manageable pages for faster, smoother browsing.

</td>
<td width="50%" valign="top">

#### 🔮 90-day forecasting
Balance projections with confidence bands, supporting 30/90-day horizons.

#### 🎛️ What-if simulation
Sliders to model income changes, expense cuts, or one-time purchases live.

#### 🔔 Alerts & Recommendations
Automatic low-balance warnings and AI-generated savings recommendations.

#### 🌍 Multi-currency support
INR, USD, and EUR with live conversion.

</td>
</tr>
</table>

<br>

## 🎬 Demo Walkthrough

<div align="center">

*The product flows through six stages, from raw statement to actionable insight.*

</div>

```mermaid
flowchart LR
    A["📂<br/><b>Upload</b><br/>CSV / Excel / PDF"] --> B["🏷️<br/><b>Auto-Classify</b><br/>+ 11 categories"]
    B --> C["📊<br/><b>Dashboard</b><br/>KPIs & charts"]
    C --> D["🔮<br/><b>Forecast</b><br/>90-day projection"]
    D --> E["🎛️<br/><b>What-If</b><br/>Live simulation"]
    E --> F["🔔<br/><b>Alerts</b><br/>& Recommendations"]

    classDef step1 fill:#1E3A8A,stroke:#60A5FA,stroke-width:2px,color:#EFF6FF,rx:10,ry:10
    classDef step2 fill:#065F46,stroke:#34D399,stroke-width:2px,color:#ECFDF5,rx:10,ry:10
    classDef step3 fill:#92400E,stroke:#FBBF24,stroke-width:2px,color:#FFFBEB,rx:10,ry:10
    classDef step4 fill:#9D174D,stroke:#F472B6,stroke-width:2px,color:#FDF2F8,rx:10,ry:10
    class A,B step1
    class C,D step2
    class E step3
    class F step4
```

<div align="center">

| Stage | What Happens |
|:---:|:---|
| 1️⃣ | **Upload** — Drag-and-drop a CSV, Excel, or PDF bank statement; columns are validated instantly. |
| 2️⃣ | **Auto-Classify** — Every transaction is tagged Incoming/Outgoing and sorted into 11 expense categories. |
| 3️⃣ | **Dashboard** — KPI cards, inflow vs. outflow charts, and a category breakdown update in real time. |
| 4️⃣ | **Forecast** — A 90-day forecast with confidence bands shows where the balance is headed. |
| 5️⃣ | **What-If** — Sliders simulate income changes, expense cuts, or one-time purchases live. |
| 6️⃣ | **Alerts & Recommendations** — Low-balance warnings and AI savings recommendations surface automatically. |

</div>

<br>

## 🏗️ Architecture

The system is organized as a clean pipeline: every transaction is classified (incoming/outgoing + category) automatically on upload, so forecasting and recommendations always work off clean, structured data.

```mermaid
flowchart TB
    FE["🖥️ <b>Frontend</b><br/>Lovable.dev · React + Tailwind"]
    API["⚙️ <b>API Layer</b><br/>FastAPI (Python)"]

    subgraph AGENTS[" "]
        direction LR
        TA["🧮 <b>Transaction Analytical Agent</b><br/>OpenAI<br/><br/>Performs transaction analysis,<br/>classification & category tagging"]
        FC["🔮 <b>Forecasting Agent</b><br/>Prophet / time-series forecasting<br/><br/>Generates cash flow forecasts<br/>and confidence intervals"]
        RA["🧠 <b>Recommendation &<br/>Insight Agent</b><br/>OpenAI APIs<br/><br/>Generates insights, explanations<br/>and savings recommendations"]
    end

    DB["🗄️ <b>PostgreSQL</b><br/>Transaction and user data<br/><br/>Persistent storage for transactions,<br/>forecasts, insights & preferences"]

    FE --> API
    API --> TA
    API --> FC
    API --> RA
    TA --> DB
    FC --> DB
    RA --> DB

    classDef frontend fill:#1E3A8A,stroke:#60A5FA,stroke-width:2px,color:#EFF6FF,rx:10,ry:10
    classDef api fill:#065F46,stroke:#34D399,stroke-width:2px,color:#ECFDF5,rx:10,ry:10
    classDef agentA fill:#9A3412,stroke:#FB923C,stroke-width:2px,color:#FFF7ED,rx:10,ry:10
    classDef agentB fill:#5B21B6,stroke:#A78BFA,stroke-width:2px,color:#F5F3FF,rx:10,ry:10
    classDef agentC fill:#9D174D,stroke:#F472B6,stroke-width:2px,color:#FDF2F8,rx:10,ry:10
    classDef store fill:#065F46,stroke:#34D399,stroke-width:2px,color:#ECFDF5,rx:10,ry:10
    class FE frontend
    class API api
    class TA agentA
    class FC agentB
    class RA agentC
    class DB store
    style AGENTS fill:none,stroke:none
```

> **Design principle:** Classify every transaction (incoming/outgoing + category) automatically on upload, so downstream forecasting and recommendations always operate on clean, structured data.

<table>
<tr>
<td width="50%" valign="top">

**🧠 Multi-Agent Architecture**

The system follows a multi-agent architecture where specialized agents handle transaction classification, forecasting, insight generation, and recommendation tasks independently while collaborating through the API layer.

</td>
<td width="50%" valign="top">

**📐 SDD (Spec-Driven Development)**

Requirements, workflows, and system behavior are defined through detailed specifications before implementation, improving consistency, scalability, and development efficiency.

</td>
</tr>
</table>

<br>

### 🧬 C4 Diagrams

<div align="center">

*The architecture is documented at four levels of zoom — system context, containers, components, and code — following the C4 model.*

</div>

**Level 1 — System Context**

```mermaid
flowchart LR
    User(["👤 <b>User</b><br/><i>Personal finance management</i>"])
    Cash["🖥️ <b>Cash Flow Predictor</b><br/>&lt;&lt;Software System&gt;&gt;<br/><i>AI-powered financial<br/>forecasting platform</i>"]
    OpenAI[/"🤖 <b>OpenAI API</b><br/>&lt;&lt;External System&gt;&gt;"/]
    Bank[/"🏦 <b>Bank Statements</b><br/>&lt;&lt;External: PDF files&gt;&gt;"/]

    User -- "Uploads, views" --> Cash
    Cash -- "LLM calls" --> OpenAI
    Cash -- "Parses PDFs" --> Bank

    classDef person fill:#1E3A8A,stroke:#60A5FA,stroke-width:2px,color:#EFF6FF,rx:12,ry:12
    classDef system fill:#2563EB,stroke:#93C5FD,stroke-width:2px,color:#EFF6FF,rx:12,ry:12
    classDef external fill:#475569,stroke:#94A3B8,stroke-width:2px,color:#F1F5F9,rx:8,ry:8

    class User person
    class Cash system
    class OpenAI,Bank external

    linkStyle default stroke:#94A3B8,stroke-width:1.5px
```

**Level 2 — Containers**

```mermaid
flowchart LR
    subgraph BOUNDARY["Cash Flow Predictor [System Boundary]"]
        direction LR

        React["⚛️ <b>React App</b><br/>&lt;&lt;Container: SPA&gt;&gt;<br/><br/><i>Dashboard, charts,<br/>chat, simulations</i>"]
        FastAPI["⚙️ <b>FastAPI Backend</b><br/>&lt;&lt;Container: Python API&gt;&gt;<br/><br/><i>REST endpoints,<br/>auth, routing</i>"]

        subgraph DOWNSTREAM[" "]
            direction TB
            AIService["🧠 <b>AI Insight Service</b><br/>&lt;&lt;Container: Python&gt;&gt;<br/><br/><i>OpenAI calls </i>"]
            Forecast["🔮 <b>Forecast Engine</b><br/>&lt;&lt;Container: Python&gt;&gt;<br/><br/><i>Prophet <br/>time-series models</i>"]
        end

        Postgres[("🗄️ <b>PostgreSQL</b><br/>&lt;&lt;Container: DB&gt;&gt;<br/><br/><i>Transactions, users,<br/>forecasts, alerts</i>")]

        React -- "REST/JSON" --> FastAPI
        FastAPI -- "calls" --> AIService
        FastAPI -- "triggers" --> Forecast
        Forecast -- "reads/writes" --> Postgres
        AIService -. "reads/writes" .-> Postgres
    end

    classDef container fill:#2563EB,stroke:#93C5FD,stroke-width:2px,color:#EFF6FF,rx:10,ry:10
    classDef db fill:#0E7490,stroke:#67E8F9,stroke-width:2px,color:#ECFEFF,rx:10,ry:10

    class React,FastAPI,AIService,Forecast container
    class Postgres db
    style BOUNDARY fill:none,stroke:#64748B,stroke-width:1.5px,stroke-dasharray:6 4
    style DOWNSTREAM fill:none,stroke:none
    linkStyle default stroke:#94A3B8,stroke-width:1.5px
```

**Level 3 — Components (FastAPI Backend)**

```mermaid
flowchart LR
    subgraph BOUNDARY["FastAPI Backend [Container Boundary]"]
        direction LR
        Auth["🔐 <b>Auth</b><br/><i>JWT, OAuth validation</i>"]
        Parser["📄 <b>Statement Parser</b><br/><i>PDF → transactions</i>"]
        Processor["🏷️ <b>Transaction Processor</b><br/><i>Categorize, dedupe</i>"]

        subgraph DOWNSTREAM[" "]
            direction TB
            Orchestrator["🔮 <b>Forecast Orchestrator</b><br/><i>Calls forecast engine</i>"]
            Alert["🔔 <b>Alert Service</b><br/><i>Low-balance alerts</i>"]
            Simulation["🎛️ <b>Simulation Service</b><br/><i>What-if scenarios</i>"]
            Gateway["🤖 <b>AI Gateway</b><br/><i>LLM proxy</i>"]
        end

        Auth --> Parser
        Parser --> Processor
        Processor -.-> Orchestrator
        Processor -.-> Alert
        Processor -.-> Simulation
        Processor -.-> Gateway
    end

    classDef auth fill:#92400E,stroke:#FBBF24,stroke-width:2px,color:#FFFBEB,rx:10,ry:10
    classDef parser fill:#065F46,stroke:#34D399,stroke-width:2px,color:#ECFDF5,rx:10,ry:10
    classDef processor fill:#065F46,stroke:#34D399,stroke-width:2px,color:#ECFDF5,rx:10,ry:10
    classDef orchestrator fill:#1E3A8A,stroke:#60A5FA,stroke-width:2px,color:#EFF6FF,rx:10,ry:10
    classDef alert fill:#9D174D,stroke:#F472B6,stroke-width:2px,color:#FDF2F8,rx:10,ry:10
    classDef simulation fill:#92400E,stroke:#FBBF24,stroke-width:2px,color:#FFFBEB,rx:10,ry:10
    classDef gateway fill:#5B21B6,stroke:#A78BFA,stroke-width:2px,color:#F5F3FF,rx:10,ry:10

    class Auth auth
    class Parser parser
    class Processor processor
    class Orchestrator orchestrator
    class Alert alert
    class Simulation simulation
    class Gateway gateway
    style BOUNDARY fill:none,stroke:#64748B,stroke-width:1.5px,stroke-dasharray:6 4
    style DOWNSTREAM fill:none,stroke:none
    linkStyle default stroke:#94A3B8,stroke-width:1.5px
```

**Level 4 — Code (ForecastOrchestrator)**

```mermaid
classDiagram
    class ForecastOrchestrator {
        -DBRepository db_repo
        -ProphetModel model
        -AlertEngine alert_engine
        -AIGateway ai_gateway
        +build_forecast(user_id, days)
        +get_confidence_interval()
        +check_low_balance(threshold)
        +generate_summary()
        +simulate_scenario(delta)
        +export_forecast_chart()
    }

    class DBRepository {
        +get_transactions()
        +save_forecast()
    }

    class ProphetModel {
        +fit(series)
        +predict()
    }

    class AlertEngine {
        +check_threshold()
        +send_alert()
    }

    class AIGateway {
        +generate_insight()
    }

    ForecastOrchestrator ..> DBRepository
    ForecastOrchestrator ..> ProphetModel
    ForecastOrchestrator ..> AlertEngine
    ForecastOrchestrator ..> AIGateway
```

<br>

## 🛠️ Technology Stack

<div align="center">

<table>
<tr><th align="left">Layer</th><th align="left">Technology</th></tr>
<tr><td>🎨 <b>Frontend</b></td><td>
<img src="https://img.shields.io/badge/Lovable.dev-0F172A?style=flat-square" />
<img src="https://img.shields.io/badge/React-0F172A?style=flat-square&logo=react&logoColor=61DAFB" />
<img src="https://img.shields.io/badge/Tailwind_CSS-0F172A?style=flat-square&logo=tailwindcss&logoColor=38BDF8" />
<img src="https://img.shields.io/badge/shadcn%2Fui-0F172A?style=flat-square" />
</td></tr>
<tr><td>⚙️ <b>Backend</b></td><td>
<img src="https://img.shields.io/badge/Python-0F172A?style=flat-square&logo=python&logoColor=3776AB" />
<img src="https://img.shields.io/badge/FastAPI-0F172A?style=flat-square&logo=fastapi&logoColor=05998b" />
</td></tr>
<tr><td>🗄️ <b>Database</b></td><td>
<img src="https://img.shields.io/badge/PostgreSQL-0F172A?style=flat-square&logo=postgresql&logoColor=4169E1" />
</td></tr>
<tr><td>📄 <b>Document Processing</b></td><td>
<img src="https://img.shields.io/badge/PDFPlumber-0F172A?style=flat-square" />
</td></tr>
<tr><td>🔮 <b>Forecasting</b></td><td>
<img src="https://img.shields.io/badge/Prophet-0F172A?style=flat-square" />
</td></tr>
<tr><td>🤖 <b>AI</b></td><td>
<img src="https://img.shields.io/badge/OpenAI_API-0F172A?style=flat-square&logo=openai&logoColor=ffffff" />
</td></tr>
<tr><td>🧪 <b>API Testing</b></td><td>
<img src="https://img.shields.io/badge/Postman-0F172A?style=flat-square&logo=postman&logoColor=FF6C37" />
</td></tr>
<tr><td>🚦 <b>Server</b></td><td>
<img src="https://img.shields.io/badge/Uvicorn-0F172A?style=flat-square" />
</td></tr>
<tr><td>✅ <b>Testing</b></td><td>
<img src="https://img.shields.io/badge/Playwright-0F172A?style=flat-square&logo=playwright&logoColor=2EAD33" />
</td></tr>
<tr><td>☁️ <b>Deployment</b></td><td>
<img src="https://img.shields.io/badge/Render-0F172A?style=flat-square&logo=render&logoColor=46E3B7" />
</td></tr>
</table>

</div>

<br>

## 🤖 AI Components

<table>
<tr>
<td width="50%" valign="top">

#### 🔮 Forecasting Engine
Uses Prophet time-series models to project account balances 30 or 90 days into the future, with confidence bands that widen further out and narrow as new transactions arrive.

#### 💬 AI Insight Service
Uses OpenAI APIs to generate plain-language explanations of forecasts and personalized savings recommendations, so users understand *why* a forecast looks the way it does, not just the number itself.

</td>
<td width="50%" valign="top">

#### 🏷️ Transaction Classification
Automatically extracts and classifies every transaction into one of 11 expense categories on upload, forming the structured data foundation that forecasting and AI insights are built on.

#### 🎛️ Scenario Simulator
Uses natural-language inputs to evaluate "what-if" financial scenarios, generating an updated cash flow forecast, 90-day impact analysis, risk assessment, and actionable recommendations.

</td>
</tr>
</table>

<br>

## 📊 Model Performance & Metrics


> Model performance is evaluated using forecast accuracy, classification quality, prediction confidence intervals, and validation against historical transaction data.


<div align="center">

| Metric | What It Measures | Our Model Performance |
|:---|:---|:---|
| 📏 **Mean Absolute Error (MAE)** | Average magnitude of forecast errors, in the same units as the balance itself | 5.0% of average balance |
| 📐 **Root Mean Squared Error (RMSE)** | Penalizes larger forecast misses more heavily than small ones | 7.0% of average balance |
| 🧮 **Mean Squared Error (MSE)** | Squared error term used internally for model tuning and comparison | 0.0049 |
| ⚖️ **Mean Absolute Scaled Error (MASE)** | Compares forecast error against a naive baseline, making accuracy comparable across users with different spending scales | 0.82 |

Illustrative placeholder values — pending real evaluation results.

</div>


<br>

## 🧗 Challenges Faced

```mermaid
flowchart TB
    A["🧾 <b>Messy real-world statements</b><br/><br/>Inconsistent columns,<br/>merged fields, and<br/>OCR-prone PDF layouts"]
    B["🔁 <b>Recurring expense detection</b><br/><br/>Rent, SIP and subscriptions<br/>vs. coincidental<br/>similar amounts"]
    C["📉 <b>Forecast uncertainty</b><br/><br/>Short transaction history<br/>leads to noisy<br/>early forecasts"]
    D["🌐 <b>Multi-currency consistency</b><br/><br/>INR / USD / EUR across<br/>every KPI<br/>and chart"]

    A1["✅ <b>Robust parsing layer</b>"]
    B1["✅ <b>Careful rule design</b>"]
    C1["✅ <b>Wide, clear confidence<br/>intervals</b>"]
    D1["✅ <b>Careful state<br/>management</b>"]

    A --> A1
    B --> B1
    C --> C1
    D --> D1

    A1 ~~~ B1
    B1 ~~~ C1
    C1 ~~~ D1

    classDef challenge fill:#9A3412,stroke:#FB923C,stroke-width:2px,color:#FFF7ED,rx:10,ry:10
    classDef resolution fill:#065F46,stroke:#34D399,stroke-width:2px,color:#ECFDF5,rx:10,ry:10
    class A,B,C,D challenge
    class A1,B1,C1,D1 resolution
```

<div align="center">

| Challenge | How It Was Tackled |
|:---|:---|
| 🧾 **Messy real-world statements** | Bank PDFs vary wildly in layout; parsing had to handle inconsistent columns, merged fields, and OCR-prone formats. |
| 🔁 **Recurring expense detection** | Distinguishing genuine recurring charges (rent, SIP, subscriptions) from coincidentally similar amounts needed careful rule design. |
| 📉 **Forecast uncertainty** | Short transaction histories early on made early forecasts noisy; confidence intervals had to be wide and clearly communicated. |
| 🌐 **Multi-currency consistency** | Keeping every KPI, chart, and recommendation in sync across INR, USD, and EUR without mixed symbols took careful state management. |

</div>

<br>

## 💡 What We Learned

```mermaid
flowchart LR
    subgraph L[" "]
        direction TB
        A["🧹 <b>Clean data beats</b><br/><b>clever models</b>"]
        B["🤝 <b>Explainability</b><br/><b>builds trust</b>"]
        C["🌍 <b>Design for real</b><br/><b>currencies, not demos</b>"]
    end

    A --> A1["Robust parsing & classification<br/>outperformed model tuning"]
    B --> B1["A reason beside the number<br/>makes users trust the forecast"]
    C --> C1["Multi-currency from day one<br/>avoided a costly retrofit"]

    classDef takeaway fill:#1E1B4B,stroke:#A5B4FC,stroke-width:2px,color:#EEF2FF,rx:10,ry:10
    classDef insight fill:#082F49,stroke:#38BDF8,stroke-width:2px,color:#F0F9FF,rx:10,ry:10
    class A,B,C takeaway
    class A1,B1,C1 insight
    style L fill:none,stroke:none
```

<table>
<tr>
<td width="33%" align="center" valign="top">

### 🧹
**Clean data beats clever models**

Time spent on robust parsing and classification paid off more than tuning the forecasting model itself.

</td>
<td width="33%" align="center" valign="top">

### 🤝
**Explainability builds trust**

Users trust a forecast more when it comes with a plain-language reason, not just a number.

</td>
<td width="33%" align="center" valign="top">

### 🌍
**Design for real currencies, not demos**

Building multi-currency support from day one avoided a costly retrofit later.

</td>
</tr>
</table>

<br>

## 🔮 Future Enhancements

<table>
<tr>
<td width="50%" valign="top">

#### 💬 Conversational financial assistant
Let users ask questions in plain English and get grounded answers from their own data.

#### 🚨 Anomaly detection
Flag unusual transactions automatically, beyond simple low-balance alerts.

#### 🏦 Multi-account support
Aggregate checking, savings, and credit accounts into one unified forecast.

</td>
<td width="50%" valign="top">

#### 🎯 Goal-based savings plans
Let users set a target (e.g. a trip or down payment) and get a tailored plan to reach it.

#### 📉 Subscription optimization
Surface underused subscriptions and suggest cancellations automatically.

</td>
</tr>
</table>

<br>

---

<div align="center">

<img width="100%" alt="footer" src="https://capsule-render.vercel.app/api?type=waving&color=0:EC4899,50:8B5CF6,100:6366F1&height=120&section=footer" />

**Personal Cash Flow Predictor** · Team Project

🌟 *Built to turn financial anxiety into financial confidence* 🌟

</div>
