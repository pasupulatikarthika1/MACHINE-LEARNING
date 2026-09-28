# Soft Actor-Critic Based Semantic-Aware Resource Allocation for Hybrid Semantic/Bit NOMA Networks

##  Project Overview

This project proposes a Soft Actor-Critic (SAC) based resource allocation framework for Hybrid Semantic/Bit NOMA networks.

The system supports two types of users:

- Semantic users, who focus on the importance and meaning of transmitted information.
- Conventional bit users, who focus on data rate and communication performance.

The SAC agent learns how to allocate transmission power and time resources among users under changing wireless channel conditions.

##  Problem Statement

Hybrid Semantic/Bit NOMA networks need to share limited wireless resources between users with different communication requirements.

The project addresses the challenge of jointly allocating power and transmission time while considering:

- Throughput
- Semantic utility
- Quality of Service (QoS)
- Fairness
- Energy efficiency

## Proposed Methodology

The project models resource allocation as a continuous-control reinforcement learning problem.

The workflow is:

1. Generate user positions and channel conditions.
2. Schedule users using OFDMA and NOMA.
3. Provide the network state to the SAC agent.
4. SAC generates power and time allocation.
5. Calculate SINR, throughput, semantic utility, QoS, fairness and energy efficiency.
6. Calculate the reward.
7. Store the transition in the replay buffer.
8. Update the SAC actor and critic networks.
9. Repeat the process for multiple training episodes.

##  System Configuration

| Parameter | Value |
|---|---:|
| Number of users | 20 |
| Semantic users | 11 |
| Bit users | 9 |
| OFDMA subcarriers | 5 |
| Users per subcarrier | 4 |
| Total bandwidth | 10 MHz |
| Power budget | 10 W |
| Frame duration | 1 s |
| Carrier frequency | 2.4 GHz |
| Training episodes | 1,200 |
| Evaluation episodes | 200 |
##  SAC Configuration

- Actor network with 2 hidden layers
- 128 neurons per hidden layer
- ReLU activation
- Twin critic networks
- Automatic entropy tuning
- Adam optimizer
- Learning rate: 3 × 10⁻⁴
- Discount factor: 0.99
- Replay buffer: 50,000 transitions
- Batch size: 128

##  Results

The evaluation compares SAC with an equal-allocation baseline.

Reported results include:

- Energy efficiency: 3.05 vs 1.64 Mbps/W
- Transmit power used: 5.19 W vs 10 W
- Throughput: 15.86 vs 16.42 Mbps
- Energy efficiency improvement: approximately 86%
- Power usage reduction: approximately 48%

The current implementation shows that the SAC agent learns to reduce power usage while retaining most of the throughput.

The current results also indicate that semantic users are not yet strongly prioritised, which is identified as an area for further improvement.

##  Technologies Used

- Python
- PyTorch
- Gymnasium
- NumPy
- Pandas
- Matplotlib
- SciPy
- Scikit-learn
- Jupyter Notebook
- Google Colab

##  Project Files

### Notebook

`Final_SAC_Semantic_Aware_Power_Time_Hybrid_NOMA_OFDMA.ipynb`

Contains the implementation of the simulation environment, SAC agent, training and evaluation.

### Presentation

`SAC_Semantic_NOMA_Review2.pptx`

Contains the project presentation, methodology, workflow, simulation results and current progress.

### Abstract

`ML-FINALABSTRACT (1).pdf`

Contains the project abstract and software requirements.

## Future Work

- Improve reward shaping to prioritise semantic users.
- Compare with additional reinforcement learning algorithms.
- Compare against conventional optimization approaches.
- Test multiple random seeds.
- Study scalability with different numbers of users and subcarriers.
- Further analyse semantic utility and QoS.

##Project Team

- N. Jesly Monica
- M. Shreya
- P. Karthika

## 📚 Course

Machine Learning (25SC2107E)

Academic Year: 2026–27
