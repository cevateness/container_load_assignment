
# Container Load Assignment Problem

This repository contains the code and data for solving the Container Load Assignment Problem, which focuses on optimally assigning loads to containers of varying capacities with no shape or 3d constraints. The main goal is to minimize the number of containers used.

## Project Overview

This project addresses the container load assignment problem where various products with specific volumes need to be placed into containers with defined capacities. The aim is to develop an optimal assignment strategy that minimizes the number of containers used. The problem is complex due to non-linear constraints and combinatorial structures, falling into the category of NP-hard problems like the "Knapsack Problem" and the "Bin Packing Problem".

### Mathematical Model

**Decision Variables:**
- $x_{ij}$: Binary variable indicating if product $i$ is placed in container $j$.
- $y_j$: Binary variable indicating if container $j$ is used.

**Objective Function:**
```math
 \text{Minimize } Z = \sum_j y_j
```

**Constraints:**
1. Each product must be placed in exactly one container:
   ```math
   \sum_j x_{ij} = 1 \quad \forall i 
   ```
3. Container capacity constraints:
   ```math
    \sum_i v_i x_{ij} \leq C_j y_j \quad \forall j
   ```
5. Binary constraints:
   ```math
    y_j \in \{0, 1\} \quad \forall j \quad | \quad
   x_{ij} \in \{0, 1\} \quad \forall i, j 
   ```


The chosen method for this project is Agglomerative Clustering due to its effectiveness in clustering problems and its computational efficiency.

## Solution Methodology

A hierarchical clustering (agglomerative clustering) approach is employed iteratively:
1. **Initialization**: Each product starts as its own cluster.
2. **Distance Matrix Calculation**: Compute initial distances between product pairs based on container capacities.
3. **Cluster Merging**: Iteratively merge the closest clusters until no more clusters can be merged without exceeding container capacities.
4. **Distance Matrix Update**: Update the distance matrix after each merge.

## Conclusion

The heuristic approach developed using hierarchical clustering was found to be effective for the container load assignment problem. Future work can explore adding new constraints or improving the distance matrix computation methods to enhance solution quality further.

