# 📊 Office-Hours Queue Optimization

> **Reducing student wait times in CMSC 216 office hours with stochastic modeling & Monte-Carlo simulation.**

---

## 📑 Table of Contents
1. [Problem Statement](#problem-statement)  
2. [Methodology](#methodology)  
3. [Key Findings](#key-findings)  
4. [Quick Start](#quick-start)  
5. [Reproducing the Analysis](#reproducing-the-analysis)  
6. [Project Structure](#project-structure)  
7. [Contributing](#contributing)  
8. [License](#license)  

---

## Problem Statement
Students in **CMSC 216** (Introduction to Computer Systems) at the University of Maryland often wait **hours** for help during office hours—especially near project deadlines.  
This project *quantitatively* models the queue and explores staffing strategies that shrink the average wait for everyone.

## Methodology

| Stage | Description |
|-------|-------------|
| **1. Data Collection** | Scraped queue length & active-TA counts from *Quuly* across three busy days |
| **2. Stochastic Modeling** | Modeled student arrivals & service completions as independent Poisson processes (⇒ exponential inter-arrival/service times) |
| **3. Parameter Estimation** | Estimated mean service time ≈ **37.5 min** per TA and mean arrival interval ≈ **32.8 min** |
| **4. Monte-Carlo Simulation** | Explored how varying TA counts & shift splits affects wait time and backlog clearance |

The full R notebook lives in [`FinalProject.Rmd`](./FinalProject.Rmd) and renders to [`FinalProject.html`](./FinalProject.html).

## Key Findings

| Scenario | Avg. Wait ↓ | TAs Needed |
|----------|-------------|------------|
| Baseline (1 TA) | — | 1 |
| Steady State (average day) | **2× faster** | 2 |
| No Growth (busy day) | **5× faster** | 5 |
| Clear 10-student backlog ≤ 1 h | **8–12× faster** | 8–12 |

> **Optimal staffing:** 6 TAs split **1 / 3 / 2** across morning, afternoon, and evening minimizes overflow under our assumptions.

## Quick Start

```bash
# Clone the repo
git clone https://github.com/chandrasekarn12/Office-Hours-Project.git
cd Office-Hours-Project

# View the report (no R needed!)
open FinalProject.html   # macOS
# OR double-click FinalProject.html in any file explorer
