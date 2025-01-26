# Synergistic-Multi-Agent-Framework-for-Energy-Optimization-in-Cloud-Tasks

## Overview

This project introduces a Q-learning-based framework designed to optimize task allocation and resource management for energy efficiency in multi-cloud systems. The proposed approach uses an epsilon-greedy policy to dynamically allocate tasks across virtual machines (VMs) based on predicted CPU and memory usage, energy consumption, and task priorities. The framework integrates AWS SageMaker for forecasting CPU and memory demands and uses Amazon S3 for data storage. The experimental results show that the framework achieves a 25% reduction in energy consumption compared to traditional scheduling approaches like FIFO and Round Robin, without compromising system performance.

## Authors

- Mummadi Hemanth Reddy
- Okesh Ankireddypalli
- Mouhitha Arella
- Saranya Gujjula
- Suja Palaniswamy

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Methodology](#methodology)
- [Task Allocation Process](#task-allocation-process)
- [Q-Learning Mechanism](#q-learning-mechanism)
- [Reward Sharing](#reward-sharing)
- [Simulation and Analysis](#simulation-and-analysis)
- [Optimization](#optimization)
- [Evaluation Metrics](#evaluation-metrics)
- [Contributing](#contributing)

## Installation

To get started, clone the repository and install the necessary dependencies:

### Clone the repository:

```bash
git https://github.com/okesh1215/Synergistic-Multi-Agent-Framework-for-Energy-Optimization-in-Cloud-Tasks.git
```

Navigate to the project folder:

```bash
cd Synergistic-Multi-Agent-Framework-for-Energy-Optimization-in-Cloud-Tasks
```

Install the dependencies:

```bash
pip install -r requirements.txt
```

## Usage

1. **Set up the cloud environment**: Ensure that you have access to AWS SageMaker and Amazon S3 for forecasting and data storage.
2. **Run the task allocation and scheduling pipeline**: The task allocation process will be initiated based on the input tasks and resource availability.
3. **Visualize the results**: The output will include logs showing energy consumption reductions and task allocation details.
4. **Monitor performance**: Use the provided metrics and analysis to assess the framework's effectiveness in real-time.

## Methodology

The framework applies a Q-learning-based approach to optimize task scheduling by integrating machine learning for CPU and memory demand forecasting.

### Key Components:
- **Virtual Machines (VMs)**: Each VM is modeled with resource control capabilities and keeps a Q-table for task allocation.
- **Task Representation**: Tasks are modeled with features like priority, power consumption, and resource requirements.
- **Cloud Representation**: Clouds contain multiple VMs, and tasks are pre-allocated based on the cloud's access history and resource utility.

## Task Allocation Process

Tasks are allocated based on:

- Predicted CPU and memory usage.
- Current resource availability of VMs.
- Energy consumption implications of task allocation.

## Q-Learning Mechanism

The Q-learning mechanism uses a state-action-reward paradigm to optimize task allocation.

### Q-learning Update Rule:

The Q-values are updated using the following formula:

```text
Q(s, a) ← Q(s, a) + α [r + γ max_a' Q(s', a') − Q(s, a)]
```

Where:
- `s` is the current state
- `a` is the action taken
- `r` is the reward received
- `α` is the learning rate
- `γ` is the discount factor

### Rewards:
- **Positive reward**: For energy-efficient task allocation.
- **Negative reward**: For task rejection or excessive energy consumption.

## Reward Sharing

An intra-cloud reward-sharing mechanism is used to encourage collaboration between VMs within the same cloud, incentivizing them to optimize energy consumption collectively.

## Simulation and Analysis

The framework is validated on a synthetic multi-cloud environment. Key performance metrics include:
- Total energy used.
- Success rate of task allocation.
- Q-table learning efficiency.

The results highlight the framework's ability to reduce energy consumption while maintaining high-quality service.

## Optimization

The Q-learning parameters, including the learning rate (`α`), discount factor (`γ`), and exploration rate (`ϵ`), are fine-tuned to optimize task allocation and energy efficiency.

## Evaluation Metrics

The performance of the framework is evaluated based on:

- **Energy consumption reduction**: The framework achieves up to 25% energy savings compared to traditional scheduling algorithms like FIFO and Round Robin.
- **Task allocation success rate**: Tasks are successfully allocated while meeting deadlines and energy efficiency goals.

## Contributing

We welcome contributions to this project! If you have suggestions or improvements, please follow these steps:

1. Fork the repository.
2. Create a feature branch: `git checkout -b new-feature`.
3. Make changes and commit: `git commit -am 'Add new feature'`.
4. Push to the branch: `git push origin new-feature`.
5. Open a pull request.

Feel free to reach out if you encounter any issues or need further assistance!
