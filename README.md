# gfnx: Fast and Scalable Generative Flow Networks in jaX

This repository is gone through anonymisation to be submitted. This results in imperfect readme-file, documentation, and some other important description files. None of code functionality was changed for anonymisation.

`gfnx` is a JAX-native toolkit for building and studying Generative Flow Networks (GFlowNets). It brings together a collection of benchmark environments and reproducible baselines so you can iterate quickly on new ideas.

## Highlights

- End-to-end JAX implementations of GFlowNet building blocks (environments, reward modules, networks, and metrics).
- Ready-to-run baseline agents inspired by the [CleanRL](https://github.com/vwxyzjn/cleanrl) style of concise single-file experiments.
- Utilities for logging, checkpointing, and evaluation that make it easy to compare runs and extend the library with new research code.

## Installation

### Requirements

- Python 3.10 or newer.
- A working JAX installation. CPU works out of the box; for GPU/TPU accelerators follow the [official JAX installation guide](https://jax.readthedocs.io/en/latest/installation.html).

### Develop locally and run baselines

Download the project and setup:
```
cd gfnx
pip install -e .[baselines]
```

## Quickstart

Kick off a short training run of Detailed Balance in the Hypergrid environment:

```
python baselines/db_hypergrid.py num_train_steps=1_000 logging.tqdm_print_rate=100
```

The script is powered by Hydra, so you can override any configuration value on the command line (for example, picking another logging backend or playing with hyperparameters of the method). Baseline outputs, checkpoints, and Hydra logs default to `tmp/<date>/<time>/`; point the `logging.log_dir` or `logging.checkpoint_dir` fields to custom paths when running longer experiments.

## Influences

`gfnx` stands on the shoulders of several excellent open-source projects:

- [torchgfn](https://torchgfn.readthedocs.io/en/latest/) – PyTorch-first GFlowNet library that shaped our environment design.
- [CleanRL](https://github.com/vwxyzjn/cleanrl) – taught us the value of single-file baselines and reproducible experiment configs.
- [purejaxrl](https://github.com/luchris429/purejaxrl/tree/main) and [JaxMARL](https://github.com/FLAIROx/JaxMARL/tree/main/jaxmarl) – reference points for idiomatic, accelerator-ready JAX reinforcement learning code.
