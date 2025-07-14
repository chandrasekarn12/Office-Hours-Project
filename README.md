Office Hours Queue Optimization

Predicting and reducing student wait times during CMSC 216 office hours by modeling arrival and service processes with Poisson/exponential distributions and Monte‑Carlo simulation in R.

Table of Contents

Problem Statement

Methodology

Key Findings

Quick Start

Reproducing the Analysis

Project Structure

Contributing

License

Problem Statement

CMSC 216 students at the University of Maryland routinely queue for multiple hours before a teaching assistant (TA) is available, especially near project deadlines. The objective of this project is to quantitatively model the office‑hours queue and recommend staffing strategies that shrink average wait time for everyone.

Methodology

Data Collection – Queue length and active‑TA counts were captured from Quuly over three days surrounding a major project deadline.

Stochastic Modeling – Student arrivals and service completions are represented as independent Poisson processes. Inter‑arrival/service times are therefore exponentially distributed.

Parameter Estimation – Empirical observations yield approximate average service time (≈ 37.5 min) and arrival time (≈ 32.8 min) for a single TA.

Monte‑Carlo Experiments – Simulations explore:

the impact of 1–3 TAs working a full day,

the number of TAs required to keep the queue from growing under “busy‑day” arrival rates,

how to distribute a fixed pool of TAs across morning/afternoon/evening shifts.

Detailed code and exposition live in FinalProject.Rmd, with a rendered, interactive report in FinalProject.html.

Key Findings

Scenario

Average Wait ↓

TAs Required

Baseline

—

1

Maintain steady state (average day)

2× faster

2

Prevent growth (busy day)

5× faster

5

Clear 10‑student backlog in ≤ 1 h

8–12× faster

8‑12

Allocating 6 TAs in a 1 / 3 / 2 split across morning, afternoon, and evening minimizes overall overflow while respecting single‑shift limits.

Quick Start

# clone the repo
$ git clone https://github.com/chandrasekarn12/Office-Hours-Project.git
$ cd Office-Hours-Project

Open FinalProject.html in your browser to read the full report without installing R.

Reproducing the Analysis

Install R ≥ 4.0 (RStudio recommended).

No external packages are required – the notebook relies only on base‑R functions.

Knit the notebook:

rmarkdown::render("FinalProject.Rmd")

This regenerates FinalProject.html with all figures and simulations.

Project Structure

Office-Hours-Project/
├── FinalProject.Rmd   # Source notebook (code + narrative)
├── FinalProject.html  # Rendered report for quick viewing
└── README.md          # You are here

Contributing

Pull requests are welcome! For major changes, please open an issue first to discuss what you would like to change.

License

This project is released under the MIT License (see LICENSE).

Acknowledgements

Queue data courtesy of the CMSC 216 teaching team and Quuly.

Project completed as part of STAT 498J – Summer 2025 at the University of Maryland.

