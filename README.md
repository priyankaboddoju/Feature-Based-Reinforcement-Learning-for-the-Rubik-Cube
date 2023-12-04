# Feature-Based Reinforcement Learning for the Rubik's Cube - User Documentation

## Introduction

Welcome to the Feature-Based Reinforcement Learning project for solving the Rubik's Cube. This user documentation provides an overview of the project, its components, the algorithms used, and instructions on how to use and explore its features.

## Table of Contents

1. [Overview](#overview)
2. [Getting Started](#getting-started)
   - [Prerequisites](#prerequisites)
   - [Installation](#installation)
3. [Project Components](#project-components)
   - [puzzle.py](#puzzlepy)
   - [tests.py and others.py](#testspy-and-otherspy)
   - [Agent.py](#agentpy)
4. [Algorithms and How It Works](#algorithms-and-how-it-works)
5. [Using the Project](#using-the-project)
   - [Executing Q-Learning](#executing-q-learning)
   - [Customizing Initial Moves](#customizing-initial-moves)
6. [References](#references)
7. [Contributors](#contributors)
8. [License](#license)

## Overview

This project aims to solve the classic Rubik's Cube using Feature-Based Reinforcement Learning. It employs advanced techniques such as feature-based Q-Learning and a pattern database to represent and solve the cube. The primary assumption is that the Rubik's cube can only execute 180-degree side turns, simplifying the complexity of its state space.

## Getting Started

### Prerequisites

no Prerequisites required to run this project.

### Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/your-username/feature-based-rl-rubik-cube.git
   ```

2. Navigate to the project directory:

   ```bash
   cd feature-based-rl-rubik-cube
   ```

## Project Components

### puzzle.py

This file contains the state representation of a Rubik's Cube (`State()`), along with auxiliary functions used throughout the application.

### tests.py and others.py

These files include various test cases that can be executed to validate the correct implementation of the cube's state representation.

### Agent.py

`Agent.py` implements the reinforcement learning agent, executing iterations of Q-Learning. It utilizes a pattern database to construct a Q-Table, attempting to solve a given random Rubik's cube.

## Algorithms and How It Works

The core algorithms used in this project are:

### Feature-Based Q-Learning

Feature-based Q-Learning is a reinforcement learning technique that aims to learn a policy for solving the Rubik's Cube by assigning a quality value (Q-value) to each possible action in a given state. The key features of the cube, such as the number of solved sides, crosses, and correct pieces, are used to represent the state.

### Pattern Database

A pattern database is employed to quantify the quality of near-finished cubes. This database stores precomputed solutions for specific cube patterns, enabling the agent to make informed decisions based on the current state of the cube.

### Cube Representation

The Rubik's Cube is represented as a state object (`State()`) with methods to manipulate the cube, perform rotations, and check for goal states. The cube can only execute 180-degree side turns, significantly reducing the branching factor of the cube's state space tree.

## Using the Project

### Executing Q-Learning

To run Q-Learning on a scrambled cube and attempt to solve it, execute the following command:

```bash
python Agent.py
```

### Customizing Initial Moves

To change the number of initial moves applied to the cube, modify the value of `n` on line 22 in `Agent.py`:

```python
self.start_state = cube if cube is not None else n_move_state(n=5)
```

## References

- [OpenAI. _Solving Rubik's Cube with a Robot Hand._](https://openai.com/research/solving-rubiks-cube)
- [Kulkarni, Tejas D., et al. _Deep Successor Reinforcement Learning._](https://arxiv.org/abs/1606.02396)
- [Singh, Arun, et al. _End-to-End Deep Reinforcement Learning for Solving the Rubik's Cube._](https://arxiv.org/abs/1910.07113)
- [Mnih, Volodymyr, et al. _Playing Atari with Deep Reinforcement Learning._](https://arxiv.org/abs/1312.5602)
- [Ha, David, and Schmidhuber, Juergen. _World Models._](https://arxiv.org/abs/1803.10122)

## Contributors

Created by: Priyanka, Santosh & Rishikeswar

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.
