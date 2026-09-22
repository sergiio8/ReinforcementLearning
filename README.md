# Discretized CartPole Q-Learning

This repository contains an **academic coursework notebook**, not a production
reinforcement-learning package. The work was prepared for *Inteligencia
Artificial 2024/25* and explores tabular Q-learning in a continuous-state
environment after discretization.

## What is included

[`RLSergio_Daniel.ipynb`](RLSergio_Daniel.ipynb) studies
[Gymnasium's CartPole-v1 environment](https://gymnasium.farama.org/environments/classic_control/cart_pole/).
The notebook:

- introduces the CartPole observation and action spaces;
- discretizes the four continuous observations into bins;
- implements a tabular `QLearnAgent`;
- trains the agent with alpha, gamma, and epsilon hyperparameters;
- plots episode-average performance; and
- compares the effect of alpha, epsilon, and gamma through a configured
  5 × 5 × 5 hyperparameter sweep.

The notebook includes explanatory Spanish coursework notes and embedded
figures. The authors identified in the notebook are Sergio Martínez Olivera
and Daniel Roldán Serrano.

## Setup

Python 3.10 or newer is recommended. Create and activate a virtual
environment, then install the declared dependencies:

```bash
python -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

The `classic-control` extra provides the optional rendering dependency used by
the introductory CartPole demonstration.

## Running the notebook

Start Jupyter from the repository root:

```bash
jupyter lab
```

Open `RLSergio_Daniel.ipynb` and execute the cells **in order**. Later cells
reuse the environment, agent, and sweep variables created earlier. The
introductory random-action demonstration requests a human-rendered CartPole
window, so a graphical desktop session may be needed for that cell.

The baseline training example uses 1,500 episodes. The larger parameter
experiment is configured as a 5 × 5 × 5 comparison over approximately 1,000
episodes per combination and can take a substantial amount of time.

## Current status and limitations

This is a notebook-based experiment and should be read as coursework rather
than as a reusable library or benchmark:

- The stored output for the first large parameter sweep ends in a
  `KeyboardInterrupt`; the repository does not prove that all 125 combinations
  completed.
- No random seeds are recorded, so numerical results are not deterministic.
- Dependencies are documented in `requirements.txt`, but there is no packaged
  Python module, automated test suite, or continuous-integration workflow.
- Results and figures are notebook artifacts. Re-running the notebook can
  produce different values and requires the cells to be executed in sequence.
- The notebook's original reward handling and episode accounting are retained
  as submitted; this repository does not claim a production-quality evaluation
  protocol.

The repository is provided under the [MIT License](LICENSE).
