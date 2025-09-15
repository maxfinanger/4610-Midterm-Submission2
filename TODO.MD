# Project TODO List

## 2️⃣ Programming Tasks

### 2.1 NSGA-II Implementation

- [ ] Implement NSGA-II algorithm
  - [ ] Define individual representation
  - [ ] Implement selection operator
  - [ ] Implement crossover operator
  - [ ] Implement mutation operator
  - [ ] Implement non-dominated sorting
  - [ ] Implement crowding distance calculation
- [ ] Test NSGA-II on:
  - [ ] Small dataset
  - [ ] Medium dataset
  - [ ] Large dataset
- [ ] Collect results:
  - [ ] Objective function values
  - [ ] Runtime for each dataset
  - [ ] Convergence plots

### 2.2 SPEA2 Implementation

- [ ] Implement SPEA2 algorithm
  - [ ] Define individual representation
  - [ ] Implement selection operator
  - [ ] Implement crossover operator
  - [ ] Implement mutation operator
  - [ ] Implement fitness assignment
  - [ ] Implement density estimation
  - [ ] Implement archive management
- [ ] Test SPEA2 on:
  - [ ] Small dataset
  - [ ] Medium dataset
  - [ ] Large dataset
- [ ] Collect results:
  - [ ] Objective function values
  - [ ] Runtime for each dataset
  - [ ] Convergence plots

### 2.3 Comparison & Analysis

- [ ] Compare NSGA-II vs SPEA2 results
  - [ ] Convergence speed
  - [ ] Solution diversity
  - [ ] Runtime efficiency
- [ ] Create tables and plots summarizing comparisons
- [ ] Analyze parameter effects:
  - [ ] Early-stage evolution
  - [ ] Later-stage evolution

---

## 3️⃣ Report (PDF)

- [ ] Deliver report in **PDF format** through Canvas
- [ ] Report length: **1000–1500 words**
- [ ] Include **Group No** as published in Canvas

### 3.1 MOEA Design

- [ ] Describe overall design of NSGA-II and SPEA2
- [ ] Explain **individual representation**
- [ ] Describe **genetic operators** used
  - [ ] Selection
  - [ ] Crossover
  - [ ] Mutation
- [ ] Describe **MOEA-specific operators**
  - [ ] NSGA-II: Non-dominated sorting, crowding distance
  - [ ] SPEA2: Fitness assignment, density estimation, archive management
- [ ] Include **implementation notes** for reproducibility

### 3.2 Objective Function

- [ ] Define the **objective function(s)** clearly
- [ ] Explain reasoning behind chosen function(s)
- [ ] Mention constraints (if any)

### 3.3 Results & Comparison

- [ ] Insert **plots** for small, medium, large datasets
- [ ] Insert **tables** of objective values
- [ ] Include **runtime tables** for all datasets and parameter sets
- [ ] Compare NSGA-II vs SPEA2 results
  - [ ] Highlight differences in convergence
  - [ ] Discuss differences in spread/diversity of solutions
- [ ] Analyze effects of parameter values
  - [ ] Early-stage evolution
  - [ ] Later-stage evolution
- [ ] Discuss correlations between parameters and results

### 3.4 Analysis & Conclusions

- [ ] Summarize key findings
- [ ] State which algorithm performed better under which conditions
- [ ] Discuss trade-offs (runtime vs solution quality)
- [ ] Highlight limitations of current implementation
- [ ] Suggest possible improvements or future work
