# Baselines

The `baselines/` directory collects reproducible training scripts for canonical GFlowNet objectives and a few closely related algorithms. Each script follows the CleanRL-style single-file pattern, relies on Hydra for configuration management, and logs to the shared `tmp/` directory unless overridden.

## Implementation matrix

The table below summarizes which method-environment combinations currently ship with the repository. Cells marked with &#x2705; point to a ready-to-run script in `baselines/`; &#x1F6A7; means experimental and unverified script that may not work; &#x274C; indicates that the pairing has not been implemented yet.

| Method / Environment | Hypergrid | BitSeq | TFBind-8 | QM9 Small | AMP | GFP |
| --- | --- | --- | --- | --- | --- | --- |
| Detailed Balance (DB)&nbsp;[1] | &#x2705; | &#x2705; | &#x2705; | &#x2705; | &#x2705; | &#x1F6A7; |
| Trajectory Balance (TB)&nbsp;[2] | &#x2705; | &#x2705; | &#x2705; | &#x2705; | &#x2705; | &#x274C; |
| Sub-Trajectory Balance (SubTB)&nbsp;[3] | &#x2705; | &#x2705; | &#x2705; | &#x274C; | &#x274C; | &#x274C; |

## Special-purpose scripts

Some environments require bespoke objectives or training tweaks. These live alongside the standard baselines:

- `baselines/soft_dqn_hypergrid.py` – Online SoftDQN baseline for Hypergrid&nbsp;[4].
- `baselines/mdb_dag.py` – Modified Detailed Balance for Bayesian network structure learning&nbsp;[5].
- `baselines/fldb_phylo.py` – Forward-Looking Detailed Balance for phylogenetic tree generation&nbsp;[6].
- `baselines/tb_ising.py` – Energy-based modeling of the Ising system using a TB objective&nbsp;[7].

## How to run a baseline

1. Install the package with baseline extras: `pip install -e '.[baselines]'`.
2. Launch the desired script, optionally overriding Hydra configs. For example:

```bash
python baselines/db_hypergrid.py num_train_steps=1_000 logging.tqdm_print_rate=100
```

Each script documents the relevant configuration group in its module docstring. Point `logging.log_dir` or `logging.checkpoint_dir` to persistent storage when running long jobs.


## References

REMOVED DURING ANONIMISATION
