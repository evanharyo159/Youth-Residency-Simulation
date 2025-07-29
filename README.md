# Youth Residency Simulation

This repository contains a NetLogo agent-based simulation model that explores the factors influencing youth residency in a simulated urban environment. It investigates how the distribution, popularity, and accessibility of urban facilities (cafes, libraries, bars, shops) impact young people's decisions to become permanent residents.

## 🧠 Model Overview

### 👤 People (Turtles)
- Represent individuals with attributes: age, gender, employment status, vehicle ownership, and residency status (`is-resident?`).
- Move around the environment, visit facilities, and decide on residency based on satisfaction.

### 🏙️ Facilities (Turtles)
- Represent cafes, libraries, bars, and shops.
- Each has: location, fame, capacity, current visitors, queue, price, and satisfaction score.

## ⚙️ Simulation Mechanics

### 🔄 Daily Flow
- People are born (at 18) and die (at `death-age`).
- Newcomers start as non-residents.
- Individuals choose facilities to visit based on a **weighted scoring system** considering:

  - **Distance** (proximity)
  - **Fame** (popularity)
  - **Queue Penalty** (crowdedness)

- Facility satisfaction and fame dynamically evolve.
- Residency decision is made using a **logistic probability function** based on the last facility's satisfaction.

## 🧪 Key Feature: Automated Experimentation

Run `experiment-best-configs` to:
- Test different combinations of:
  - Facility counts (cafes, libraries, bars, shops)
  - Weighting schemes (distance, fame, queue)
- Record simulation results (young residents, growth)
- Identify the **best configuration** for maximizing youth residency.
- Results saved in `best_config_results.csv`.

---

## 🚀 How to Run

### Prerequisites
- NetLogo 6.x installed 

### Steps
1. Download `youth-residency-simulation-model.nlogo`.
2. Open the file in NetLogo.
3. Adjust parameters in the Interface tab as needed.
4. Click `setup`, then `go` to start the simulation.

### Run Experiment
- Click `experiment-best-configs` to launch automated testing.
- Results will be saved to a CSV file in the model’s directory.

---

## 🔧 Adjustable Parameters

| Variable                  | Description                                               |
|--------------------------|-----------------------------------------------------------|
| `num-cafes`              | Number of cafes                                           |
| `num-libraries`          | Number of libraries                                       |
| `num-bars`               | Number of bars                                            |
| `num-shops`              | Number of shops                                           |
| `score-weight-distance`  | Importance of proximity in facility choice (0.0–1.0)      |
| `score-weight-fame`      | Importance of fame in facility choice (0.0–1.0)           |
| `score-weight-queue`     | Penalty for queue length in facility choice (0.0–1.0)     |
| `max-facility-capacity`  | Max visitors a facility can handle                        |
| `satisfaction-threshold` | Minimum satisfaction to consider becoming a resident      |
| `facility-radius`        | Max distance people consider for visiting a facility      |
| `birth-rate`             | New people added per tick                                 |
| `death-age`              | Age when people are removed                               |

---

## 📊 Output

### Visual
- Residents turn green.
- Facilities show varying fame and satisfaction.

### CSV (via `experiment-best-configs`)
Fields in `best_config_results.csv`:
- `tick`
- `num-cafes`, `num-libraries`, `num-bars`, `num-shops`
- `distance-weight`, `fame-weight`, `queue-weight`
- `young-residents` (final count)
- `young-growth` (increase in youth population)


