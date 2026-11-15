# ED Nurse Staffing Optimization Engine

## Overview
The goal of this project is to develop an optimization engine that can evaluate the 120 possible roster variations for nurses working in a large emergency department in Auckland. By identifying the Pareto frontier of efficient solutions, it lays the foundations for a decision agent to be developed to recommend the most optimal staffing levels.

## Business Problem
Health New Zealand | Te Whatu Ora have a target of 95% of ED patients to leave the ED within 6 hours. In the March 2026 quarter, only 74.4% did, while hospitals face a shortage of around 2,000 registered nurses. As adding more nurses to the team will increase patient flow but also cost more money, ED managers have to make a decision on how many core and floating nurses they want to roster per shift.

## Status
✅ Complete - Part 1: Optimization Engine (Unit 11)
🚧 In progress — Part 2: Decision Agent

## Technologies
- Python
- Pandas
- NumPy
- Matplotlib
- Jupyter Notebook

## Part 1: Optimization Engine (Complete ✓)

### What It Does
This optimization engine takes 120 different scenarios of core (18-29) and float nurses (0-9) per shift, to find the Pareto frontier (efficient solutions) of weekly nurse budget remaining (NZD) vs % of patients leaving ED in 6 hours.

### Key Findings
- 33.3% of solutions are Pareto optimal (40 Pareto optimal scenarios out of 120)

- 80 dominated solutions were found which we should avoid (e.g. 20 core: 0 float is dominated by 18 core: 1 float on both objectives)

- Key strategic points were identified including: Budget Priority (18 core: 0 float, 55.1%), Weighted 60/40 (19 core: 3 float, 72.7%), Equity (20 core: 4 float, 78.7%), Balanced (26 core: 1 float, 81.3%) and 6-Hour Target Priority (29 core: 9 float, 91.9%, but $52,638 over budget)

- No scenarios were identified within the $380,000 weekly nurse budget limit to hit Health NZ’s 95% target. The best result was 88.9%.

### Running the Analysis
1. Ensure you have the required packages: `pandas`, `numpy`, `matplotlib`
2. Open `optimization_engine.ipynb`
3. Run all cells in order
4. Outputs will be saved to the `images/` folder

### Next Steps
Part 2 will add a constraint-aware decision agent that selects among these
Pareto optimal solutions based on business constraints and priorities.