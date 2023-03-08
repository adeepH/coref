# How to run a minimal coref

## Setup
1. Download this [repo](https://github.com/mandarjoshi90/coref)
1. Create a new conda environment with python=3.5
1. cd into the downloaded repo and install requirements.txt with pip

## Downloading the weights
1. set the variable data_dir to the path to onto-notes ex., `export data_dir=<path_to_onto_notes>`
1. inside the repo run `./setup_all.sh`
1. inside the repo run `./download_pretrained.sh spanbert_large`

## Prediction
1. The repo has a sample sentence in `cased_config_vocab/trial.jsonlines`
1. To run the prediction on the file run `GPU=0 predict.py spanbert_large cased_config_vocab/trial.jsonlines output.txt`
