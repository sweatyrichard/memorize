# Memorize

This is a repository containing code and data for the paper:

> B. Tabibian, U. Upadhyay, A. De, A. Zarezade, Bernhard Schölkopf, and M. Gomez-Rodriguez. Enhancing Human Learning via Spaced Repetition Optimization. To appear at the Proceedings of the National Academy of Sciences (PNAS), 2019.

An in a nutshell description of our algorithm is available in this
supporting website: [http://learning.mpi-sws.org/memorize/](http://learning.mpi-sws.org/memorize/).

## Pre-requisites

This code depends on the following packages:

 1. `numpy`
 2. `pandas`
 3. `matplotlib`
 4. `seaborn`
 5. `scipy`
 6. `dill`
 7. `click`

## Code structure

 - `memorize.py` contains the memorize algorithm.
 - `preprocesed_weights.csv` contains estimated model parameters for the [HLR model](https://github.com/duolingo/halflife-regression), as described in section 8 of supplementary materials.
 - `observations_1k.csv` contains a set of 1K user-item pairs and associated number of total/correct attempts by every user for given items. This dataset has been curated from a larger dataset released by Duolingo, available [here](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/N8XJME).

## Execution

The code can by executed as follows:

`python memorize.py`

The code will use default parameter value (q) used in the code.

----

# Experiments with Duolingo data

## Pre-processing

Convert to Python `dict` by `user_id, lexeme_id` and pruning it for reading it:

    python dataset2dict.py ./data/raw/duolingo.csv ./data/duo_dict.dill --success_prob 0.99 --max_days 30 
    python process_raw_data.py ./data/raw/duolingo.csv ./data/duolingo_reduced.csv

## Plots

See the notebook `plots.ipynb`.
