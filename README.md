# FantasyPL_Team_Prediction

# ⚽ Fantasy Premier League Optimizer (PuLP)

This project uses **linear programming (PuLP)** to select an optimal Fantasy Premier League (FPL) squad.

---

## 🚀 Features
- Selects a squad of 15 players.
- Picks 11 starters maximizing **expected points**.
- Enforces rules like squad size, formation, and budget.
- Easily extendable with custom constraints.

---

## 🛠️ Requirements
- Python 3.x
- pandas
- pulp

## Install dependencies:
```bash
pip install pandas pulp
```

## 📊 Data
The dataset (players.csv) should contain at least:

- name (player name)

- position (GK, DEF, MID, FWD)

- team

- value (price in millions)

- expected_points

## ⚙️ Model
Decision Variables:

- in_squad[i] ∈ {0,1} → Player i is in the squad

- is_start[i] ∈ {0,1} → Player i is a starter

## Objective:
Maximize:

Total Expected Points=∑(is_start[i]×expected_points[i])


## Constraints:

Squad size = 15

Starters = 11

Starters ⊆ Squad

(Optional) Budget ≤ 100

(Optional) Position constraints (1 GK, 3–5 DEF, 2–5 MID, 1–3 FWD)

## ▶️ Usage
Run the notebook:

```bash
jupyter notebook fpl_optimizer.ipynb
```

## 📈 Example Output
Final Squad: List of 15 players chosen

Starters: 11 best players according to the optimizer

