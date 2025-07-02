# Dynamic Graph-Based Multi-Agent Rescue Simulation in Post-Earthquake NovaCity

A simulation framework that uses AI-based optimization and reasoning to coordinate police and fire truck deployments across disaster-stricken NovaCity after a major earthquake.

## 🎯 Overview

This project integrates multiple AI algorithms into a unified simulation framework:

* **City**: Modeled as a dynamic graph with evolving fire and road damage in 5 regions
* **Agents**: Fire trucks and police units perform rescues
* **Damage**: Fires increase every 10 minutes; road blocks increase every 15 minutes
* **Goal**: Optimally reduce total damage using coordinated multi-agent deployment

## 🧠 Algorithms Used

### 🔬 Genetic Algorithm (GA)

* Optimizes initial path allocations for fire trucks and police units
* **Fitness function**: Total damage reduction based on unit placement
* **Chromosome**: Encoded as sequences of region visits

### 🐜 Ant Colony Optimization (ACO)

* Simulates pheromone-based exploration to identify optimal paths
* Separate runs for **fire** and **police** operations
* **Pheromone strength** is based on distance and regional damage severity

### ♟️ Minimax with Alpha-Beta Pruning

* Models a competitive turn-based simulation:

  * **MAX**: Rescue teams reducing damage
  * **MIN**: Disasters increasing damage
* Integrates GA-derived paths into decision trees for faster convergence

### 🎲 Game Theory

* Determines Nash Equilibria between possible disaster reactions and rescue strategies
* Assesses strategic allocation trade-offs in scenarios with adversarial escalation

### 🧮 Bayesian Networks

* Predicts probability of future fire/road conditions per region
* Updates beliefs after each action (rescue or disaster increment)

## 🔁 Rescue Simulation

* **Regions**: R1 to R5

* **Initial Damage**:

  * R1: 60% roads, 35% fires
  * R2: 40% roads, 25% fires
  * R3: 15% roads, 5% fires
  * R4: 35% roads, 30% fires
  * R5: 5% roads, 3% fires

* **Units**:

  * 8 Fire Trucks (start at R2): reduce fire by 10% per unit per operation
  * 6 Police Units (start at R4): reduce road blockage by 10% per unit per operation

* **Distance Graph**: Fully connected with weighted distances (e.g., R1 -- R2 = 5km)

* **Time Ticks**: Fire spreads every 10 minutes, Road blocks increase every 15 minutes

## 📊 Features

* **Modular Simulation**: Plug-and-play algorithm design
* **Graph-Based Movement**: Region-to-region distance impacts rescue pathing
* **Real-Time Damage Modeling**: Simulates damage increase if unaddressed
* **Comparative Analysis**: Evaluate algorithms by damage minimisation, path efficiency

## 📈 Sample Outputs

* Visualizations: Damage over time, unit paths
* Metrics: Final fire %, road blockage %, total utility, algorithm runtime

## 🤝 Contributing

Contributions welcome via pull requests.

## 📜 License

MIT License
