# AI Probabilistic Reasoning Practicals

A comprehensive collection of Python implementations for fundamental probabilistic reasoning algorithms in Artificial Intelligence, focusing on Hidden Markov Models (HMM) and Bayesian Networks.

## 📋 Overview

This repository contains educational implementations of key probabilistic inference algorithms used in AI systems. The project demonstrates practical applications of probabilistic graphical models through two main modules:

1. **Hidden Markov Model Analysis** - Implementation of HMM inference algorithms
2. **Bayesian Network for Robot Navigation** - Probabilistic reasoning for autonomous navigation

## ✨ Features

### Hidden Markov Models (HMM)
- ✅ Custom implementation of **Viterbi Algorithm** for finding optimal state sequences
- ✅ **Forward-Backward Algorithm** for computing posterior probabilities
- ✅ Validation against `hmmlearn` library implementation
- ✅ Visualization of hidden state sequences
- ✅ Support for multi-state, multi-observation scenarios

### Bayesian Networks
- ✅ **Conditional Probability Distribution (CPD)** implementation
- ✅ **Variable Elimination Algorithm** for exact inference
- ✅ Robot navigation scenario modeling with uncertainty
- ✅ Graphical network visualization using NetworkX
- ✅ Probabilistic reasoning for:
  - Weather conditions (clear, rain, fog)
  - Battery level management
  - Sensor accuracy modeling
  - Obstacle detection
  - Goal-directed navigation

## 🛠️ Technologies Used

- **Python 3.7+**
- **NumPy** - Numerical computations and matrix operations
- **Matplotlib** - Data visualization and plotting
- **NetworkX** - Bayesian network graph visualization
- **hmmlearn** - HMM reference implementation for validation
- **Jupyter Notebook** - Interactive development environment

## 📦 Prerequisites

- Python 3.7 or higher
- pip package manager
- Jupyter Notebook or JupyterLab

## 🚀 Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/koushamoeini/ai-probabilistic-reasoning-practicals.git
   cd ai-probabilistic-reasoning-practicals
   ```

2. **Create a virtual environment** (recommended)
   ```bash
   python -m venv venv
   
   # On Windows
   venv\Scripts\activate
   
   # On macOS/Linux
   source venv/bin/activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Launch Jupyter Notebook**
   ```bash
   jupyter notebook
   ```

## 📖 Usage

### Hidden Markov Model Analysis

Navigate to `notebooks/hmm_analysis.ipynb` to explore:

```python
# Define HMM parameters
A = np.array([...])  # Transition probabilities
B = np.array([...])  # Emission probabilities
pi = np.array([...]) # Initial state probabilities

# Run Viterbi algorithm
optimal_path = viterbi(observations, A, B, pi)

# Run Forward-Backward algorithm
gamma, alpha, beta = forward_backward(observations, A, B, pi)
```

**Example Output:**
```
Optimal state sequence: [0, 1, 3, 2, 1, 0, 3, 3, 1, 2]
Posterior probabilities computed successfully
```

### Bayesian Network for Robot Navigation

Navigate to `notebooks/bayesian_robot_navigation.ipynb` to explore:

```python
# Define CPDs for robot navigation
weather_cpd = CPD(["Weather"], {...})
sensor_cpd = CPD(["Weather", "SensorAccuracy"], {...})
battery_cpd = CPD(["BatteryLevel"], {...})

# Perform inference
result = variable_elimination(cpds, query_vars=["RobotPosition"], 
                              evidence={"Weather": "clear", "BatteryLevel": "high"})
```

**Example Output:**
```
P(RobotPosition=goal) = 0.78
P(RobotPosition=obstacle) = 0.15
P(RobotPosition=stuck) = 0.07
```

## 📁 Project Structure

```
ai-probabilistic-reasoning-practicals/
├── notebooks/
│   ├── hmm_analysis.ipynb              # Hidden Markov Model implementations
│   └── bayesian_robot_navigation.ipynb # Bayesian Network for robot navigation
├── src/
│   └── __init__.py                     # Python package initialization
├── docs/
│   └── screenshots/                    # Documentation images (placeholder)
├── requirements.txt                     # Python dependencies
├── .gitignore                          # Git ignore rules
├── LICENSE                             # MIT License
└── README.md                           # Project documentation
```

## 📊 Algorithms Implemented

### 1. Viterbi Algorithm
Finds the most likely sequence of hidden states given observations.

**Time Complexity:** O(N²T) where N = number of states, T = sequence length

### 2. Forward-Backward Algorithm
Computes posterior probabilities of hidden states at each time step.

**Time Complexity:** O(N²T)

### 3. Variable Elimination
Performs exact inference in Bayesian networks by systematically eliminating variables.

**Time Complexity:** Depends on network structure and elimination order

## 🖼️ Screenshots

### HMM State Visualization
![HMM States](docs/screenshots/hmm_states_placeholder.png)
*Visualization of hidden state sequences identified by the Viterbi algorithm*

### Bayesian Network Graph
![Bayesian Network](docs/screenshots/bayesian_network_placeholder.png)
*Robot navigation Bayesian network showing dependencies between variables*

## 🎓 Educational Context

These implementations were developed as part of the **Artificial Intelligence** course at Sharif University of Technology, Computer Engineering Department (Fall 2024). The assignments focus on:

- Understanding probabilistic reasoning in AI systems
- Implementing core algorithms from scratch
- Validating custom implementations against established libraries
- Applying theoretical concepts to practical scenarios


## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Author
   
   koushamoeini
   - Email: koushamoeini@gmail.com
   - GitHub: [@koushamoeini](https://github.com/koushamoeini)

   - 
## 📚 References

- Rabiner, L. R. (1989). "A tutorial on hidden Markov models and selected applications in speech recognition"
- Pearl, J. (1988). "Probabilistic Reasoning in Intelligent Systems"
- Koller, D., & Friedman, N. (2009). "Probabilistic Graphical Models: Principles and Techniques"
