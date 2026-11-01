# University Research Projects

This repository contains research projects and academic work from my Master's degree in Statistics and Computer Science. The current projects focus on swarm intelligence and metaheuristic optimization.

## Projects

### `metaheuristic-algorithms`

A Python project containing implementations and benchmark experiments for three population-based optimization algorithms:

- Walrus Optimizer (WO)
- Particle Swarm Optimization (PSO), implemented in `pos.py`
- Ant Colony Optimization (ACO), implemented in `aco.py`

The experiment compares the algorithms on 23 standard benchmark functions grouped as unimodal (F1–F7), multimodal (F8–F13), and fixed-dimension multimodal (F14–F23). It uses the same population size and maximum number of iterations for each algorithm, records summary statistics, compares mean results with WO, and generates qualitative plots for selected WO runs.

To install the dependencies and run the default experiment:

```bash
cd metaheuristic-algorithms
python -m pip install -r requirements.txt
python main.py
```

The default configuration runs 100 independent trials with a population of 10 and 50 iterations. Functions with fixed dimensions use their required dimensions; the others use the configured dimension. These are reduced settings for a manageable experiment. The article uses a population of 100 and 2,000 iterations; update those values in `main.py` to use its settings.

The experiment writes its outputs to the path configured by `output_path` in `main.py`. The current outputs include:

- `statistics.csv` — best, worst, mean, standard deviation, and median runtime for each algorithm and benchmark
- `comparison_with_wo.csv` — counts of benchmark wins, ties, and losses against WO
- `qualitative/` — plots for selected WO benchmark runs

See the [algorithm project README](metaheuristic-algorithms/README.md) for implementation and experiment details.

### `walrus-optimizer`

A LaTeX report on the Walrus Optimizer. It presents WO's biological motivation and mathematical model and discusses its benchmark results alongside PSO and ACO. The report source is in `walrus-optimizer/`; the compiled document is available as [`main.pdf`](walrus-optimizer/main.pdf).

## Clone the repository and its submodule

`metaheuristic-algorithms` is a Git submodule. Clone the repository and initialize its submodules with:

```bash
git clone --recurse-submodules <repository-url>
```

If you have already cloned the repository without its submodule, initialize it from the repository root with:

```bash
git submodule update --init --recursive
```

To check out the submodule commit recorded by the parent repository, run the same update command from the repository root.

## Repository structure

```text
.
├── metaheuristic-algorithms/  # Python implementations and benchmark experiments
└── walrus-optimizer/          # LaTeX report and figures
```
