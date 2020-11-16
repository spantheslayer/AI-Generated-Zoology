# AI-Generated-Zoology

Our goal is to be able to convert an animal sketch to an animal picture.

## Set-up project

1. Git clone the repository

```
git clone https://github.com/niyonx/AI-Generated-Zoology.git
```

2. Create your python virtual environment

```
virtualenv --python=/usr/bin/python3.8 venv
source venv/bin/activate
```

3. Install dependencies

```
pip install -r requirements.txt
```

## Run Jupyter Notebooks:

**Locally**: Make sure jupyter is using venv python interpreter.

```
jupyter lab
```

**Online**: Upload notebook on [Google Colab](https://colab.research.google.com/notebooks/intro.ipynb#recent=true).


## Images to sketch

1. Input is in data/raw-img

2. Convert all .png files to .jpeg by executing **png_to_jpeg.py** (PhotoSketch doesn't seem to work on .png files, even if it says it should)

3. From PhotoSketch directory run

```
./scripts/test_pretrained.sh (Linux)
```
```
./scripts/test_pretrained.cmd (Windows, can run from any directory or just double click on file)
```
4. Output sketches will be in data/sketch-img

Input and Output directory can be modified from scripts/test_pretrained file. [More info](https://github.com/mtli/PhotoSketch).

## Data folder structure
data/ was temporarily added to .gitignore. We will add and create many files inside it, thus we want to avoid github having to sync thousands of files and induce lagg.\
Just make sure that your data/ dir has the following structure:\
data/\
|--train\
|--test\
|--raw-img\
|--sketch-img

## How to generate train and test data

Assuming you have done all the previous steps:

1. Execute **resize_combine.py**\
Will throw exception if filenames(without extension) in data/raw-img and data/sketch-img don't have a 1-to-1 corespondance

2. Execute **shuffle_into_train_test.py**

