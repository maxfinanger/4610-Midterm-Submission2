# Multi-Objective Optimization Project TODO

## 1️⃣ Programming Tasks

### NSGA-II Implementation

- [ ] Implement NSGA-II algorithm:
  - [ ] Initialize population
  - [ ] Evaluate objective functions
  - [ ] Non-dominated sorting
  - [ ] Crowding distance calculation
  - [ ] Selection, crossover, and mutation
  - [ ] Replacement for next generation
- [ ] Test NSGA-II on a small dataset
- [ ] Validate Pareto front generation

### SPEA2 Implementation

- [ ] Implement SPEA2 algorithm:
  - [ ] Initialize population and external archive
  - [ ] Evaluate objective functions
  - [ ] Fitness assignment based on strength values
  - [ ] Density estimation and environmental selection
  - [ ] Selection, crossover, and mutation
- [ ] Test SPEA2 on a small dataset
- [ ] Validate Pareto front generation

### Experiment Setup

- [ ] Define performance metrics:
  - [ ] Hypervolume
  - [ ] Generational Distance
  - [ ] Spread / Spacing
  - [ ] Number of Pareto-optimal solutions
- [ ] Decide parameter settings for algorithms:
  - [ ] Population size
  - [ ] Number of generations
  - [ ] Crossover rate
  - [ ] Mutation rate
- [ ] Create reproducible experiment scripts

### Running Experiments

- [ ] Run NSGA-II on all test problems
- [ ] Run SPEA2 on all test problems
- [ ] Record results for each metric
- [ ] Save execution time for all parameter sets

### Analysis & Visualization

- [ ] Plot Pareto fronts for visual comparison
- [ ] Compare performance metrics for NSGA-II vs SPEA2
- [ ] Analyze convergence and diversity differences
- [ ] Summarize key findings from experiments

---

## 2️⃣ Report Tasks (PDF, 1000–1500 words)

- [ ] Include Group No as published in Canvas
- [ ] **MOEA Design Description**
  - [ ] Detailed explanation of the complete MOEA design
  - [ ] Individual representation
  - [ ] Implementation of all genetic and MOEA operators
- [ ] **Objective Function**
  - [ ] Define and explain the objective function(s)
- [ ] **Comparison & Analysis**
  - [ ] Present results with plots and tables
  - [ ] Compare NSGA-II and SPEA2 performance
- [ ] **Execution Time Table**
  - [ ] Summarize time to find solutions for all test problems with three parameter sets
- [ ] **Findings & Conclusions**
  - [ ] Discuss correlation of parameters with achieved results
  - [ ] Explain effects of parameter values during early and later evolutionary stages
