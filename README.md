# Overview

This project applies Linear Programming (LP) to a transportation optimization problem using the lpSolve and lpSolveAPI packages. The scenario involves allocating production from three plants to four warehouses (including a dummy warehouse to absorb surplus capacity).

- Objective (Primal): Minimize the total cost of production and shipping while meeting warehouse demand and plant capacity constraints.

- Objective (Dual): Maximize total shadow prices (economic values of the demand constraints) to assess resource bottlenecks.

Approach:

- Formulated both primal and dual problems explicitly.

- Solved using R’s lp.transport() and lp() functions.

- Compared optimal cost, shipment plan, and dual variable interpretations.

# Findings

Optimal transportation cost: 88,250 (minimum total cost).

Shipment plan:

- Plant A: 10 units → Warehouse 1, 90 units → Warehouse 2

- Plant B: 55 units → Warehouse 1, 70 units → Warehouse 3

- Plant C: 15 units → Warehouse 1, 135 units → Dummy Warehouse (surplus)

All supply and demand constraints satisfied.

Shadow prices (Dual values):

- Warehouse 2 has a shadow price of 315, indicating it is the critical bottleneck — each additional unit of demand at Warehouse 2 increases total cost by 315.

- Warehouses 1, 3, and Dummy have shadow prices of 0, meaning increasing their demand does not affect total cost.

Economic Interpretation:

- The system efficiently utilizes available supply while meeting all demands.

- Capacity at Warehouse 2 is the binding constraint, driving marginal cost changes.
