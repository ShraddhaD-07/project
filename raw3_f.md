<div align="center">

# 💰 Personal Cash Flow Predictor

### Know your money before it moves.

**AI-powered forecasting, spending intelligence & savings recommendations**

[![Status](https://img.shields.io/badge/status-active-2DD4BF?style=for-the-badge&labelColor=1E293B)](#)
[![Made With](https://img.shields.io/badge/made%20with-Python%20%2B%20React-6366F1?style=for-the-badge&labelColor=1E293B)](#)
[![Forecasting](https://img.shields.io/badge/forecasting-Prophet%20%2F%20ARIMA-F472B6?style=for-the-badge&labelColor=1E293B)](#)
[![License](https://img.shields.io/badge/license-Team%20Project-FBBF24?style=for-the-badge&labelColor=1E293B)](#)

</div>

<br>

> [!NOTE]
> Banking apps show what already happened. This project shows what's *about* to happen — and why.

---

## 📑 Table of Contents

<table>
<tr>
<td width="50%" valign="top">

- [🎯 Project Overview](#-project-overview)
- [🧩 Problem Statement](#-problem-statement)
- [✨ Why It Matters](#-why-it-matters)
- [🚀 Features](#-features)
- [🎬 Demo Walkthrough](#-demo-walkthrough)
- [🏗️ Architecture](#️-architecture)

</td>
<td width="50%" valign="top">

- [🛠️ Technology Stack](#️-technology-stack)
- [🤖 AI Components](#-ai-components)
- [📊 Model Performance & Metrics](#-model-performance--metrics)
- [🧗 Challenges Faced](#-challenges-faced)
- [💡 What We Learned](#-what-we-learned)
- [🔮 Future Enhancements](#-future-enhancements)

</td>
</tr>
</table>

---

## 🎯 Project Overview

Most people can't answer a simple question:

> [!IMPORTANT]
> **"Will I have enough money next month?"**

Banking apps show what already happened. Spreadsheets are manual and quickly go stale. Nothing connects past transactions to a forward-looking view of cash flow.

**Personal Cash Flow Predictor** closes that gap. Upload a bank statement, and the system automatically classifies every transaction, builds a 90-day balance forecast, and surfaces plain-language insights and savings opportunities — turning financial anxiety into financial confidence.

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

| | Pain Point | Description |
|---|---|---|
| 💸 | **Low-balance surprises** | Unexpected shortfalls arrive before the next paycheck, with no warning. |
| 🌀 | **No visibility into patterns** | Recurring expenses and spending habits go unnoticed month after month. |
| ⏪ | **Reactive, not proactive** | Decisions get made after the money is already gone, not before. |

<br>

## ✨ Why It Matters

> [!TIP]
> Financial stress is rarely about income alone — it's about **uncertainty**. A forward-looking view turns financial anxiety into financial confidence.

| 🔑 Principle | Description |
|:---|:---|
| ⏱️ **Act before it's too late** | Forecasting low balances days in advance gives people time to adjust spending, not just react after an overdraft. |
| 🧮 **Save without the spreadsheet** | Automated pattern detection finds savings opportunities people would never spot manually. |
| 🌍 **Built for real life** | Supports multiple currencies and real bank statement formats, not just toy demo data. |

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
      30 / 90 day horizons
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
<td width="50%">

**📂 Multi-format upload**
Drag-and-drop CSV, Excel, or PDF bank statements, with instant column validation

**🏷️ Automatic transaction classification**
Every transaction tagged Incoming/Outgoing and sorted into 11 expense categories

**📊 Real-time dashboard**
KPI cards, inflow vs. outflow charts, and category breakdowns

**📄 Pagination support**
Large transaction datasets split into manageable pages for faster, smoother browsing

</td>
<td width="50%">

**🔮 90-day forecasting**
Balance projections with confidence bands, supporting 30/90-day horizons

**🎛️ What-if simulation**
Sliders to model income changes, expense cuts, or one-time purchases live

**🔔 Alerts & Recommendations**
Automatic low-balance warnings and AI-generated savings recommendations

**🌍 Multi-currency support**
INR, USD, and EUR with live conversion

</td>
</tr>
</table>

<br>

## 🎬 Demo Walkthrough

The product flows through six stages, from raw statement to actionable insight:

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

| Stage | What Happens |
|:---:|---|
| 1️⃣ | **Upload** — Drag-and-drop a CSV, Excel, or PDF bank statement; columns are validated instantly. |
| 2️⃣ | **Auto-Classify** — Every transaction is tagged Incoming/Outgoing and sorted into 11 expense categories. |
| 3️⃣ | **Dashboard** — KPI cards, inflow vs. outflow charts, and a category breakdown update in real time. |
| 4️⃣ | **Forecast** — A 90-day forecast with confidence bands shows where the balance is headed. |
| 5️⃣ | **What-If** — Sliders simulate income changes, expense cuts, or one-time purchases live. |
| 6️⃣ | **Alerts & Recommendations** — Low-balance warnings and AI savings recommendations surface automatically. |

<br>

## 🏗️ Architecture

The system is organized as a clean pipeline: every transaction is classified (incoming/outgoing + category) automatically on upload, so forecasting and recommendations always work off clean, structured data.

<div align="center">
<img width="1448" height="1086" alt="architecture" src="https://github.com/user-attachments/assets/9508d29b-eb62-42d1-b720-c5f1819e44e4" />
</div>

> [!NOTE]
> **Design principle:** Classify every transaction (incoming/outgoing + category) automatically on upload, so downstream forecasting and recommendations always operate on clean, structured data.

- 🧠 **Multi-Agent Architecture** — The system follows a multi-agent architecture where specialized agents handle transaction classification, forecasting, insight generation, and recommendation tasks independently while collaborating through the API layer.
- 📐 **SDD (Spec-Driven Development)** — Requirements, workflows, and system behavior are defined through detailed specifications before implementation, improving consistency, scalability, and development efficiency.

<br>

## 🛠️ Technology Stack

<div align="center">

| Layer | Technology |
|:---|:---|
| 🎨 **Frontend** | ![Lovable](https://img.shields.io/badge/Lovable.dev-1E293B?style=flat-square) ![React](https://img.shields.io/badge/React-1E293B?style=flat-square&logo=react&logoColor=61DAFB) ![Tailwind](https://img.shields.io/badge/Tailwind_CSS-1E293B?style=flat-square&logo=tailwindcss&logoColor=38BDF8) ![shadcn](https://img.shields.io/badge/shadcn%2Fui-1E293B?style=flat-square) |
| ⚙️ **Backend** | ![Python](https://img.shields.io/badge/Python-1E293B?style=flat-square&logo=python&logoColor=3776AB) ![FastAPI](https://img.shields.io/badge/FastAPI-1E293B?style=flat-square&logo=fastapi&logoColor=05998b) |
| 🗄️ **Database** | ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-1E293B?style=flat-square&logo=postgresql&logoColor=4169E1) |
| 📄 **Document Processing** | ![PDFPlumber](https://img.shields.io/badge/PDFPlumber-1E293B?style=flat-square) |
| 🔮 **Forecasting** | ![Prophet](https://img.shields.io/badge/Prophet-1E293B?style=flat-square) |
| 🤖 **AI** | ![OpenAI](https://img.shields.io/badge/OpenAI_API-1E293B?style=flat-square&logo=openai&logoColor=ffffff) |
| 🧪 **API Testing** | ![Postman](https://img.shields.io/badge/Postman-1E293B?style=flat-square&logo=postman&logoColor=FF6C37) |
| 🚦 **Server** | ![Uvicorn](https://img.shields.io/badge/Uvicorn-1E293B?style=flat-square) |
| ✅ **Testing** | ![Playwright](https://img.shields.io/badge/Playwright-1E293B?style=flat-square&logo=playwright&logoColor=2EAD33) |
| ☁️ **Deployment** | ![Render](https://img.shields.io/badge/Render-1E293B?style=flat-square&logo=render&logoColor=46E3B7) |

</div>

<br>

## 🤖 AI Components

- 🔮 **Forecasting Engine** — Uses Prophet / ARIMA time-series models to project account balances 30 or 90 days into the future, with confidence bands that widen further out and narrow as new transactions arrive.
- 💬 **AI Insight Service** — Uses OpenAI APIs to generate plain-language explanations of forecasts and personalized savings recommendations, so users understand *why* a forecast looks the way it does, not just the number itself.
- 🏷️ **Transaction Classification** — Automatically extracts and classifies every transaction into one of 11 expense categories on upload, forming the structured data foundation that forecasting and AI insights are built on.
- 🎛️ **Scenario Simulator** — Uses natural-language inputs to evaluate "what-if" financial scenarios, generating an updated cash flow forecast, 90-day impact analysis, risk assessment, and actionable recommendations.

<br>

## 📊 Model Performance & Metrics

> [!NOTE]
> Model performance is evaluated using forecast accuracy, classification quality, prediction confidence intervals, and validation against historical transaction data.

Forecast accuracy is benchmarked using the following error metrics:

| Metric | What It Measures |
|:---|:---|
| 📏 **Mean Absolute Error (MAE)** | Average magnitude of forecast errors, in the same units as the balance itself |
| 📐 **Root Mean Squared Error (RMSE)** | Penalizes larger forecast misses more heavily than small ones |
| 🧮 **Mean Squared Error (MSE)** | Squared error term used internally for model tuning and comparison |
| ⚖️ **Mean Absolute Scaled Error (MASE)** | Compares forecast error against a naive baseline, making accuracy comparable across users with different spending scales |

> [!TIP]
> **Evaluation approach:** Forecast accuracy is validated by comparing predicted vs. actual balances on held-out historical weeks; classification accuracy is checked against manually labeled sample transactions. The confidence band on the 90-day forecast widens further into the future and narrows as new transactions arrive.

<br>

## 🧗 Challenges Faced

```mermaid
flowchart TD
    A["🧾 <b>Messy Real-World</b><br/><b>Statements</b><br/><sub>Inconsistent columns, merged<br/>fields, OCR-prone PDFs</sub>"] -.-> A1["✅ Robust parsing layer"]
    B["🔁 <b>Recurring Expense</b><br/><b>Detection</b><br/><sub>Rent, SIP & subscriptions vs.<br/>coincidental similar amounts</sub>"] -.-> B1["✅ Careful rule design"]
    C["📉 <b>Forecast</b><br/><b>Uncertainty</b><br/><sub>Short transaction history =<br/>noisy early forecasts</sub>"] -.-> C1["✅ Wide, clear confidence intervals"]
    D["🌐 <b>Multi-currency</b><br/><b>Consistency</b><br/><sub>INR / USD / EUR across<br/>every KPI & chart</sub>"] -.-> D1["✅ Careful state management"]

    classDef challenge fill:#7C2D12,stroke:#FB923C,stroke-width:2px,color:#FFF7ED,rx:10,ry:10
    classDef solution fill:#14532D,stroke:#4ADE80,stroke-width:2px,color:#F0FDF4,rx:10,ry:10
    class A,B,C,D challenge
    class A1,B1,C1,D1 solution
```

| Challenge | How It Was Tackled |
|:---|:---|
| 🧾 **Messy real-world statements** | Bank PDFs vary wildly in layout; parsing had to handle inconsistent columns, merged fields, and OCR-prone formats. |
| 🔁 **Recurring expense detection** | Distinguishing genuine recurring charges (rent, SIP, subscriptions) from coincidentally similar amounts needed careful rule design. |
| 📉 **Forecast uncertainty** | Short transaction histories early on made early forecasts noisy; confidence intervals had to be wide and clearly communicated. |
| 🌐 **Multi-currency consistency** | Keeping every KPI, chart, and recommendation in sync across INR, USD, and EUR without mixed symbols took careful state management. |

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

- 🧹 **Clean data beats clever models** — Time spent on robust parsing and classification paid off more than tuning the forecasting model itself.
- 🤝 **Explainability builds trust** — Users trust a forecast more when it comes with a plain-language reason, not just a number.
- 🌍 **Design for real currencies, not demos** — Building multi-currency support from day one avoided a costly retrofit later.

<br>

## 🔮 Future Enhancements

<table>
<tr>
<td width="50%">

**💬 Conversational financial assistant**
Let users ask questions in plain English and get grounded answers from their own data.

**🚨 Anomaly detection**
Flag unusual transactions automatically, beyond simple low-balance alerts.

**🏦 Multi-account support**
Aggregate checking, savings, and credit accounts into one unified forecast.

</td>
<td width="50%">

**🎯 Goal-based savings plans**
Let users set a target (e.g. a trip or down payment) and get a tailored plan to reach it.

**📉 Subscription optimization**
Surface underused subscriptions and suggest cancellations automatically.

</td>
</tr>
</table>

---

<div align="center">

**Personal Cash Flow Predictor** — Team Project

🌟 *Built to turn financial anxiety into financial confidence* 🌟

</div>
