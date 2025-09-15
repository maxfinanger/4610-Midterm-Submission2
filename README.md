# 4610-Midterm-Submission2

ACIT 4610
Mid-Term Group Portfolio/Project – 2 -2025
Multi-Objective Capacitated VRP (MOVRP) Problem Using Multi-Objective
Evolutionary Algorithms (MOEAs)
Objective: In Mid-Term Group Portfolio/Project -1, you solved the classical VRP with a single
depot, customers with known demands, vehicles starting/ending at the depot, where the only
objective is to minimize total distance. Now we extend this to a more realistic version used in
logistics: the Capacitated Vehicle Routing Problem (CVRP). You need to develop and
implement any two Multi-Objective Evolutionary Algorithms (MOEAs) from your lectures.
The project is to be carried out in the already-approved groups for the Mid-Term Group
Portfolio/Project -1. Any submission outside this accepted group list will NOT be accepted.
Submission Deadline: October 3rd (Friday) at 17:00.
Submission Channel: Canvas.
• Every group must submit Only ONE submission by any of the group members.
• The coding must be sent as a GitHub link through email (kazi.ripon@oslomet.no) by
the submission deadline. You need to ensure it is shareable and executable.
• Note that we will download the coding immediately after the submission deadline to
prevent the possibility of updating it later.
Cheating / Plagiarism: In case of any Cheating/plagiarism, it will be handled according to
OsloMet’s policy. You can find more about it at https://student.oslomet.no/en/cheating
Use of Artificial Intelligence (AI):
• For coding, you can use AI tools as defined by OsloMet’s policy.
• For the report, you are NOT allowed to use any AI tools.
• You can find the policy at: https://ansatt.oslomet.no/en/siste-nytt/-/nyhet/veiledning-
for-bruk-av-kunstig-intelligens-i-studentoppgaver

## 1 The Capacitated VRP (CVRP)

In CVRP, each vehicle has a maximum capacity Q (e.g., truck load limit in kg or pallet space),
and each customer has a demand di , where a route must not exceed the vehicle’s capacity.
Example.
• Depot in the city centre.
• Vehicle capacity Q = 10.
• Customer demands: [3, 4, 7, 2, 5].
• You cannot put customers with demands 7 + 5 in the same route (12 > 10).
• Feasible routes might be:
o Route 1: Depot → Customer 1 (3) → Customer 2 (4) → Depot. Load = 7.
Page 2 of 5
o Route 2: Depot → Customer 3 (7) → Depot. Load = 7.
o Route 3: Depot → Customer 4 (2) → Customer 5 (5) → Depot. Load = 7.
So capacity constraints force more routes than distance minimization alone would suggest.
Fig. 1: A CVRP with capacity = 10.

## 2 Multi-Objective CVRP

In practice, logistics planners don’t only care about total travel distance. They also want to
ensure fairness among routes, so no driver has an extremely long or overloaded route
compared to others. To ensure this, you need to solve the CVRPs using the following two
objectives:

1. Total Distance (minimize):
   f1 (x)= # distance(route)
   all routes
2. Route Balance (minimize):
   Two common definitions are possible (pick one and explain in your report):
   o Maximum Route Length (min–max objective):
   f2 (x)= distance(r)r
   ∈R
   max
   This objective tries to shorten the longest route.
   o Standard Deviation of Route Lengths:
   f2 (x)=$ 1
   |R| #(distance(r) - L') 2
   r
   ∈R
   Where L is the average route length. The goal of this objective is to keep all
   routes close to the same length.
   Page 3 of 5
   Example.
   Two solutions for 4 routes, distances:
   • Solution A: [20, 20, 20, 80], total = 140, max = 80.
   • Solution B: [35, 35, 35, 35]. total = 140, max = 35.
   Both have the exact total, but Solution B is more balanced and usually preferred
   in practice.
   This makes total distance vs. balance a conflicting pair of objectives:
   • Reducing total distance tends to overload one or two routes.
   • Improving balance requires spreading routes, which often increases total
   distance.
   (a) Total = 38.4; Max route = 20.5 (b) Total = 62.2; Max route = 20.4
   Fig. 2: Balanced Solution (Routes more equal, slightly longer total)
   Example with Capacity:
   • Vehicle capacity Q=10
   • Customer demands:
   o C1 = 3, C2 = 4, C3 = 2, C4 = 5, C5 = 3, C6 = 4, C7 = 6, C8 = 2
   Check feasibility:
   • In the Unbalanced solution:
   o Route 1: C1(3) + C2(4) = 7 ≤ 10 ✔
   o Route 2: C6(4) + C7(6) + C8(2) = 12 ❌ (over capacity → infeasible unless we
   repair)
   o Route 3: C3(2) + C4(5) + C5(3) = 10 ✔
   • In the Balanced solution:
   o Route 1: C1(3) + C6(4) = 7 ✔
   o Route 2: C2(4) + C7(6) = 10 ✔
   o Route 3: C3(2) + C8(2) = 4 ✔
   o Route 4: C4(5) + C5(3) = 8 ✔
   So the Balanced solution is feasible, but the Unbalanced one is slightly over capacity.

## 3 Data repository

    Use the CVRPLIB repository (http://vrp.atd-lab.inf.puc-rio.br/index.php/en/)
    It provides:
    • Customer coordinates (for distance dij ).
    • Customer demands.
    • Vehicle capacity Q.
    • Depot location.
    From this single dataset, you can compute both objectives:
    • Total distance: by summing route lengths.
    • Route balance: by measuring the longest route (or load variance).
    Recommended instances:
    • Small: A-n32-k5 (32 customers, 5 vehicles).
    • Medium: B-n78-k10 (78 customers, 10 vehicles).
    • Large: X-n101-k25 (101 customers, 25 vehicles).

## 4 Task Details

### 1 Problem Definition:

    a. Algorithms: Select any two MOEAs discussed during the lectures.
    b. Experimental Setup: Define three groups of scenarios, each with 2 instances.
    The lower limits of each group are mentioned in “Recommended instances” as
    outlined above.
    § Instances: 3 (S, M, L from CVRPLIB).
    § Runs: ≥ 20 per algorithm per instance with different seeds.
    § Budget: identical for both algorithms (e.g., pop = 100, generations =
    500, x-over prob = 0.7, mutation prob = 0.2, etc.).
    § Termination: fixed number of generations.
    § Runtime: record both wall-clock seconds and #evaluations.
    c. Objectives: You must utilize the two objectives outlined above. For the
    second objective, you may select either of the two alternatives. However, you
    need to discuss the details of your chosen second objective.

### 2 Comparison and Analysis:

    a. Multi-objective optimization has two distinct objectives: convergence and
    diversity. You must compare and analyze the solutions and also the Pareto front
    achieved by each algorithm in terms of convergence and diversity metrics, using
    our three categories of test problems.
    b. You also need to test and analyse all the test problems for three sets of MOEA
    parameters (population size, generation number, crossover probability, and
    mutation probability), ultizing the statistics from multiple runs.

## 5 Deliverables

### a. Code Implementation:

    i. Provide a GitHub repository containing all your source code. Include a clear
    README with instructions on how to install any dependencies and run the
    algorithms on the provided example data.
    ii. Include the GitHub link in the submitted report and ensure it is shareable and
    executable.
    iii. The code should preferably be written in Python (if you are not familiar with
    Python, you can use a similar language).
    iv. The code should be commented on or accompanied by notes explaining key
    parts of the MOEA implementation.
    v. The code must be in an executable state and generate the outputs.

### b. Report

    i. You should deliver your report in a PDF format through Canvas.
    ii. The project report should be between 1000-1500 words.
    iii. The report must mention the Group No as published in the Canvas.
    iv. The report should at least discuss the points below:

3. A detailed description of the complete MOEA design. Describe your
   implementation in detail so that others can replicate your work. This
   includes the individual representation, implementation of all
   corresponding genetic and MOEA operators.
4. Define and explain the objective function.
5. Comparison and analysis of your achieved results (plots + tables) as
   mentioned in the above (Comparison and Analysis section)
6. A table summarizing the required time to find the solution for all the
   test problems with your defined three sets of parameters.
7. What are your findings, analysis, and conclusions about the correlation
   of the parameters based on the achieved results?
8. Describe the effects of these parameter values during the early and later
   stages of the evolutionary cycle.
