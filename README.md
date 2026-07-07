# No Plan Yet Human: A Reactive Robotics Model Predicts Human Planning Failures on a Clinical Task

**Authors**: Michael Migacev*, Vito Mengers*, Antonia Köngeter, Oliver Brock

\*shared first authorship

Paper accepted for publication at SAB 2026 (International Conference on the Simulation of Adaptive Behavior)

[preprint](https://arxiv.org/abs/2605.16514)

## Setup

The [environment_tol.yml](environment_tol.yml) file contains the environment information.

## Running the Code

### ToL AICON

### Analysis

#### Please keep in mind that no human data is made available with the Paper

To run the analysis you can prepare the human data with the [problem_ordering_preparation.ipynb](./src/domip/tower_of_london_move_gridsearch/evaluation/problem_ordering_preparation.ipynb) file. An example for the human data is provided [here](./src/tower_of_london_human_data/EXAMPLE_HUMAN_DATA.csv)

After preparing the human data you can either compare the human ordering to a fixed baseline such as [bfs_bidirectional](./src/tower_of_london_human_data/bfs_bidirectional_avg_nodes_for_po.csv) by running the [po_pipeline_pp_mult_val.py](./src/domip/tower_of_london_move_gridsearch/evaluation/po_pipeline_pp_mult_val.py):

```
python src\domip\tower_of_london_move_gridsearch\evaluation\po_pipeline_pp_mult_val.py "folder_with_human_orderings" --metric-path "file_for_baseline_orderings" --output-folder "output_folder_name" --permutation-runs 200 --seed 42 --splits-csv-path "csv-file_of_your_splits"
```

or compare it to the model data by running [top_analysis_average.py](./src/domip/tower_of_london_move_gridsearch/evaluation/top_analysis_average.py):

```
python "path_to/top_analysis_average.py" --reference-orderings-path "folder_with_human_orderings" --model-orderings-path "file_of_gridsearch_output" --cross-validation-path "csv-file_of_your_splits" --output-root "path_to_output" --folder-name "output_name" --seed 42 --permutation-runs 200 --metric-mode extra_number_of_moves --moves-till-failure none
```

## Provided Data

In case you do not intend to change existing parameters or run the ToL AICON code you can access the output of the given AICON configuration in [gridsearch_0-10000](./tower_of_london_plots/gridsearch_0-10000/)

### Please keep in mind that no human data is made available with the Paper
