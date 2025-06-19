# Short README

## Install
```bash
GIT_LFS_SKIP_SMUDGE=1 uv sync
GIT_LFS_SKIP_SMUDGE=1 uv pip install -e .
```

## Create a new dataset

See LeRobotDataset documentation [here](https://github.com/huggingface/lerobot/blob/main/lerobot/common/datasets/lerobot_dataset.py#L363)

#### Add dataset to training configs

* Edit [src/openpi/training/config.py](./src/openpi/training/config.py)
* Add an entry to the _CONFIGS array

## Train a model

#### Log in to WandB
```bash
$ pip install wandb
$ wandb login
```

#### Standard training
```bash
XLA_PYTHON_CLIENT_MEM_FRACTION=0.99 python scripts/train.py pi0_ur10e_finetune --exp-name=<EXPERIMENT NAME> --overwrite
```
#### LoRA Training
```bash
XLA_PYTHON_CLIENT_MEM_FRACTION=0.99 python scripts/train.py pi0_ur10e_finetune_lora --exp-name=<EXPERIMENT NAME> --overwrite
```