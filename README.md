## Conda environment

We recommend to new a Conda environment to run the code. We use Pytorch 1.12, DGL 1.0.1, and Rdkit 2023.3.1. It should be okay to use the latest Rdkit version with some slight changes accordingly. Please refer to the *requirements.txt* file for detailed packages.

## Step-1: Data preprocessing and Extract semi-template patterns

In the main directory (*~/DVMR/*)

1. Run data preprocessing, this will preprocess the USPTO-50K dataset to prepare required labels and DGL graphs.

```
python preprocessing.py
```

2. Extract semi-template patterns.

```
# extract semi-tempaltes for training data
python extract_semi_template_pattern.py --extract_pattern

# find semi-template patterns for all data
python extract_semi_template_pattern.py
```

## Step-2: Run model

Start to train DVMR_CL model with reaction category

```
python train.py --typed

python train.py --test_only
```

Train DVM model without reaction category

```
python train.py --typed False

python train.py --test_only
```







