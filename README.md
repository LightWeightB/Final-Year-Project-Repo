# Final-Year-Project-Repo
🏠 Home Energy Management System (HEMS) – PV-Battery Optimisation

This repository contains the MATLAB implementation of a Home Energy Management System (HEMS) for a residential PV–Battery Energy Storage System (BESS) using Mixed-Integer Linear Programming (MILP).

The project focuses on optimal energy scheduling and economic battery sizing for UK residential households.

📌 What This Project Does
Optimises energy flow between:
PV generation
Battery storage
Household load
Grid import
Minimises:
Electricity cost
Grid dependency
Determines:
Optimal battery size (kWh)
Cost savings vs no battery system
⚙️ Files in This Repository
🔹 FinalMILPCode.mlx

Main implementation file:

MILP formulation using intlinprog
Battery scheduling (charge/discharge)
Capacity sweep (1–10 kWh)
Economic optimisation
KPI outputs
Plots (cost, energy, import)
🔹 AveragingScriptOneSet.mlx
Processes a single dataset
Converts raw data into half-hourly format (48 points/day)
🔹 AveragingScriptThirtySets.mlx
Processes multiple datasets (CREST-style)
Generates averaged load and PV profiles
Used for creating representative daily profiles
🔹 README.md

Project documentation (this file)

🧠 Method Overview

The system is formulated as a Mixed-Integer Linear Programming (MILP) problem:

Objective

Minimise total daily cost:

Cost=∑(Pimp⋅cimp⋅Δt)+Battery Cost+PV Cost
Key Constraints
Power balance
PV energy allocation (load, battery, curtailment)
Battery state of charge (SoC) dynamics
Charge/discharge limits
Binary operation modes
SoC-dependent limits
PV-only charging (no grid charging)
Cyclic SoC
📊 Outputs
Energy KPIs
Total household load (kWh/day)
PV generation (kWh/day)
Grid import (kWh/day)
PV → Load
PV → Battery
PV curtailment
Battery discharge
Economic Results
Daily cost (£/day)
Yearly cost (£/year)
Savings vs baseline
% reduction
Optimal battery size
Plots
Cost vs battery size
Load vs PV vs grid import
🚀 How to Run
Open MATLAB

Prepare your data in:

HalfHourly.Load48
HalfHourly.PV48

Run:

FinalMILPCode.mlx
📌 Assumptions
Perfect knowledge of load and PV (no forecasting)
No grid export (only curtailment)
PV-only battery charging
Constant electricity price
No battery degradation modelling
🎯 Key Outcome

The model identifies the economic optimum battery size, balancing:

Reduced electricity import
Battery capital cost
👤 Author

Abdullah Albu Arish
BEng Electrical & Electronic Engineering
University of Manchester
