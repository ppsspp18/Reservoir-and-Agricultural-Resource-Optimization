# Crop Planning Optimization using Linear Programming

This project applies **Linear Programming (LP)** to optimize the allocation of agricultural resources for multiple crops over a 12-month period. It aims to maximize profit while considering constraints such as water availability, pesticide use, land area, storage capacity, and balanced food production.

## 📌 Features

- Optimizes crop selection and land allocation for 25 crops across 12 months.
- Considers:
  - Water requirements (including industrial use)
  - Pesticide usage (limited to 0.1g/m²)
  - Storage constraints (min, max, and initial reservoir levels)
  - Area constraints
  - Balanced food category outputs (e.g., cereals, vegetables, spices)

## 🛠 Technologies Used

- **Python 3**
- **PuLP** – Linear programming modeling package
- **NumPy** – Numerical computation
- **Matplotlib** - Graphical visualization

## 📁 Project Structure

- `lp_code.ipynb` – Jupyter Notebook containing:
  - Data preprocessing
  - Problem formulation (objective function + constraints)
  - LP model construction using PuLP
  - Solution output
  - Graphs of area allocation, rainfall, crop allocation and storage of each month 

## 🚀 How to Run

1. Install dependencies:
   ```bash
   pip install pulp numpy
   ```

2. Open the notebook:
   ```bash
   jupyter notebook Untitled2.ipynb
   ```

3. Run all cells to:
   - Define data and constraints
   - Build and solve the optimization model
   - Review results: selected crops, area allocation, and expected profit

## 📊 Constraints Modeled

- **Water**: Satisfies monthly and cumulative usage bounds.
- **Pesticide**: Constrained to 0.1 gram per square meter.
- **Area**: Total land cannot exceed 1.826 billion m².
- **Food Category Balance**: Ensures diversity across categories like cereals, vegetables, and spices.

## 📈 Objective

> **Maximize total profit** from crop production while respecting all agricultural and environmental constraints.

## ✍️ Author

*Your Name Here*  
*Affiliation or Contact (Optional)*
## 🧾 Results Summary

### ✅ Optimization Status
- **Status:** Optimal
- **Total Profit:** ₹51,336,563,730.35
- **Profit per Acre:** ₹113,750.13
- **Fertilizer Used:** 107,129,637.31 grams (out of 182,600,000 grams)
- **Fertilizer Usage per Acre:** 237.37 g/acre

### 🌾 Optimal Crop Allocation (Area in m²)
- Wheat: 644,853.92
- Maize: 6,655,146.10
- Groundnut: 1,095,000.00
- Tur (Rabi): 1,825,000.00
- Brinjal (Summer): 10,220,000.00
- Onion (Rabi): 2,555,000.00
- Spinach (Summer): 2,555,000.00
- Ginger: 685,292.52
- All other crops: 0.00

### 💧 Water Storage Levels (in m³)
Reservoir storage increased during months of expected drought:
- **Low Point:** Aug 23 – 100,000,000 
- **Peak Storage:** Jan 24 – 3,140,000,000
This indicates smart reservoir management to handle drought periods by stockpiling water in advance.

### 💡 Shadow Prices (Dual Values)
Shadow prices represent the change in objective function (profit) per unit increase in constraint bounds.

- **Active Area Constraints:**
  - Aug 23: ₹39.12/m²
  - Oct 23: ₹15.68/m²
  - Nov 23: ₹39.12/m²
- **Food Category Balance Constraints:**
  - Cereals: ₹-9594.77
  - Pulses: ₹-27166.43
  - Nuts: ₹-17990.66
  - Vegetables (varied limits): Up to ₹1582.00
  - Slack variables show tight limits especially for vegetable categories, indicating these are bottlenecks in further profit optimization.

---
