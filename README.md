# mvts-imputation
Multivariate Time Series Imputation by Graph Neural Networks and other methods

```
Note that, given the size of the files, the datasets are not readily available in the folder. See the next section for the downloading instructions.
```

## Datasets

All the datasets used in the experiment, except CER-E, are open and can be downloaded from this [link](https://mega.nz/folder/qwwG3Qba#c6qFTeT7apmZKKyEunCzSg). The CER-E dataset can be obtained free of charge for research purposes following the instructions at this [link](https://www.ucd.ie/issda/data/commissionforenergyregulationcer/). We recommend storing the downloaded datasets in a folder named `datasets` inside this directory.

## Configuration files

The `config` directory stores all the configuration files used to run the experiment. They are divided into folders, according to the model.

## Library

The support code, including the models and the datasets readers, are packed in a python library named `lib`. Should you have to change the paths to the datasets location, you have to edit the `__init__.py` file of the library.

## Scripts

The scripts used for the experiment in the paper are in the `scripts` folder.

* `run_baselines.py` is used to compute the metrics for the `MEAN`, `KNN`, `MF` and `MICE` imputation methods. An example of usage is

	```bash
	python ./scripts/run_baselines.py --datasets air36 air --imputers mean knn --k 10 --in-sample True --n-runs 5
	```

* `run_imputation.py` is used to compute the metrics for the deep imputation methods. An example of usage is

	```bash
	python ./scripts/run_imputation.py --config config/grin/air36.yaml --in-sample False
	```

* `run_synthetic.py` is used for the experiments on the synthetic datasets. An example of usage is

	```bash
	python ./scripts/run_synthetic.py --config config/grin/synthetic.yaml --static-adj False
	```

## Requirements

We run all the experiments in `python 3.8`, see `requirements.txt` for the list of `pip` dependencies.
